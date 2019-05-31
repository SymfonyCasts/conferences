# Développement d'applications TDD avec Symfony et ses amis en situation réelle (Chris Holland)

***TIP
Symfony Live Paris 2019 presentation by [Chris Holland](https://connect.symfony.com/api/alternates/c6747465-e45e-4e9d-96c8-a4fff2460516).
This talk is in French and (sorry!) no transcript is available.
***

## Talk Abstract

Démarrer Symfony avec REST, OAuth, gestion des utilisateurs, tests d'acceptation et tests unitaires.
Mise en place de Doctrine avec PHPUnit, pour permettre un workflow TDD hautement productif.

* Tester ses classes Repository avec des opérations réelles sur les données tout en conservant une vitesse fulgurante.
* Tester ses Entity dans le cadre de ce processus, tout en ne créant pas un schéma de base de données sur notre instance MySQL locale.
* Laisser Doctrine générer toutes les migrations MySQL pour synchroniser le schéma avec nos entités.
* 

Également :

* Support API/REST via FOSRestBundle
* Support OAuth via FOSOAuthServerBundle
* Gestion des utilisateurs via FOSUserBundle
* 

Optimisations de la configuration pour optimiser la performance sur les tests unitaires lors de l'introduction de ces frameworks.
Utilisation de Codeception pour tester la création des Controller, avec des tests de bout en bout sur le serveur web, en utilisant notre MySQL local.

