# Docker-Gitlab

Une brique Docker avec :

- Gitlab avec SSL (HTTPS)
- Gitlab Runner (CI/CD)
- Traefik (Proxy)

## Initialisation

1. Pensez à modifier les fichier ``.env`` et ``traefik/traefik.toml`` afin de fournir vos noms de domaine et le réseau créé sur docker pour le proxy.
2. Créer le répertoire ``certs`` et y stocker votre certificat SSL (crt) et votre clef (key) généré par vos soins ou une autorité tiers.
3. Créer le réseau (network) docker sur lequel vous souhaitez mettre le proxy (renseigner dans l'étape 1).
4. Vérifier les noms de fichiers et domaine dans le fichier ``docker-compose.yml``.

## Utilisation

Une fois les étapes d'initialisation, vous pouvez lancer votre compose avec un simple :

```docker-compose up -d```

## Accès

Pour accéder à **Traefik** ou **Gitlab**, il suffit de saisir votre nom de domaine associé à celui-ci dans le fichier ``.env``.

## Explications

_TODO_ : Fournir une explication sur le fonctionnement de l'ensemble.
