# Verbindung auf anderen Geräten 
Damit Benicio und ich zusammen auf meine lokale Instanz zugreifen konnten, mussten wir zusätzlich die Ports mit meiner IP weiterleiten. Mit meiner IP ist die IP-Adresse im WISS-Netzwerk gemeint, die auch von Benicio gesehen werden kann.

Der zweitoberste Eintrag ist der NextCloud-Dienst (8080), die anderen Einträge sind Portainer (9000), MediaWiki (8085) und Gogs (3000).
![nextcloud_port](https://github.com/lyfe691/LB-WISS_169-347/assets/111024477/6a0063ad-875b-4966-8f14-982e1e1bb456)
<br>‎ 
<br>Jeweils bei den Diensten funktionierte es sofort, nachdem man die Ports weitergeleitet hatte. Aber bei Nextcloud trat ein Domain-Fehler auf, weil es eine unbekannte Domain war und nicht localhost. Um den Fehler zu beheben, mussten wir im Docker-Environment, also im ``docker exec -it docker_id /bin/bash``, die Datei ``/var/www/html/config/config.php`` ändern. Im Abschnitt trusted_domains haben wir unsere eigenen IP-Adressen hinzugefügt.

### Dies sollte dann wie Folgt aussehen.
```php
  array (
    0 => 'localhost:8080', 
    1 => '172.28.1.15', # benicio ip
    2 => '172.28.1.2', # meine ip
  ),
```
### Hier wäre der Ganze Code.
```php
<?php
$CONFIG = array (
  'htaccess.RewriteBase' => '/',
  'memcache.local' => '\\OC\\Memcache\\APCu',
  'apps_paths' =>
  array (
    0 =>
    array (
      'path' => '/var/www/html/apps',
      'url' => '/apps',
      'writable' => true,
    ),
    1 =>
    array (
      'path' => '/var/www/html/custom_apps',
      'url' => '/custom_apps',
      'writable' => true,
    ),
  ),
  'upgrade.disable-web' => true,
  'instanceid' => 'oc7jr9r9m1td',
  'passwordsalt' => 'hy2Rytej82S0E5ga9XE3T6ZswBWFbB',
  'secret' => '7obcFkIX5Onoig2Kletmz1EL/5dpmzzYnREOUuITxWKKxO/b',
# --------------------------------------------------------------------
  'trusted_domains' =>
  array (
    0 => 'localhost:8080',
    1 => '172.28.1.15', # benicio ip
    2 => '172.28.1.2', # meine ip
  ),
# ---------------------------------------------------------------------
  'datadirectory' => '/var/www/html/data',
  'dbtype' => 'mysql',
  'version' => '29.0.1.1',
  'overwrite.cli.url' => 'http://localhost:8080',
  'dbname' => 'nextcloud',
  'dbhost' => 'db',
  'dbport' => '',
  'dbtableprefix' => 'oc_',
  'mysql.utf8mb4' => true,
  'dbuser' => 'nextcloud',
  'dbpassword' => 'secret',
  'installed' => true,
  'config_is_read_only' => true,
);

```
