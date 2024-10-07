# BP-valkey

## Qu'est-ce que Valkey ?
Valkey est un serveur de structures de données hautes performances qui sert principalement aux charges de travail clé/valeur. Il prend en charge une large gamme de structures natives et un système de plug-ins extensible pour ajouter de nouvelles structures de données et de nouveaux modèles d'accès.

## Pourquoi Redis pose-t-il un problème de licence ?
Redis, une base de données en mémoire populaire, est sous la licence "Redis Source Available License" (RSAL). Cette licence permet l'utilisation libre de Redis dans de nombreux cas, mais impose certaines restrictions concernant l'utilisation dans des offres commerciales cloud. Les principaux fournisseurs cloud ne peuvent pas proposer Redis en tant que service managé sans respecter certaines conditions définies par cette licence.

Cela devient problématique si vous prévoyez d'utiliser Redis dans un environnement commercial, car les utilisateurs doivent veiller à respecter cette licence sous peine de violer les conditions d'utilisation. De plus, certaines fonctionnalités "modules" de Redis sont couvertes par des licences spécifiques qui imposent des restrictions supplémentaires.

## Prérequis

Assurez-vous d'avoir les éléments suivants installés sur votre machine avant de commencer :

- Docker
- Docker Compose
- [Le projet BP-traefik-v3-ssl-ovh-api](https://github.com/lgrdev/BP-traefik-v3-ssl-ovh-api)

## Structure du projet

```
.
├── docker-compose.yaml
├── valkey/
│   ├── data/  # Répertoire de persistance des données
│   ├── conf/  # Répertoire pour les configurations personnalisées
└── .env.sample
```

## Installation

### 1. Préparation

copier le fichier .env.sample en .env
```bash
cp .env.sample .env
```

### 2. Configurer l'environnement

Modifiez le fichier `.env` à la racine du projet avec les variables nécessaires :

```env
DB_VERSION=latest
```

Le choix de la version mariadb doit être effectué à partir des tags disponibles sur [Image officielle valkey](https://hub.docker.com/r/valkey/valkey/tags)

### 3. Lancer le service

Une fois les secrets créés et les variables d'environnement configurées, vous pouvez lancer le service MariaDB avec Docker Compose :

```bash
docker-compose up -d
```

## Contributions

Les contributions sont les bienvenues ! Si vous trouvez des problèmes ou souhaitez ajouter des fonctionnalités, n'hésitez pas à ouvrir une issue ou une pull request.

## License

Ce projet est sous licence MIT. Voir le fichier [LICENSE](LICENSE) pour plus de détails.