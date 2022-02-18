# Echanges DevOps


## Présentation

- 30% de méthodes de travail & bonnes pratiques
- 60% d'outils (Kubernetes, Terraform,...)
- 10% de bricolage pour relier ces outils au mieux


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
### N-tiers
TODO : Schéma
### Database
TODO : Schéma
### Microservices
TODO : Schéma
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
| *A* **\|** *B* || Envoie la sortie standard de A à l'entrée standard de B|
||*A* *\|* *B* **-**|lorsque la commande B ne prend pas d'entrée standard|
|more *\<fichier\>*|||
|less *\<fichier\>*|||
|tail *\<fichier\>* ||Lecture de la fin d'un fichier|
||-f|(follow) permet d'afficher le fichier lorsqu'il accepte de nouvelles lignes|
|chmod [options]||permet de modifier les droits d'un fichier|
|env|| affiche les variables d'environnements (dont le PATH)|
|which *\<commande\>*||affiche l'emplacement d'une commande|
|find *\<fichier\>* ||affiche l'emplacement d'un fichier|
||||
||||
||||
