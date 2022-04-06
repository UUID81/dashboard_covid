# dashboard_covid
Un tableau de bord pour la COVID
Installation d'Ubuntu 20.04 LTS
projectvax
+-- test.py
+-- .devcontainer
    +-- devcontainer.json
    +-- docker-compose.yml
    +-- Dockerfile
Créer un dossier `mkdir projectvax` et un dossier 'mkdir .devcontainer'
Puis rentrer dans le dossier: `cd projectvax`
Et enfin nous avons ouvert VS Code avec `code .`

Nous avons créé 4 fichier:

 - fichier python `test.py` -> ouvrir la connection avec MySQL
 - fichier `Dockerfile` -> paramètrer le code
 - fichier `docker-compose.yml` -> Créer les containers dans Docker et fait le lien entre la bdd et grafana
 - fichier `devcontainer.json` -> Echange de données

Les trois derniers fichiers ce trouve dans le dossier `.devcontainer`

Télécharger sur VS Code l'extension `VS Code Remote-Containers extension`
Il permet de créer les containers dans Docker.
Nous allons par la suite chercher cette extension dans une ` Command Palette` en tapant Ctr + Shift + p
Et ouvrir `Remote-Containers: Open Folder in Container ...`
Cela nous envoi nos dossier dans un Workspace du nom de `Dev Container: Develop Python`

Nous ouvrons MySQL avec un `localhost:8080` et nous connectons avec les données fournies dans `test.py`
On import le fichier `vaccination.sql`
Après cela nous pouvons ouvrir Grafana grâce au lien `localhost:3000`
Nous nous connectons, faisons le lien avec la bdd depuis `DATA Sources`

Pour finir nous avons fait deux graphiques avec le dashboard.

Voici les graphiques avec leur requêtes:

SELECT sum(people_fully_vaccinated), country FROM country_vaccinations GROUP BY country having sum(people_fully_vaccinated);

![grapfcarte](https://user-images.githubusercontent.com/90393606/161998881-386f10fa-da11-47fb-a0f2-cf4819aa37a6.PNG)

SELECT people_vaccinated, country FROM country_vaccinations
WHERE country = 'France';








