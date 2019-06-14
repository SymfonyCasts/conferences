# Lightning Talks

***TIP
Symfony Live Paris 2019 lightning talks by various authors.
This talk is in French and (sorry!) no transcript is available.
***

## Les side-projects, c'est cool ! ([@pierstoval](https://github.com/pierstoval))

_Timecode: [00:00](?playAt=0)_ 

Les _side-projects_, ce sont ces petits projets personnels que l'on fait quand on a du temps libre, en dehors de notre travail.

Parfois, on trouve des idées révolutionnaires, parfois pas.

Il n'y a pas de règles, c'est nous qui les fixons !

Pas de deadline, pas de chef de projet, pas de client, et une liberté totale sur le choix des technos à utiliser !

## Retour critique sur les PSR ([@jeremyFreeAgent](https://github.com/jeremyFreeAgent))

_Timecode: [05:32](?playAt=332)_ 

Depuis l'arrivée du composant HttpClient de Symfony, j'aime l'idée de n'avoir aucune dépendance. Et aucune PSR.

PSR _était_ un très bon moyen de créer un terrain commun pour PHP, pour une _interopérabilité_ ([@fabpot](https://github.com/fabpot)).

Certaines PSR sont très utiles: PSR-0 & PSR-4 (autoload), PSR-1 & PSR-2 (coding style), PSR-7 & PSR-18 (HTTP Message/Client).

PSR = PHP Standard Recommendation. Il y a ici une injonction paradoxale : "standard" et "recommendation".

Les PSR sont immuables, et ne peuvent pas évoluer. PSR-7, dernier commit le 6 août 2016, il y a 3 ans (au moment de la conférence), et le standard ne peut plus évoluer.

`symfony/contracts` est un nouveau _package_ permettant de faire évoluer les propositions de Symfony.

Il faut améliorer la DX pour que les devs prennent du plaisir à coder.

## Supprimer du code mort ([@ValentineBoineau](https://github.com/ValentineBoineau))

_Timecode: [13:00](?playAt=780)_ 

Supprimer du code, parfois une nécessité, mais on a souvent peur de "tout casser".

PHP étant dynamique et pas 100% strict, peut-on trouver une solution pour supprimer du code sans risque ?

L'AST de PHP permet de modéliser le code, chaque élément étant un objet typé, et les analyseurs actuels utilisent ce graphe pour détecter d'éventuelles erreurs de compilation.

Et du coup, nous sommes en train de travailler sur le `Symfony Checker`, outil d'analyse statique et dynamique qui va vous permettre de détecter le code mort ou incorrect. 

## Git en 7 minutes ([@alxmhe](https://github.com/alxmhe))

_Timecode: [17:46](?playAt=1066)_

« Git, c'est comme les _24 heures du Mans_, et il ne faut pas manquer le _checkpoint_. »

Qu'est-ce qu'un commit ? Merge vs rebase ?

Quelques explications sur le fonctionnement de Git.

## Sonata Admin vs EasyAdmin ([@tony-tran](https://github.com/tony-tran)) 

_Timecode: [25:12](?playAt=1512)_

Ces deux bundles permettent de créer un CRUD dans un backoffice.

Les différences entre les deux bundles ne sont peut-être pas intuitives pour les personnes qui ne les connaissent pas.

À partir d'un exemple simple de classes `Publication` et `Category`, et leur relation, nous voyons ensemble les avantages et inconvénients de chacun.

Résumé : 

* Sonata:
  * Il faut créer des classes `Admin`, à déclarer comme services dans le _container_ avec certaines options et être tagués.
  * Chaque classe `Admin`, en PHP donc, permet de configurer les formulaires, la liste des objets, les critères de recherche, etc.
  * La configuration des classes `Admin` est assez exhaustive, mais permet de faire beaucoup de personnalisation
* EasyAdmin
  * La config est en Yaml, pas de classes `Admin`
  * Autocomplete pour les relations et les `ChoiceType`
  * Chaque entité peut avoir son propre contrôleur

## Symfony CLI ([@tucksaun](https://github.com/tucksaun))

_Timecode: [33:03](?playAt=1983)_

`symfony` est un binaire installable en local, unique, développé en Go, qui permet de fournir beaucoup de fonctionnalités :

* Compatible tout OS
* Pas de dépendances
* Comme la console Symfony (helpers, etc.)
* Serveur web local natif, dédié au développement
* TLS natif avec Let's Encrypt
* Peut utiliser `php-fpm`, `php-cgi` ou `php -S ...`
* Peut utiliser plusieurs versions de PHP auto-détectées selon l'OS
* Compatible HTTP/2
* Noms de domaines locaux avec un proxy HTTP et DNS local
* Compatible `docker-compose`
* Intégration native avec SymfonyCloud
* Logs formatés
* Workers, daemons...
* Et tant d'autres !

## Go beyond composer update: Contribute! ([@nicolas-grekas](https://github.com/nicolas-grekas))

_Timecode: [40:40](?playAt=2440)_

Si vous n'avez jamais contribué à Symfony, voici le guide ultime pour savoir comment faire.

Il n'est jamais trop tard pour contribuer !
