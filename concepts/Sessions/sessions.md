# Comprendre l'usage des Sessions dans Sails

Le mot **sessions** est ici synonyme de tous les composants permettant de mémoriser de l'information à propos d'un **user agent** entre des requêtes.

>Un **user agent** est un logiciel (e.g. navigateur ou application) qui vous représente sur une machine (e.g. un onglet de navigateur sur votre ordinateur, une application mobile, ou un réfrigérateur). Le mot **client** aura ici la même signification que user agent. Celui-ci est associé à un cookie ou un token.

Les sessions peuvent être très utiles car le cycle requête/réponse est **indépendant**. Ce cycle est considéré indépendant comme ni le client, ni le serveur, ne stockent d'informations relatives à une requête lors des différents échanges entre le client et le serveur. C'est pourquoi un cycle requête/réponse prend fin quand une réponse est fournie au client à l'origine de la requête (e.g. `res.send()`).

Pour information nous allons traiter les sessions dans le cadre de navigateur pour user agent. Bien que vous puissez utiliser les sessions Sails pour tout type d'usage, l'usage original reste de mémoriser où est rendue l'authentification du client. L'authentification est le processus qui permet au client de prouver son identité auprès du serveur. Par exemple pour être autorisé à accéder à des fonctionnalités sensibles (administration, envoi de mails, etc...) je vais avoir besoin de démontrer que je corresponds à un utilisateur dans une base de données. Si je fournis au serveur un nom accompagné d'un mot de passe, il pourra alors vérifier la correspondance nom/mot de passe (si possible [chiffré](http://node-machine.org/machinepack-passwords/encrypt-password)) avec les enregistrements présents dans la base.  S'il y a correspondance, je suis authentifié. Mais comment représenter mon "identité" entre les requêtes ? Voila un problème que permet de résoudre les sessions.

### Qu'est-ce qui compose les Sessions
Il y a trois principaux composants des sessions implémentées par Sails:
1. Le **session store** où se situe l'information
2. Le middleware ayant pour rôle de gérer les sessions
3. Un cookie contenant un ID de session envoyé lors de chaque requête (par défaut, `sails.sid`)

Le **session store** peut ou bien être dans la mémoire (e.g. comportement par défaut des session store dans Sails), ou dans une base de données (e.g. Sails facilite l'utilisation de Redis dans ce but).  Sails est construit par dessus le middleware Connect pour la gestion des sessions; ce qui inclue un **cookie** attribué au client afin de se souvenir de l'ID de session (`sid`).

### Un jour dans la vie d'une *requête*, d'une *réponse*, et d'une *session* 
Quand une `requête` est reçue par Sails, l'entête de la requête est traité par le middleware de session.  

##### Scenario 1: The request header has no *cookie property*

If the header does not contain a cookie property, a `sid` is created in the session and a default session dictionary is added to `req` (e.g. `req.session`).  At this point you can make changes to the session property (usually in a controller/action).  For example, let's look at the following *login* action.

```javascript
module.exports = {
  
  login: function(req, res) {

    // Authentication code here

    // If successfully authenticated

    req.session.userId = foundUser.id;   // returned from a database

    return res.json(foundUser);

  }
}
```

Here we added a `userId` property to `req.session`.  

> **Note:** The property will not be stored in the *session store* nor available to other requests until the response is sent.

Once the response is sent, any new requests will have access to `req.session.userId`. Since we didn't have a cookie *property* in the request header a cookie will be established for us.  

##### Scenario 2: The request header has a cookie *property* with a `Sails.sid`

Now when the user agent makes the next request, the `Sails.sid` stored on the cookie is checked for authenticity and if it matches an existing `sid` in the session store, the contents of the session store is added as a property on the `req` dictionary (e.g. `req.session`).  We can access properties on `req.session` (e.g. `req.session.me`) or add properties to it (e.g. `req.session.me == someValue`).  The values in the session store might change but generally the `Sails.sid` and `sid` do not change.

### When does the `Sails.sid` change?
By default, the Sails session store is *in memory*.  Therefore, when you close the Sails server, the current session store moves on to session heaven (e.g. the session store disappears).  When Sails is restarted, although a user agent request contains a `Sails.sid` in the cookie, the `sid` is no longer in the session store.  Therefore, a new `sid` will be generated and replaced in the cookie.  The `Sails.sid` will also change if the user agent cookie expires or is removed.

>The lifespan of a Sails cookie can be changed from its default setting (e.g. never expires) to a new setting by accessing the `cookie.maxAge` property in `projectName/config/session.js`.


### Using *Redis* as the session store 

Redis is a key-value database package that can be used as a session store that is separate from the Sails instance.  This configuration for sessions has two benefits.  The first is that the session store will remain viable between Sails restarts.  The second is that if you have multiple Sails instances behind a load balancer, all of the instances can point to a single consolidated session store.

To enable Redis as a session store open `projectName/config/session.js` in your favorite text editor and uncomment the `adapter` property.  That's it.  During development as long as you have a Redis instance running on the same machine as your Sails instance your session store will use Redis.  You can point to a different Redis instance by configuring the following optional properties in `projectName/config/session.js`:

```
  // host: 'localhost',
  // port: 6379,
  // ttl: <redis session TTL in seconds>,
  // db: 0,
  // pass: <redis auth password>,
  // prefix: 'sess:',

```

For more information on configuring these properties go to [https://github.com/tj/connect-redis](https://github.com/tj/connect-redis).

#### Nerdy details of how the session cookie is created
The value for the cookie is created by first hashing the `sid` with a configurable *secret* which is just a long string.

>You can change the session `secret` property in `projectName/config/session.js`. 

The Sails `sid` (e.g. `Sails.sid`) then becomes a combination of the plain `sid` followed by a hash of the `sid` plus the `secret`.  To take this out of the world of abstraction, let's use an example.  Sails creates a `sid` of `234lj232hg234jluy32UUYUHH` and a `session secret` of `9238cca11a83d473e10981c49c4f`. These values are simply two strings that Sails combine and hash to create a `signature` of `AuSosBAbL9t3Ev44EofZtIpiMuV7fB2oi`.  So the `Sails.sid` becomes `234lj232hg234jluy32UUYUHH.AuSosBAbL9t3Ev44EofZtIpiMuV7fB2oi` and is stored in the user agent cookie by sending a `set-cookie` property in the response header. 

**What does this prevent?** It prevents a user from guessing the `sid` as well as prevents a evil doer from spoofing a user into making an authetication request with a `sid` that the evil doer knows.  This could allow the evil doer to use the `sid` to do bad things while the user is authenticated via the session.

<docmeta name="displayName" value="Sessions">
