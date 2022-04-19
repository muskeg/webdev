# webdev

Exemple d'environnement de développement Web (NGINX + PHP + MySQL) Dockerisé

---

## Repository

Le repository contient les fichier suivants

```bash
├── README.md
├── content
│   └── index.php
├── docker-compose.yml
├── nginx
│   ├── config
│   │   └── localhost.conf
│   └── logs
│       ├── access.log
│       └── error.log
└── php
    └── php.ini
```

### README.md

Ce fichier.

### content

Ce dossier contient le contenu Web (inclus: un hello-world php).

### docker-compose.yml

Contient les définitions des différents containers de la plateforme Web

### nginx

#### config

Ce dossier contient la configuration NGINX pour un serveur http (non-ssl) et PHP-FPM

#### logs

Ce dossier contient les logs d'accès et d'erreurs du service NGINX

### php

Ce dossier contient le php.ini. Le fichier présentement est une copie de `php.ini-development`.

> :warning: **Ne pas utiliser en production**. Cette configuration expose trop d'information

---

## Installation

Cet environnement est construit sur Docker Compose.
Le moyen le plus simple d'installer les outils nécessaires pour un utilisateur non-commercial est d'installer Docker Desktop.

[Télécharger Docker Desktop](https://www.docker.com/products/docker-desktop/)

## Utilisation

### Docker Compose

Pour lancer l'environnement, dans la racine du repository:

```bash
$ docker compose up -d
[+] Running 4/4
 ⠿ Container webdev-db-1            Started     0.7s
 ⠿ Container webdev-phpmyadmin-1    Started     1.6s
 ⠿ Container webdev-php-1           Started     0.7s
 ⠿ Container webdev-web-1           Started     1.6s
```

### Contenu Web

Le contenu est déposé dans le dossier `./content` et est accessible <http://localhost:8080>

### Logs

Bien que les logs NGINX soient exposés dans le dossier `/nginx/logs` il est possible de suivre les logs des containers facilement en utilisant la commande:

`docker-compose logs -f`

### MySQL

Le container crée une base de données appelée `webdev` automatiquement (user: `webdev` password: `DO_NOT_USE_IN_PROD`).

Le container MySQL est disponible au service Web (et aux fichiers PHP) via le réseau Docker interne:

* host: `db`
* port: `3306`

Il est également possible de se connecter à la base de donnée à partir de l'ordinateur host:

* host: `localhost`
* port: `6033`

L'environnement présente finalement aussi l'outil phpMyAdmin qui permet d'administrer la base de donnée via une interface Web:

* phpMyAdmin: <http:localhost:8081>
* server: `vide`, environnement configuré pour utiliser `db` par défaut
* username: `root`
* password: `DO_NOT_USE_IN_PROD`
