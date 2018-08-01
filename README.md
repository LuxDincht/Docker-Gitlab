# Docker-Gitlab

Une brique Docker clean avec seulement :

- [Traefik](https://traefik.io/) (Proxy)

## Utilisation

### Initialisation

1. Pensez à modifier les fichier ``.env`` et ``traefik/traefik.toml`` afin de fournir vos noms de domaine et le réseau créé sur docker pour le proxy.
2. Créer le réseau (network) docker sur lequel vous souhaitez mettre le proxy (renseigner dans l'étape 1).
3. Vérifier les noms de fichiers et domaine dans le fichier ``docker-compose.yml``.

### Exécution

Une fois les étapes d'initialisation, vous pouvez lancer votre compose avec un simple :

```
docker-compose up -d
```

### Accès

Pour accéder à **Traefik**, il suffit de saisir votre nom de domaine associé à celui-ci dans le fichier ``.env``.

## Explications

Voici quelques explications sur la manière de gérer les différents éléments intervenant dans cette brique.

### Génération du certificat SSL

#### Autorité de certification

Il existe plusieurs autorité de certification comme **Comodo**, **RapidSSL**, **thawte**, etc.  

Il est possible d'avoir un certificat gratuitement pour une domaine précis d'une durée de 30 jours.  
Sinon en fonction des options choisis, il faudra débourser un certain montant pour une durée déterminée. (en règle générale 1 an)

Il existe des types de certificat qui permettent de certifié l'ensemble d'un domaine (*Wildcard*).

Pour plus de détail, je vous invite à vous renseigner sur Google et les sites spécifiques.

#### Let's Encrypt

Lets'encrypt est une autorité de certification qui vous permet de délivrer gratuitement un certificat de domaine.  

**C'est celui-ci que nous allons utiliser !**

##### Traefik

Traefik embarque Let's Encrypt et vous permet de manière dynamique de créer des certificats de domaine pour chacun de vos containers qu'il doit gérer.  
