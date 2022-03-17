# https://classroom.github.com/a/2kkaiNQn

# TP BruteForce SQL Wildward - Ynov Python B1


### Tips   

:raising_hand: Si vous avez des soucis n'hésitez pas à m'appeler. 
 
## Exercice 1 : Bruteforce SQL Wildcard

L'objectif de cet exerice est de trouver le mot de passe de l'utilisateur **admin**. 
Pour cela il va falloir exploiter une faille dans le code PHP de l'application. 

L'application sert à authentifier les personnes pour qu'elles puissent accéder sur le site. 
Pour ça il faut rentrer son username et son mot de passe. Par défaut vous avez trouver que le username était **admin**. 

La vulnérabilité se trouve ici : 

![image](https://user-images.githubusercontent.com/51991304/158778405-627896d3-f966-40bd-8afe-ef043949106f.png)

En effet, le mot clef **LIKE** en SQL permet d'utiliser des *wilcard* pour compléter un champ. 
Les wildcard permettent de remplacer n'importe quel caractère, en SQL elles s'écrivent avec cette syntaxe : 

```sql
SELECT user FROM users WHERE user LIKE 'Fra%';
```

Le signe **%** permet de selectionner tout les users commençant par **Fra**. 

Il faudra donc créer un programme Python qui puisse envoyer des requête HTTP en complétant le champ password dynamiquement avec l'utilisation des wildcard. 

L'application sera hébergée sur le réseau Ynov et l'addresse vous sera donnée au début du TP. 
