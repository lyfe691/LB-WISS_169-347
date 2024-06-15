# Projekt-Dokumentation
## Projektübersicht

Dieses Projekt umfasst die Einrichtung und Konfiguration der folgenden Dienste für ein KMU:

- MediaWiki: Ein Wiki für firmeninterne Zwecke auf Port 8085.
- Nextcloud: Eine Filesharing- und Kollaborationsplattform auf Port 8080.
- Gogs: Eine Self-Hosted Git-Server-Plattform auf Port 3000.
- Portainer: Ein Docker-Management-Tool auf Port 9000.

Alle Dienste wurden mit Docker-Compose konfiguriert und laufen in Docker-Containern. Die Konfiguration und Verwaltung der Container erfolgt über GitLab.

### Projektstruktur

Wir haben die Projektstruktur wie folgt organisiert:

```plaintext
LB/
├── docs/
|   ├── Arbeitsjournal.md
|   |── Dokumenation.md
│   ├── Testkonzept.md
│   └── README.md
├── services/
│   ├── mediawiki/
│   │   └── docker-compose.yaml
│   ├── nextcloud/
│   │   └── docker-compose.yaml
│   ├── gogs/
│   │   └── docker-compose.yaml
│   └── portainer/
│       └── docker-compose.yaml
└── .gitignore
```
### Voraussetzungen
- Docker und Docker-Compose müssen auf dem Host-System installiert sein.
- Ein GitLab-Konto zur Versionierung und Verwaltung der Konfigurationsdateien.

### Einrichtung der Dienste

#### MediaWiki

```yaml
version: '3.8'

services:
  mediawiki:
    image: mediawiki:latest
    container_name: mediawiki
    networks:
      - internal_net
    environment:
      - MEDIAWIKI_DB_TYPE=mysql
      - MEDIAWIKI_DB_HOST=db
      - MEDIAWIKI_DB_NAME=mediawiki
      - MEDIAWIKI_DB_USER=mediawiki
      - MEDIAWIKI_DB_PASSWORD=secret
    volumes:
      - mediawiki_data:/var/www/html
    ports:
      - "8085:80"
    depends_on:
      - db

  db:
    image: mysql:5.7
    container_name: mediawiki_db
    networks:
      - internal_net
    environment:
      - MYSQL_ROOT_PASSWORD=root_password
      - MYSQL_DATABASE=mediawiki
      - MYSQL_USER=mediawiki
      - MYSQL_PASSWORD=secret
    volumes:
      - db_data:/var/lib/mysql

networks:
  internal_net:
    driver: bridge

volumes:
  mediawiki_data:
  db_data:
```
<hr>

#### Nextcloud
```yaml
version: '3.8'

services:
  nextcloud:
    image: nextcloud:latest
    container_name: nextcloud
    networks:
      - internal_net
    environment:
      - MYSQL_HOST=db
      - MYSQL_DATABASE=nextcloud
      - MYSQL_USER=nextcloud
      - MYSQL_PASSWORD=secret
    volumes:
      - nextcloud_data:/var/www/html
    ports:
      - "8080:80"
    depends_on:
      - db

  db:
    image: mysql:5.7
    container_name: nextcloud_db
    networks:
      - internal_net
    environment:
      - MYSQL_ROOT_PASSWORD=root_password
      - MYSQL_DATABASE=nextcloud
      - MYSQL_USER=nextcloud
      - MYSQL_PASSWORD=secret
    volumes:
      - db_data:/var/lib/mysql

networks:
  internal_net:
    driver: bridge

volumes:
  nextcloud_data:
  db_data:
```
<hr>

#### Gogs
```yaml
version: '3.8'

services:
  gogs:
    image: gogs/gogs:latest
    container_name: gogs
    networks:
      - internal_net
    environment:
      - DB_TYPE=mysql
      - DB_HOST=db:3306
      - DB_NAME=gogs
      - DB_USER=gogs
      - DB_PASSWD=secret
    volumes:
      - gogs_data:/data
    ports:
      - "3000:3000"
      - "2222:22"
    depends_on:
      - db

  db:
    image: mysql:5.7
    container_name: gogs_db
    networks:
      - internal_net
    environment:
      - MYSQL_ROOT_PASSWORD=root_password
      - MYSQL_DATABASE=gogs
      - MYSQL_USER=gogs
      - MYSQL_PASSWORD=secret
    volumes:
      - db_data:/var/lib/mysql

networks:
  internal_net:
    driver: bridge

volumes:
  gogs_data:
  db_data:
```
<hr> 

