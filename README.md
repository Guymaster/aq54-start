# AQ54 START

Ceci est un dépôt mère permettant de configurer et de lancer plus facilement les codes du [Frontend](https://github.com/Guymaster/aq54), du [Backend](https://github.com/Guymaster/aq54-backend) et la base de données.

Vous pouvez trouver une version de l'application hébergée à cette addresse : https://aq54.onrender.com

Le tout représente un service permettant de consulter les historiques de mesures de plusieurs capteurs placés à Abidjan.

Tech Stack :
- NestJS, Prisma et PostgreSQL pour le Backend
- ReactJS et Mapbox pour le frontend
- Firebase Auth et Firebase Admin pour l'authentification

## Comment exécuter (Docker-compose) ?

Commencez par cloner ce dépot en ouvrant un terminal pour y entrer la ligne suivante :

```
git clone https://github.com/Guymaster/aq54-start.git
```

Ouvrez un terminal dans le nouveau dossier **aq54-star**t et entrez :

```
git submodule update --remote aq54
```

```
git submodule update --remote aq54-backend
```

Dans le dossier **aq54-start**, créez un fichier environnement nommé `.env`. Vous devez y renseigner les variables d'environnement de la manière suivante :

```
FRONTEND_LISTEN_PORT=3000
API_LISTEN_PORT=5000

# Mapbbox
MAPBOX_TOKEN=<Token Mapbox>

# Firebase client
FB_API_KEY=<Api key Firebase>
FB_AUTH_DOMAIN=<Auth domain Firebase>
FB_PROJECT_ID=<Project ID Firebase>
FB_STORAGE_BUCKET=<Storage bucket Firebase>
FB_MESSAGING_SENDER_ID=<Messaging sender Firebase>
FB_APP_ID=<App ID Firebase>
FB_MEASUREMENT_ID=<Measurement ID Firebase>

# Firebase admin
FB_ACCOUNT_TYPE=<Type de compte Firebase>
FB_PROJECT_ID=<ID projet Firebase>
FB_PRIVATE_KEY_ID=<ID clé privée Firebase>
FB_PRIVATE_KEY=<Clé privée Firebase>
FB_CLIENT_EMAIL=<Email client Firebase>
FB_CLIENT_ID=<Id client Firebase>
FB_AUTH_URI=<Auth uri Firebase>
FB_TOKEN_URI=<Token uri Firebase>
FB_AUTH_PROVIDER_X509=<Auth provider Firebase>
FB_CLIENT_X509=<Client X509 Firebase>
FB_UNIVERSE_DOMAIN=<Uniiverse domain Firebase>
```

Vous avez dû recevoir ces informations par mail. Si ce n'est pas cas, veuillez me contacter. Vous avez juste à copier le contenu du fichier `env.txt` reçu par mail dans le fichier `.env`.

Ensuite, placez le fichier `dump.sql` reçu par mail dans le dossier aq54-start.

Dans le terminal, entrez :

```
docker-compose up --build
```

Accédez à l'application via `localhost:3000`
