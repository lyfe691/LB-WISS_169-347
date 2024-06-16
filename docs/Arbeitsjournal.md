# Skizze, muss noch updaten

# Arbeitsjournal

## Woche 1

### Montag
- **Aufgabe:** Vorbereitung und Planung des Projekts
  - Projektstruktur und -ziele festgelegt
  - Anforderungen analysiert und dokumentiert
  - Projektplan erstellt

### Dienstag
- **Aufgabe:** Einrichtung der Entwicklungsumgebung
  - Ubuntu VM aufgesetzt und konfiguriert beziehungsweise einfach die vom Unterricht benutzt.
  - Docker und Docker-Compose installiert
  - GitLab Repository erstellt und initialisiert
  - Projektstruktur in GitLab hochgeladen

### Mittwoch
- **Aufgabe:** Konfiguration und Start von MediaWiki
  - `docker-compose.yml` für MediaWiki erstellt und getestet
  - MediaWiki-Datenbank (MySQL) konfiguriert
  - MediaWiki-Weboberfläche aufgerufen und Grundkonfiguration durchgeführt
  - Benutzerkonto für MediaWiki erstellt und Administratorrechte zugewiesen
  - **Herausforderung:** Fehler bei der Datenbankverbindung, durch Überprüfung der Umgebungsvariablen gelöst

### Donnerstag
- **Aufgabe:** Konfiguration und Start von Nextcloud
  - `docker-compose.yml` für Nextcloud erstellt und getestet
  - Nextcloud-Datenbank (MySQL) konfiguriert
  - Nextcloud-Weboberfläche aufgerufen und Grundkonfiguration durchgeführt
  - Benutzerkonto für Nextcloud erstellt und Administratorrechte zugewiesen
  - **Herausforderung:** Nextcloud-Datenbankfehler, durch Neuinstallation der Datenbank gelöst

### Freitag
- **Aufgabe:** Konfiguration und Start von Gogs
  - `docker-compose.yml` für Gogs erstellt und getestet
  - Gogs-Datenbank (MySQL) konfiguriert
  - Gogs-Weboberfläche aufgerufen und Grundkonfiguration durchgeführt
  - Benutzerkonto für Gogs erstellt und Administratorrechte zugewiesen
  - **Herausforderung:** Repository-Verzeichnis konfigurieren und prüfen, dass der Pfad korrekt ist

## Woche 2

### Montag
- **Aufgabe:** Konfiguration und Start von Portainer
  - `docker-compose.yml` für Portainer erstellt und getestet
  - Portainer-Weboberfläche aufgerufen und Grundkonfiguration durchgeführt
  - Docker-Container über Portainer verwaltet und überprüft
  - **Herausforderung:** Portainer-Containerstartprobleme, durch Anpassung der `docker-compose.yml` gelöst

### Dienstag
- **Aufgabe:** Tests und Überprüfungen der installierten Dienste
  - Testpläne für MediaWiki, Nextcloud und Gogs erstellt
  - Tests gemäß den Testplänen durchgeführt
  - Ergebnisse dokumentiert
  - **Herausforderung:** Testfehler bei Nextcloud-Dateifreigabe, durch Anpassung der Freigabeeinstellungen gelöst

### Mittwoch
- **Aufgabe:** Implementierung von Sicherheitsmaßnahmen
  - Überprüfung und Sicherstellung, dass alle Dienste sichere Passwörter verwenden
  - Netzwerkkonfiguration überprüft und unnötige Ports geschlossen
  - SSL/TLS-Konfiguration für Nextcloud und Gogs implementiert
  - **Herausforderung:** SSL/TLS-Zertifikatsprobleme bei Gogs, durch Neuinstallation der Zertifikate gelöst

### Donnerstag
- **Aufgabe:** Implementierung von Backup-Strategien
  - Backup-Strategien für MediaWiki, Nextcloud und Gogs dokumentiert
  - Regelmäßige Backups der Datenbanken und Dateien eingerichtet
  - Backup- und Wiederherstellungsverfahren getestet und dokumentiert
  - **Herausforderung:** Fehler bei der Wiederherstellung der Nextcloud-Datenbank, durch Überprüfung der Backup-Skripte gelöst

### Freitag
- **Aufgabe:** Dokumentation und Vorbereitung der Projektabgabe
  - Detaillierte Dokumentation der Konfigurationen und Installationsschritte erstellt
  - Arbeitsjournal abgeschlossen und formatiert
  - Projektabgabe gemäß den Anforderungen vorbereitet
  - **Herausforderung:** Vollständigkeit und Klarheit der Dokumentation sicherstellen
