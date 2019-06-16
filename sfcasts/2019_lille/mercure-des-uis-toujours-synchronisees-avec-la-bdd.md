# Mercure : des UIs toujours synchronisées avec la BDD (Kévin Dunglas)

***TIP
Symfony Live Lille 2019 presentation by [Kévin Dunglas](https://connect.symfony.com/profile/dunglas). This talk is in French and (sorry!)
no transcript is available.
***

## Talk Abstract

Et si l’UI de vos sites web ou vos apps mobiles se mettaitent à jour en temps réel dès qu’une donnée affichée (prix, disponibilités, commentaires…) est modifiée dans le système de persistence ? Mercure permet aux serveurs de "pousser" des mises à jour en temps réel à tous types de clients.

Mercure est auto-découvrable, conçu dès le départ pour être utilisé avec des API hypermedia ou GraphQL, dispose d’un mécanisme d’autorisation qui permet de ne publier certaines mises jour qu’à certains clients autorisés, permet aux clients de se reconnecter automatiquement s'ils perdent puis retrouvent une connection, ré-envoie les messages qui se seraient perdus.

Après avoir découvert le protocole, verrons comment :

* installer un serveur Mercure
* découvrir le serveur côté client
* s’abonner à des mises à jour
* publier des mises à jour avec Symfony et API Platform (qui disposent déjà du support officiel du protocole)
* mettre à jour des apps React avec les données envoyées par Mercure

