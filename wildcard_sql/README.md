# Installation Application At Home

Si vous souhaitez installer l'application sur votre serveur pour continuer le TP il faut suivre les indications suivantes : 


Prérequis : 
 - Avoir un Serveur Web Apache2/Nginx/Httpd
 - Avoir une base de donnée (mysql)
 - Avoir PHP installé

# Installation de l'application PHP

Prendre les fichiers PHP (`index.php` et `user.php`) et les déposer à l'endroit où votre serveur Web va aller lire. Pour du linux il s'agit de `/var/www/html/` par défaut.

Les fichiers doivent être lisibles par l'utilisateur de le groupe `www-data` : 
```bash
chown -R www-data: /var/www/html 
```

**Pensez à reloader votre serveur Web a chaque modification des fichier** : `systemctl apache2 reload`

# Installation de la Base de Données

Une fois votre base de données installé (mysql par exemple), il faut : 

- créer une base de donnée qui s'appelle : `db`
- Pouvoir se connecter dessus en tant qu'utilisateur `root` et **sans mot de passe**
- Avec le fichier `dump.sql` importer les éléments de la base de donées : `mysql -u root  db < file.sql`
  - Sinon vous pouvez la créer à la main : 
 
| username | password        |
|----------|-----------------|
| admin    | v^Xf4MtShR#74eB |  


# Accéder à l'application

Une fois votre application lancée, vous pouvez y accéder depuis votre navigateur sur l'adresse : `http://localhost` vous devriez avoir le formulaire
