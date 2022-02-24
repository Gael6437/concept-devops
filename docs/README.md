# Echanges DevOps


## Présentation

- 30% de méthodes de travail & bonnes pratiques
- 60% d'outils (Kubernetes, Terraform,...)
- 10% de bricolage pour relier ces outils au mieux

Si on fait trop de bricolage, c'est probablement que l'on n'utilise pas les bons outils.

TODO : Schéma INFINI 

## Echanges de données bas niveau 

| SSH | HTTPS | SOCKETS |
| - | - | - |
| - clé privée/publique | - URL | - fichier |
| - protocole de sécurité | - user / mdp / token | - pile / FIFO / LIPO |
| - mdp | - certificat SSL | - droits |


## SCALABILITE

### Monolithe

TODO : Schéma

- Duplication du monolithe
- Répartition du flux dans les instances du monolithe par le loadbalancer
- Utilisation d'un cache pour conserver le contexte / la session
- Database peu scalable ou duplicable


### N-tiers

TODO : Schéma

- Duplication du front 
- Duplication du back
- Pas possible d'associer un back avec chaque front !
- Loadbalancer entre : 
    - entrée du flux (F5) et les instances du Front
    - les instances du Front et les instances du Back
- Possibilité de scaler la base de donnée

### Database
TODO : Schéma

- utilisation d'un loadbalancer qui réparti en fonction des requêtes : écriture ou lecture
- une db master unique destinée à l'écriture 
- des db slave mutiples qui sont des réplications de la db master et qui sont réservées aux queries de lecture.

### Microservices

TODO : Schéma

Avantages: 
- chaque microservice possède sa propre database (plus petites donc moins honéreuses)
- possibilité de scaler chaque microservice en fonction des besoins 

Inconvénients: 
- Augmentation importante des requêtes entre les microservices pour une requête de base

Solution ->  utilisation d'un bus de message : file d'attente
- chaque service traite le message contenu dans le BUS, si et seulement si, il lui est destiné.
- permet une réponse asynchrone : évite les aller/retour et pas de perte de données 
- principalement utilisé pour le Back ( couplé à une architecture monolithique ou N-tiers pour le Front )

## GIT 

### Sécurisation du repo 

### Mise en place CI 

### Commandes Git à maîtriser

## 12 factors 


## UNIX 

### Les commandes de base
| Commande| Options | Utilisation |
|- |- |- |
| ps | -aux | Liste l'ensemble des processus en cours |
|ls || liste les fichiers du répertoire courant |
|| -a <br/> -l | affiche les fichiers cachés <br/> affichage en liste détaillée |
|df||affiche les partitions|
||-i|affiche l'utilisations des inodes|
|du||affiche l'utilisation disque|
||-h|améliore l'affichage des valeurs|
||--max-depth=1|ne prend en compte que le premier niveau d'arborescence|
|cat *\<fichier\>*||lit le fichier|
|echo *\<string\>*||Envoi la string sur la sortie standard|
|grep *\<string\>*||recherche de texte|
||-i<br/> -A*x* <br/> -B*x*|-ignore la casse<br/> Ajoute les x lignes après le résultat <br/> Ajoute les x lignes avant le résultat |
| *\<comm. A\>* **\|** *\<comm. B\>*|| Envoie la sortie standard de A à l'entrée standard de B|
|more *\<fichier\>*|||
|less *\<fichier\>*|||
|tail *\<fichier\>* ||Lecture de la fin d'un fichier|
||-f|(follow) permet d'afficher le fichier lorsqu'il accepte de nouvelles lignes|
|chmod [options]||permet de modifier les droits d'un fichier|
|env|| affiche les variables d'environnements (dont le PATH)|
|which *\<commande\>*||affiche l'emplacement d'une commande|
|find *\<contexte\>* *\<fichier\>* ||affiche l'emplacement d'un fichier|
|id||indique la session en cours|
|groups||indique les groupes auxquels on appartient|
|sudo su -||passe en mode root|
|top||affiche les processus actifs en fonction de leur utilisation du CPU|






## Lexique

- **loadbalancer** : technologie qui prend en entrée un flux qu'il redistribue en fonction d'un algorithme (randoming, ...)
- **F5** : c'est le point d'entrée du flux dans le système informatique 