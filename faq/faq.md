# Questions fréquemment posées

### Comment la documentation se retrouve-t-elle sur le site web de Sails?

La documentation est compilée à partir des fichiers markdown dans le [`sails-docs` repo sur github] (https://github.com/balderdashy/sails-docs). Un certain nombre d'utilisateurs de Sails ont exprimé leur intérêt à imiter le processus que nous utilisons pour générer les pages sur le site Web de Sails. La bonne nouvelle est simple: le processus de compilation des documents Sails implique de générer du HTML à partir des fichiers Markdown dans le repo sails-docs, puis d'effectuer des transformations supplémentaires telles que l'ajout de bulles de données, le marquage de permaliens pour chaque section de pages pour alimenter le menu de navigation latérale et paramétrer les attributs HTML <<title> `pour une meilleure visibilité des moteurs de recherche des différentes pages de document. Voir le module [doc-templater] (https://github.com/uncletammy/doc-templater) pour plus d'informations.


### Où est la documentation pour les différentes versions de Sails?
La [documentation sur le site principal] (http://sailsjs.com/documentation) est pour la dernière version stable de Npm de Sails, et est reflétée par la [branche principale du repo `sails-docs` sur github] (https : //github.com/balderdashy/sails-docs) (Maître est parfois un peu en avance, mais toutes les mises à jour de documentation critiques le font sur le site dans un jour ou deux.)

Pour les anciennes versions de Sails qui sont encore largement utilisées, la documentation est compilée à partir des branches `sails-docs` pertinentes et hébergée sur les sous-domaines suivants:
+ [0.12.sailsjs.com] (http://0.12.sailsjs.com/)
+ [0.11.sailsjs.com] (http://0.11.sailsjs.com/)


### Comment je m'implique?

Il y a plusieurs façons de contribuer à Sails; Par exemple vous pouvez nous aider à améliorer la [documentation officielle] (https://github.com/balderdashy/sails-docs), écrire un [plugin] (http://sailsjs.com/documentation/concepts/extending-sails) , répondez à [StackOverflow questions] (http://stackoverflow.com/questions/tagged/sails.js), démarrez un meetup Sails, aidez à résoudre les problèmes GitHub, rédigez des tests ou envoyez un patch au core de Sails ou à l'une de ses dépendances . Veuillez consulter le [guide des contributions] (http://sailsjs.com/documentation/contributing) avant de commencer. C'est une courte lecture qui couvre les lignes directrices et les meilleures pratiques qui garantissent que votre travail acharné aura un impact maximal.


### Où puis-je soumettre des idées? Signaler des problèmes?

Le projet Sails suit les rapports de bogue dans les problèmes de GitHub et utilise les requêtes d'extraction pour les propositions de fonctionnalités. Veuillez lire le [guide des contributions] (http://sailsjs.com/documentation/contributing) avant de créer un problème, de soumettre une proposition ou de commencer à travailler sur une demande d'extraction.


### Quelle version de Sails dois-je utiliser?

[! [Version NPM] (https://badge.fury.io/js/sails.png)] (http://badge.fury.io/js/sails)

À moins que vous ne soyez un contributeur qui exécute une version préliminaire du framework afin de faire des tests ou de travailler sur core, vous devez utiliser la dernière version stable de Sails de NPM (cliquez sur le badge ci-dessus). L'installation est facile - il suffit de suivre [ces instructions] (http://sailsjs.com/get-started).

> Remarque: pour installer / mettre à niveau localement la dernière version de Sails dans un projet existant, exécutez `npm install sails @ latest --force`. Si vous rencontrez des problèmes et que vous cherchez un bazooka, vous pouvez aussi lancer `rm -rf node_modules && npm cache effacer && npm install sails @ latest --force && npm install`.

Si vous cherchez à installer une version préliminaire de Sails, vous pouvez installer à partir de la balise `beta` sur npm (c'est-à-dire` npm install sails @ beta`). C'est une excellente façon d'essayer une nouvelle version à l'avance et de commencer à la mettre à jour avant que la version ne devienne officielle. Le candidat à la version beta npm correspond à la branche `beta` du repo de Sails.

Enfin, si vous aimez vivre sur le fil du rasoir, ou si vous travaillez sur l'ajout d'une fonctionnalité ou la correction d'un bug dans Sails, installez la version edge à partir de la branche `master` sur github. La version edge n'est pas publiée sur le registre car elle est constamment en développement, mais vous pouvez toujours utiliser npm pour l'installer (par exemple `npm install sails @ git: // github.com / balderdashy / sails.git`)

Pour plus d'instructions sur l'installation des versions beta et edge de Sails, consultez le [guide des contributions] (http://sailsjs.com/documentation/contributing).


### J'ai du mal à installer Sails. Que devrais-je faire?

Commencez par le guide de dépannage utile de NPM (https://github.com/npm/npm/wiki/Troubleshooting). Si vous continuez à avoir des problèmes et que vous avez essayé la recherche Google, mais que vous êtes toujours perplexe, veuillez lire attentivement le guide de contribution Sails [http://sailsjs.com/documentation/contributing] mis à jour, puis créer un problème GitHub dans le repo de Sails.



### Quelles sont les dépendances de Sails?

[! [Statut de dépendance] (https://david-dm.org/balderdashy/sails.png)] (https://david-dm.org/balderdashy/sails)

Nous avons appris à plusieurs reprises au fil des ans à prendre très au sérieux le versionnement des dépendances. Nous verrouillons les versions de dépendances de Sails et ne modifions ces versions que si les mises à jour associées corrigent un problème de sécurité ou présentent d'autres avantages substantiels pour les utilisateurs de Sails (compatibilité, performances améliorées, etc.). , les performances ou les bogues de stabilité qui surviennent dans l'une de nos dépendances - indépendamment du fait que ces modules sont [officiellement maintenus par une autre entité ou non] (https://github.com/balderdashy/sails/pull/3235#issuecomment- 170417122).

Sails est testé avec les versions 0.10.x et supérieures de [node] (http://nodejs.org/) et repose sur les bases solides de [Express] (https://github.com/expressjs/) et [ Socket.io] (http://socket.io/). Hors de la boîte, il dépend également d'autres grands modules, comme `grunt`,` waterline`, et `fs-extra`. Cliquez sur le badge ci-dessus pour la liste complète des dépendances.


### Où puis-je obtenir de l'aide?

En dehors de la [page de support sur le site Web de Sails] (http://sailsjs.com/support), et entrez dans notre [ Salle de discussion Gitter] (https://gitter.im/balderdashy/sails). Si vous êtes perplexe, assurez-vous et [poser une question sur StackOverflow] (http://stackoverflow.com/questions/ask), où il y a une [communauté Sails active] (http://stackoverflow.com/questions/tagged / sailsjs? sort = latest & days = 30). Les membres de notre équipe principale ont récemment enseigné un [cours vidéo gratuit] (https://courses.platzi.com/courses/develop-apps-sails-js/) sur [Platzi] (http://platzi.com) et ont écrit [un livre] (https://www.manning.com/books/sails-js-in-action). Si vous êtes un membre du [Support Flagship] (http://sailsjs.com/flagship), vous pouvez soumettre un ticket [ici] (http://flagship.sailsjs.com/new-ticket).


### Qui d'autre utilise Sails.js?

> Sails est utilisé dans la production par des particuliers et des entreprises, des organismes à but non lucratif, et des entités gouvernementales dans le monde entier, pour toutes sortes de projets (greenfield et mature). Cette petite liste ne fait absolument pas autorité, donc si vous utilisez Sails dans votre application / produit / service, nous aimerions en entendre parler! Vous pouvez soumettre une demande d'extraction en mettant à jour cette liste [ici] (https://github.com/balderdashy/sails-docs/edit/1.0/FAQ.md). (Nous demandons simplement que vous respectiez l'ordre dans lequel les projets / entreprises ont été soumis, et ajoutez le vôtre à la fin de la liste.)

#### Entreprises / Organisations utilisant Sails:
+ [La ville de Paris] (http://paris.fr)
+ [18F (États-Unis)] (http://18f.gsa.gov/)
+ [Facteur] (http://www.getpostman.com/)
+ [BeyondSoft] (http://beyondsoft.com/)
+ [Le Broad Institute / Human Genome Project] (http://www.broadinstitute.org/)
+ [Insight Replay] (http://insightreplay.com) - Relecture instantanée pour [athlètes] (http://insightreplay.com/insight-replay-at-sochi-winter-olympics/) et entraîneurs
+ [Gamefroot] (http://gamefroot.com/)

#### Projets construits avec Sails:
+ [Cuckoo Quack] (http://www.cyber-duck.co.uk/blog/the-cuckoo-quack) - Une horloge antique transformée en un système de notification
+ [Portfolio Page] (http://isaac.levid.com/) - Par Isaac T. Wooten
+ [Taskboard] (http://tarlepp.github.io/Taskboard/) - une application Sails pour imiter le tableau de tâches "scrum-ban"


### Y a-t-il des options de support professionnel?

The Sails Company (les principaux mainteneurs du framework) propose des abonnements de support professionnels via Sails Flagship. Vous pouvez en savoir plus sur nos plans à l'adresse [sailsjs.com/flagship](http://sailsjs.com/flagship).


### Quels sont les bons tutoriels communautaires?

> Si vous êtes l'auteur d'un tutoriel ou d'un guide sur Sails, envoyez-nous une demande d'extraction [ici] (https://github.com/balderdashy/sails-docs/edit/1.0/FAQ.md) et nous Vérifiez-le. (Assurez-vous d'ajouter votre didacticiel en haut de la liste applicable, car nous essayons de les commander du plus récent au plus ancien.)

<! -
Une note rapide pour toute personne contribuant à ce fichier:

Tout d'abord, merci de faire un tutoriel! C'était plutôt cool de ta part.

Deuxièmement, lorsque vous ajoutez le tutoriel à l'une des listes ci-dessous, veuillez le suivre avec un commentaire indiquant la date à laquelle votre tutoriel a été mis à jour pour la dernière fois. (Nous essayons de garder les plus récents vers le haut de la liste.) Si vous faites un lien vers une série en cours que vous mettez à jour continuellement, ajoutez simplement la date de votre post le plus récent + l'expression '(séries en cours)' savoir pour continuer à vérifier.

Merci!
- @ rachaelshaw
->

##### Guides en plusieurs parties:
+ [Le guide du développeur JavaScript pour Sails.js] (https://www.ibm.com/developerworks/library/wa-build-deploy-web-app-sailsjs-1-bluemix/index.html) - 4 -part série d'IBM developerWorks. (Aussi disponible en [chinois] (http://www.ibm.com/developerworks/cn/web/wa-build-deploy-web-app-sailsjs-1-bluemix/) et [en japonais] (http: // www.ibm.com/developerworks/jp/web/library/wa-build-deploy-web-app-sailsjs-1-bluemix/).)
<! - 7-12-2016 ->
+ [SailsCasts] (http://irlnathan.github.io/sailscasts/) - Courts screencasts qui vous emmènent à travers les bases de la construction de sites Web traditionnels, d'applications mono-pages / mobiles, et d'API utilisant Sails. Parfait pour les développeurs débutants et débutants, mais suppose un peu d'expérience sur MVC.
<! - 4-4-2015 ->
+ [Canal de développement Sails.js sur Medium] (https://medium.com/sails-js-development/)
<! - 3-19-2015 ->
+ [Sails.js Cours sur Plurasight] (https://www.pluralsight.com/courses/two-tier-enterprise-app-api-development-angular-sails)
<! - 2-10-2015 ->
+ Sails Développement API
  + [Datalayer -modèles, connexions, ligne d'eau] (http://www.codeproject.com/Articles/898221/Sails-API-development-Datalayer-models-connections)
  + [Méthodes personnalisées, actions prioritaires par défaut et connexes] (http://www.codeproject.com/Articles/985730/Sails-API-development-2-2-Custom-methods-overriding-default)
<! - 5-5-2015 ->
+ Desarrollar Webapps en temps réel:
  + [Creación] (http://jorgecasar.github.io/blog/desarrollar-webapps-realtime-creacion/)
  + [Usuarios] (http://jorgecasar.github.io/blog/desarrollar-webapps-realtime-usuarios/)
  + [Auth] (http://jorgecasar.github.io/blog/desarrollar-webapps-realtime-auth/)
  + [Auth con Passport] (http://jorgecasar.github.io/blog/desarrollar-webapps-realtime-auth-con-passport/)
<! - 1-19-2014 ->


##### Articles et articles de blog:
+ [Twitter Dev Blog: Guest Post: Connexion Twitter avec Sails.js] (https://blog.twitter.com/2015/guest-post-twitter-sign-in-with-treelineio)
<! - 3-25-2015 ->
+ [Guest Post sur Segment.io Blog: Webhooks avec Slack, Segment, et Sails.js / Treeline] (https://segment.com/blog/segment-webhooks-slack/)
<! - 15/03/2015 ->
+ [Blog Postman: Gérez votre code d'amorçage du serveur Sails.js] (http://blog.getpostman.com/2015/08/28/manage-your-sailsjs-server-bootstrap-code/)
<! - 8-28-2015 ->
+ [Sails.js sur Heroku] (https://vort3x.me/sailsjs-heroku/)
<! - 5-19-2015 ->
+ [Angular + Sails.js (0.10.0-rc5) avec angular-sails socket.io] (https://github.com/maartendb/angular-sails-scrum-tutorial/blob/master/README.md)
<! - 4-14-2014 ->
+ [Angulaire + Voiles! Aide!] (Https://github.com/xdissent/spinnaker) - Sails Ressources Service pour AngularJS
<! - 8-19-2013 ->
+ [Comment créer une application Node.js en utilisant Sails.js sur un VPS Ubuntu] (https://www.digitalocean.com/community/articles/how-to-create-an-node-js-app-using- sails-js-on-an-ubuntu-vps)
<! - 7-16-2013 ->
+ [Travailler avec des données dans Sails.js] (http://net.tutsplus.com/tutorials/javascript-ajax/working-with-data-in-sails-js/) tutoriel sur NetTuts
<! - 6-12-2013 ->

##### Tutoriels vidéos:
+ [Jorge Casar: Introduccion a Sails.js] (https://www.youtube.com/watch?v=7_zUNTtXtcg)
<! - 12-17-2014 ->
+ [Sails.js - Comment afficher les vues des noeuds via Ajax, une seule page, SPA] (http://www.youtube.com/watch?v=Di50_eHqI7I&feature=youtu.be)
<! - 29/08/2013 ->
+ [Intro to Sails.js] (https://www.youtube.com/watch?v=GK-tFvpIR7c) [@mikermcneil] (https://github.com/mikermcneil) screencast original
<! - 2-25-2013 ->

### Comment puis-je convaincre les autres filles / gars de mon équipe?

##### Articles / interviews / communiqués de presse / whitepapers / talks

> + Si vous êtes l'auteur d'un article sur Sails, envoyez-nous une demande d'extraction [ici] (https://github.com/balderdashy/sails-docs/edit/1.0/FAQ.md). Nous allons vérifier!
> + Si vous êtes une entreprise intéressée à faire un communiqué de presse sur Sails, merci de contacter @mikermcneil sur Twitter (et de lui rappeler si nécessaire!) Nous ferons tout ce qui est en notre pouvoir pour vous aider.

+ [Microsoft Case Study: Déploiement de Sails.js sur Azure Web Apps] (https://blogs.msdn.microsoft.com/partnercatalystteam/2015/07/16/y-combinator-collaboration-deploying-sailsjs-to-azure- web-apps /)
+ [InfoWorld: Pourquoi Node.js bat Java et .Net pour les applications web, mobiles et IoT] (http://www.infoworld.com/article/2975233/javascript/why-node-js-beats-java-net -for-web-mobile-iot-apps.html) _ (La rapidité, l'évolutivité, la productivité et la politique des développeurs ont tous joué un rôle dans la sélection de Sails.js / Node [AnyPresence] (http://anypresence.com) .js pour sa plate-forme de développement d'entreprise) _
+ [Anypresence & Node.js] (http://www.anypresence.com/blog/2015/03/06/anypresence-nodejs/)
+ [TechCrunch: Sails.js Financé par Y-Combinator] (http://techcrunch.com/2015/03/11/treeline-veut-demander-la-coding-out-of-building-a-backend/ )
+ [TechRepublic: Construire des applications robustes avec le framework MVC Node.js] (http://www.techrepublic.com/article/build-robust-node-applications-with-the-sails-js-mvc-framework/)
+ [L'interview de Mike avec @freddier et @cvander de Platzi] (https://www.youtube.com/watch?v=WN0YgPdPbRE)
+ [Magazine Smashing: Voile avec Sails.js] (https://www.smashingmagazine.com/2015/11/sailing-sails-js-mvc-style-framework-node-js/)
+ [Présentation à Smart City Conference & Expo 2015] (http://www.goodxense.com/blog/post/our-presentation-at-smart-city-conference-expo-2015/) (George Lu & YJ Yang)
+ Sails.js, Treeline et l'avenir de la programmation ([Article] (https://courses.platzi.com/blog/sails-js-creator-mike-mcneil-on-treeline-and-frameworks/) | ] (https://www.youtube.com/watch?v=nZKG7hLhbRs) | [Deck] (https://speakerdeck.com/mikermcneil/what-even-is-software))
+ [Entretien radio avec Mike McNeil avec Craig Crossman de ComputerAmerica] (https://www.youtube.com/watch?v=ERIvf2iUj5U&feature=youtu.be)
+ [Conception et développement de l'API UI-First: les API I d'Apigee, San Francisco, 2015] (https://speakerdeck.com/mikermcneil/i-love-apis)
+ [Choisir le bon framework pour le développement de Node.js] (https://jaxenter.com/choosing-the-right-framework-for-node-js-development-126432.html)
+ [TechCrunch: Nos 10 entreprises préférées de Y Combinator Demo Day] (https://techcrunch.com/gallery/our-10-favorite-companies-from-y-combinator-demo-day-day-1/slide/11 /)
+ [Sails.js utilisé sur le site de la ville de Paris] (https://twitter.com/parisnumerique/status/617999231182176256)
+ [Tirer le bouchon: dotJS (Paris, 2014)] (http://www.thedotpost.com/2014/11/mike-mcneil-pulling-the-plug)
+ [De Rags à Open Source] (https://speakerdeck.com/mikermcneil/all-things-open) (All Things Open, Raleigh, 2014)
+ Conférence SxSW, Austin, TX: ([2014] (https://speakerdeck.com/mikermcneil/2014-intro-to-sails-v0-dot-10-dot-x) | [2015] (https: // speakerdeck.com/mikermcneil/sxsw-2015))
+ [Plus de discussions par Mike et l'équipe de base de Sails.js] (http://lanyrd.com/profile/mikermcneil/)
+ [Web de Dessarolo: Interview w / Mike McNeil] (https://www.youtube.com/watch?v=XMpf44oV2Og) (Espagnol et anglais - anglais commence à 1:30)
+ [CapitalOne blog: Contrastant Enterprise Node.js Frameworks] (http://www.capitalone.io/blog/contrasting-enterprise-nodejs-frameworks/) (par [Azat Mardan] (https://www.linkedin.com / in / azatm), auteur du livre "Pro Express.js")
+ [Alternatives à MongoDB (article chinois)] (http://www.infoq.com/cn/news/2015/07/never-ever-mongodb)
+ [Introduction à Sails.js un cadre pour la création d'applications en temps réel] (https://abalozz.es/introduccion-a-sails-js-un-framework-para-crear-aplicaciones-realtime/)
+ [Démarrage Austin trouve le succès dans la conception sensible] (http://www.bizjournals.com/sanantonio/blog/socialmadness/2013/03/sxsw-2013-Balderdash-startup-web-app.html?ana=twt)
+ [Interact ATX] (http://www.siliconhillsnews.com/2013/03/10/flying-high-with-interact-atx-adventures-in-austin-part-3-2-1/)
+ [Introduction à Sails.js :: Node.js Conf: Italie, 2014] (http://2014.nodejsconf.it/)
+ [Startup America] (http://www.prlog.org/12038372-engine-pitches-startup-america-board-of-directors.html)
+ [tweets récents À propos Sails.js] (https://twitter.com/search?f=realtime&q=treelinehq%20OR%20%40treelinehq%20OR%20%23treelinehq%20OR%20%23treeline%20OR%20treeline.io% 20ou% 20sailsjs.com% 20ou% 20github.com% 2Fbalderdashy% 2Fsails% 20ou% 20sailsjs% 20ou% 20sails.js% 20ou% 20% 23sailsjs% 20ou% 20% 40sailsjs & src = TYPD)
Général + [Comment utiliser une source plus ouverte] (https://18f.gsa.gov/2014/11/26/how-to-use-more-open-source/) _ (18F est un bureau à l'intérieur des services nous Administration qui aide les autres agences fédérales à créer, acheter et partager des services numériques efficaces et faciles à utiliser.) _
+ [18F Open Source série Hack: Midas] (https://18f.gsa.gov/2014/10/01/open-source-hack-series-midas/)
+ (https://adtmag.com/articles/2016/02/11/express-joins-node.aspx) [Web express Les progrès du serveur dans Node.js des écosystèmes] ([auch auf Deutsch] (http: // www. heise.de/developer/meldung/IBM-uebergibt-JavaScript-Webframework-Express-an-Node-js-Foundation-3099223.html))
+ Interview avec Tim Heckel [sur InfoQ] (http://www.infoq.com/news/2013/04/Sails-0.8.9-Released)
+ [Sails.js - Une architecture MVC applications verser en temps réel Node.js] (http://www.lafermeduweb.net/billet/sails-js-une-architecture-mvc-pour-applications-real-time-node -js-1528.html)
+ [Nouvelles Hacker] (https://news.ycombinator.com/item?id=5373342)
+ [Introduction à Sails.js :: Node PDX, Portland, 2013 (Diapositives)] (http://www.slideshare.net/michaelrmcneil/node-pdx))
+ [Sail.js: un cadre MVC pour Node.js] (http://javascript.developpez.com/actu/52729/Sail-js-un-framework-MVC-pour-Node-js/)
+ [Construire Custom & Enterprise Node.js Apps avec Sails.js] (http://www.webappers.com/2013/03/29/build-custom-enterprise-node-js-apps-with-sails-js/ )
+ [Nouveaux outils pour la conception et le développement web: Mars 2013] (http://www.creativebloq.com/design-tools/new-tools-web-design-and-development-march-2013-4132972)
+ [Voiles 0.8.9: Un cadre MVC en temps réel inspiré de Rails] (http://www.infoq.com/news/2013/04/Sails-0.8.9-Released)
+ [Node.js の MVC ク レ ー ワ ー ク Sails.js が 良 げ な し て て た (] (http://nantokaworks.com/?p=1101)
+ [InfoWorld: 13 frameworks fabuleux pour Node.js] (http://www.infoworld.com/article/3064653/application-development/13-fabulous-frameworks-for-nodejs.html#slide9)
+ [Nouveaux outils de conception de sites Web que vous devez consulter] (http://www.designyourway.net/blog/resources/new-web-design-tools-that-you-need-to-check-out/)
+ [Live code Sails.js avec Mike McNeil] (http://www.weezevent.com/live-code-sailsjs-avec-mike-mcneil)
+ [# hack4good ajoute des villes et accueille le créateur de Sails.js pour parler et pirater à Paris!] (http://us2.campaign-archive1.com/?u=cf9af451f2674767755b02b35&id=fb98713f48&e=b2d87b15fe)


