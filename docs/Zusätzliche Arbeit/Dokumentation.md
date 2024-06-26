# Verbindung auf anderen Geräten 
Damit ich und Benicio zusammen auf meine Lokalen Instanzen zugreifen konnten mussten wir einfach noch zusätslich die Ports jeweils mit meiner IP Weiterleiten 
Damit ich und Benicio Zusammenarbeiten konnten mussten wir im Docker Environment ``root@6e52e35328f6:/var/www/html/config/config.php`` so ändern das er zugriff auf meine Lokale Instanz hat, das machten wir so:

### Man muss meine lokale IP und seine Lokale IP einfügen.
```php
  array (
    0 => 'localhost:8080', 
    1 => '172.28.1.15', # benicio ip
    2 => '172.28.1.2', # meine ip
  ),
```
### Das ist der ganze code
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
  'trusted_domains' =>

# --------------------------------------------------------------------
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



### Dazu musste man noch die Ports Weiterleiten:

![nextcloud_port](https://github.com/lyfe691/LB-WISS_169-347/assets/111024477/6a0063ad-875b-4966-8f14-982e1e1bb456)
