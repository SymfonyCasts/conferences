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

<!-- Todo -->
