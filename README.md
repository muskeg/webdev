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

Ce dossier contient le contenu Web. Ce contenu est disponible au `http://localhost:8080`

### docker-compose.yml

Contient les définitions des différents containers de la plateforme Web

### nginx

#### config

Ce dossier contient la configuration NGINX pour un serveur http (non-ssl) et PHP-FPM

#### logs

Ce dossier contient les logs d'accès et d'erreurs du service NGINX

---

## Installation

Cet environnement est construit sur Docker Compose.
Le moyen le plus simple d'installer les outils nécessaires pour un utilisateur non-commercial est d'installer Docker Desktop.

[Télécharger Docker Desktop](https://www.docker.com/products/docker-desktop/)

## Utilisation

### Docker Compose

Pour lancer l'environnement:

```bash
$ docker compose up -d
[+] Running 4/4
 ⠿ Container webdev-db-1            Started     0.7s
 ⠿ Container webdev-phpmyadmin-1    Started     1.6s
 ⠿ Container webdev-php-1           Started     0.7s
 ⠿ Container webdev-web-1           Started     1.6s
```

### Contenu Web


