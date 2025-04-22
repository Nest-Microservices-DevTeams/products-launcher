## Dev

1. Cloner le referentiel
2. Creer un fichier `.env` basé `.env.template`
3. Exécuter la commande `docker compose up --build`

### Étapes pour créer des sous-modules Git

1. créer un nouveau dépôt sur GitHub
2. Cloner le dépôt sur la machine locale.
3. Ajouter le sous-module, où `repository_url` est l'url du dépôt et `directory_name` est le nom du dossier où vous voulez que le sous-module soit stocké (il ne doit pas exister dans le projet)

```
git submodule add <repository_url> <directory_name>
```

4. Ajouter des modifications au dépôt (git add, git commit, git push)
   Ex :

```
git add .
git commit -m « Ajouter un sous-module »
git push
```

5. Initialiser et mettre à jour les sous-modules, lorsque quelqu'un clone le dépôt pour la première fois, il doit exécuter la commande suivante pour initialiser et mettre à jour les sous-modules

```
git submodule update --init --recursive
```

6. Pour mettre à jour les références des sous-modules

```
git submodule update --remote
```

## Important

Si vous travaillez dans le dépôt qui contient les sous-modules, **mettez d'abord à jour et poussez** le sous-module et **ensuite** le dépôt principal.

Si vous faites l'inverse, vous perdrez les références aux sous-modules dans le dépôt principal et devrez résoudre les conflits.
