# Mode d'emploi

Ce setup contient :
- un serveur PHP accessible par défaut sur `http://localhost:80`
- un PhpMyAdmin accessible sur `http://localhost:8080`
- une base de données MariaDB

1. Lancez Docker Desktop sur votre poste
2. Clonez ce repo sur votre poste **ATTENTION : Docker a besoin d'être sur le disque local du poste. Ne copiez pas ce dossier sur une clé ou sur un dossier du réseau sinon les volumes ne fonctionneront pas**
3. Ouvrez un terminal dans le dossier où se trouve le `docker-compose.yml` et lancez la commande `docker compose up`
4. Dans le dossier `src`, vous placerez vos fichiers `.php`. La racine de `src` correspond à la racine de votre serveur.
5. Le dossier `data` contient votre base de données. Si vous l'altérez vous perdrez vos données !.

## Modifier le port du serveur PHP
Ouvrez le `docker-compose.yml` et modifiez la partie gauche de la propriété `services.php.ports`. Après les `:`, cela devra toujours être `80`, mais si vous voulez accéder à votre serveur sur `localhost:8080` par exemple, vous pouvez mettre `8080:80`.
Redémarrez le serveur avec `docker compose up`.

## Modifier les mots de passe ou le nom de la BDD
Modifiez le fichier `.env` en fonction de ce que vous voulez, faites ensuite :
- `docker compose down` pour stopper et supprimer les containers
- `docker compose up` pour recréer les containers et prendre en compte les modifications