#### Portainer
```yaml
version: '3.8'

services:
  portainer:
    image: portainer/portainer-ce:latest
    container_name: portainer
    networks:
      - internal_net
    ports:
      - "9000:9000"
    volumes:
      - /var/run/docker.sock:/var/run/docker.sock
      - portainer_data:/data

networks:
  internal_net:
    driver: bridge

volumes:
  portainer_data:
```
<hr>

### Dienste starten

Um die Dienste zu starten navigierten wir in die entsprechenden Verzechinisse führten ```docker-compose up -d``` aus:

```bash
cd ~/LB/services/mediawiki
docker-compose up -d
```

```bash
cd ~/LB/services/nextcloud
docker-compose up -d
```

```bash
cd ~/LB/services/gogs
docker-compose up -d
```

```bash
cd ~/LB/services/portainer
docker-compose up -d
```
### Versionsverwaltung

Alle Konfigurationsdateien wurden im GitLab-Repository versioniert. Der Fortschritt wurde durch regelmässige Commits dokumentiert.
<hr>

#### Repository einrichten und Änderungen pushen

1. Remote-Repository hinzufügen:

```bash
git remote add origin https://gitlab.com/joomla2613824/WISS-LB.git
```
2. Änderungen pushen:

```bash
git add -A
git commit --amend -m "beispiel für doku"
git push origin master --force
```
<hr>

### Einrichten von MediaWiki

##### Jetzt haben wir angefangen das MediaWiki einzurichten, es sah so aus am anfang:

 ![MediaWiki-start](images/mediawiki/start_mediawiki.png)

##### Installation:

 ![Mediawiki-installation](images/mediawiki/mediawiki_installation.png)

##### LocalSettings.php:

 ![LocalSettigns.php](images/mediawiki/LocalSettingsphp.png)

Nachdem wir mit der Konfiguration fertig waren mussten wir LocalSettings.php ins ```mediawiki:/var/www/html/``` Verzechnis kopieren und das machten wir mit dem command ```scp``` auf dem main OS:
```bash
scp "C:\Users\sebiz\Downloads\LocalSettings.php" lyfe@192.168.1.32:/home/lyfe
```
Als nächstes mussten wir das LocalSettings.php ins docker environement verschieben:
```bash
docker cp /home/lyfe/LocalSettings.php mediawiki:/var/www/html/LocalSettings.php
```
##### Small Showcase:

scp:

- ![showcase_scp](images/mediawiki/showcase_scp.png)

docker cp:

- ![showcase_docker-cp](images/mediawiki/Beispiel_docker_cp.png)

##### So sah das ganze nach dem setup aus:
![mediawiki installation fertig](images/mediawiki/fertig_setup_mediawiki.png)

Beim einrichten haben wir auch noch bemerkt das wir keine admistratoren rechte hatten, deswegen haben wir das LocalSettings.php umgeändert:

```bash
$wgGroupPermissions['*']['createaccount'] = true;
$wgGroupPermissions['sysop']['createaccount'] = true;
```
```bash
$wgGroupPermissions['*']['read'] = true;
$wgGroupPermissions['user']['edit'] = true;
$wgGroupPermissions['sysop']['delete'] = true;
$wgGroupPermissions['bureaucrat']['userrights'] = true;
```
<hr>

### Einrichten von NextCloud
Bei NextCloud mussten wir einfach die details des docker-compose.yaml eingeben.
##### Wie es aussieht:
![NextCloud after setup](images/nextcloud/nextcloud_aftersetup.png)
##### Bestätingung des contents:
```bash
docker exec -it nextcloud /bin/bash
cd /var/www/html/config
cat config.php
```
![Confirmation config](images/nextcloud/confirmation_nextcloud.png)
<hr>

### Einrichten von Gogs
##### Am anfang der Einrichtung sah es so aus:
![anfang gogs](images/gogs/gogs_anfang.png)
##### Während der installation:
![während installaiton](images/gogs/gogs_installatuion.png)
##### Nach der installation:
![nach installation](images/gogs/gogs_after_installation.png)
<hr>

### Einrichten von Portainer


