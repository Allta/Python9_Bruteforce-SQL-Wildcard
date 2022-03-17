# https://classroom.github.com/a/uvuFpNYB

# TP BruteForce Password - Ynov Python B1

### Tips   

:raising_hand: Si vous avez des soucis n'hésitez pas à m'appeler. 
 
## Exercice 1 : Password Generator
 
Dans un programme python créer une fonction qui permet de générer un mot de passe aléatoire.

Il faudra utiliser la librairie `random` comme pour le TP Guess the Number. 

Pour générer une liste de caractère à utiliser vous pouvez soit créer une variable possédant tous les caractères : 

```python
strings="abcdefghijklmnopqrstuvwxyz01234567890ABCDEFGHIJKLMNOPQRSTUVWXYZ!@#$%^&*()?"
 ```
 
 Ou alors vous pouvez utiliser la librairie `strings` : 
 
 ```python 
 import string

strings = string.ascii_letters + string.digits + "_@{}-/()!\"$%=^[]:;"
chars = string.printable[:-5]
```


 
## Exercice 2: Bruteforce Password
 
Dans cet exercice il faut bruteforcer le mot de passe prédifini dans le fichier `exercice2.py`

Vous allez devoir utiliser la librairie `requests`. 

Documentation : https://docs.python-requests.org/en/latest/ 

Les fonctions sont déjà nommées avec le nombre d'arguments à utiliser. 
Il faut compléter les fonctions pour pouvoir executer le programme. 


## Exercice 3 : Wifi Password stealing

Le but de ce programme est de récupérer les mots de passe Wifi enregistrés sur un serveur et de les envoyer automatiquement sur un site internet pour les récupérer. 

Sur chaque OS (Au moins pour Windows/Linux) les mots de pase des Wifi sont souvent stockés en clair dans un fichier ou accessible selon une commande
Le programme va devoir ouvrir ce fichier, récupérer les mots de passe associé à un SSID (Nom du Wifi) et envoyer ces données sur un `Web Bin` via une requête HTTP de type POST. 

Un WebBin ou RequestBin est un "attrape requête". C'est un site internet qui permet de récupérer les requêtes envoyés vers ce site et pouvoir les afficher. 

Vous pouvez utiliser ce site : https://requestbin.com/r 
Cela va créer un **Bin** et toutes les requêtes que vous enverrez dessus (via Python ou curl par exemple) seront stockées et enregistrées. 
Ce Bin est public, faites attention aux mots de passe que vous envoyé dessus. Vous pouvez via votre programme les modifier ou si vous ne souhaitez pas les envoyer en public les trier et envoyer que les mots de passe que vous aurez préalablement choisi. 


Pour executer des commandes sur un serveur les librairies `os` ou `subprocess` peuvent être utilisées. 
Explication : https://stackoverflow.com/questions/14894993/running-windows-shell-commands-with-python 

### Windows : 

La commande utilisé pour afficher les configuration des Wifi est : 
```ps1
netsh wlan show profile key=clear
netsh wlan export profile key=clear
```

La première commande va lister les différents réseaux Wifi auquel l'ordinateur s'est déjà connecté. 
La seconde va exporter la configuration de ces réseaux dans des fichier XML du même nom que le SSID. 

  
### Linux : 

Pour les personnes étant sur un Linux natif (pas en VM).
Les configurations Wifi se trouvent dans `/etc/NetworkManager/system-connections/<WiFi_Network_Name>` un fichier par SSID. La clef du Wifi se trouvera dans le champ `psk`

Se fichier est uniquement accessible en **root**. 

**Si vous êtes sur une VM, vous pouvez copier les 2 fichiers BBox et EduWifi dans le dossier /etc/NetworkManager/system-connections/ pour continuer de travailler sur Linux** 

 
