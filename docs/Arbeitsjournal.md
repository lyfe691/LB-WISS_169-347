# Skizze
![169Skizze drawio](https://github.com/lyfe691/LB-WISS_169-347/assets/111024477/3c2da311-a8e4-409c-be65-15d5361bbcc3)

# Verantwortlichkeit
  **Yanis Zuständig für:**
  - Projektleitung
  - Aufsetzten der VM und Konfiguieren der verschiedenen Dienste
  - Erstellen des Github & Gitlab Repository

  **Benicio Zuständig für:**
  - Erweiterung der Dokumentation
  - Erstellen vom Gantt Diagramm
  - Transfer vom Gitlab zu Github

# Arbeitsjournal

## Woche 1

### Montag
- **Aufgabe:** Vorbereitung und Planung des Projekts
  - Projektstruktur und -ziele festgelegt
  - Anforderungen dokumentiert
  - Projektplan erstellt

### Dienstag
- **Aufgabe:** Installtion auf Server
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
  - Tests gemäss den Testplänen durchgeführt
  - Ergebnisse dokumentiert
  - **Herausforderung:** Testfehler bei Nextcloud-Dateifreigabe, durch Anpassung der Freigabeeinstellungen gelöst

### Mittwoch
- **Aufgabe:** Implementierung von Sicherheitsmassnahmen
  - Passwörter extern in .env Datei gespeichert und in .gitignore eingefügt
  - **Herausforderung:** Gab keine

### Donnerstag
- **Aufgabe:** Implementierung von Backup-Strategien
  - Backup-Strategien für MediaWiki, Nextcloud und Gogs dokumentiert
  - Regelmässige Backups/Snapshots und appliances erstellt
  - Backup- und Wiederherstellungsverfahren getestet und dokumentiert
  - **Herausforderung:** Fehler bei der Wiederherstellung der Nextcloud-Datenbank, durch Überprüfung der Backup-Skripte (config.php) gelöst

### Freitag
- **Aufgabe:** Dokumentation und Vorbereitung der Projektabgabe
  - Detaillierte Dokumentation der Konfigurationen und Installationsschritte erstellt
  - Arbeitsjournal abgeschlossen und formatiert
  - Projektabgabe gemäss den Anforderungen vorbereitet
  - **Herausforderung:** Vollständigkeit und Klarheit der Dokumentation sicherstellen


## Woche 3

### Montag
- **Aufgabe:**
- 

### Dienstag
- **Aufgabe:** Kontrolle der Systeme
  - Testen der Sicherheits Zugänge der Systeme
  - Verbesseren der Login-Daten zu den Systemen
  - Verschiedene Umgehungs methoden ausprobiert und die dann repariert

### Mittwoch
- **Aufgabe:** Überprüfung des Ganzen Projekts
  - Arbeitsjournal verbessert
  - Ganzes Projekt von Gitlab auf Github transferiert (falsch verstanden)


## Fazit zum Projekt
#### Einrichtung von Diensten für ein Informatik-KMU
Das Projekt zur Einrichtung verschiedener Dienste für ein Informatik-KMU war sowohl herausfordernd als auch lehrreich. Ziel war es, eine MediaWiki-Plattform, Nextcloud für Filesharing und eine Git-Verwaltung mit Gogs zu implementieren und diese Dienste unter Verwendung von Docker-Containern zu betreiben. Dabei sollten alle Daten persistent gespeichert und die Dienste mit Portainer überwacht werden.

#### Herausforderungen und Lösungen
Eine der grössten Herausforderungen bestand darin, die verschiedenen Dienste in Docker-Containern zu implementieren und sicherzustellen, dass diese Container effizient und zuverlässig miteinander kommunizieren. Dies erforderte ein tiefes Verständnis der Docker-Technologien sowie der Netzwerkkonfiguration innerhalb von Docker.

Ein weiteres Problem war die sichere Verwaltung der Zugangsdaten. Um dies zu lösen, wurden Umgebungsvariablen verwendet und sensible Daten in separate ``.env`` Dateien ausgelagert. Dies erhöhte die Sicherheit und erleichterte die Verwaltung der Zugangsdaten erheblich.

#### Lernfortschritte und Erfolge
Durch die Arbeit an diesem Projekt habe wir mein Wissen in mehreren Bereichen vertieft. Insbesondere habe ich ein besseres Verständnis für Docker und dessen Anwendungsmöglichkeiten gewonnen. Die Einrichtung von MediaWiki, Nextcloud und Gogs hat mir gezeigt, wie flexibel und leistungsfähig Docker-Container sind.

Der Einsatz von Portainer zur Überwachung und Verwaltung der Container hat uns gezeigt, wie wichtig es ist, eine zentrale Verwaltungskonsole zu haben, um die Kontrolle über mehrere Dienste zu behalten. Auch die Implementierung und Verwaltung von Datenbanken innerhalb von Docker-Containern war ein wertvoller Lernschritt.

#### Fazit
Das Projekt hat gezeigt, dass es möglich ist, komplexe IT-Dienstleistungen effizient und sicher in einer containerisierten Umgebung bereitzustellen. Durch die Nutzung von Docker und Portainer konnten wir eine robuste und skalierbare Lösung implementieren, die den Anforderungen des Auftraggebers gerecht wird. Der Einsatz von Umgebungsvariablen und .env-Dateien hat die Sicherheit der Lösung erhöht und gleichzeitig die Verwaltung vereinfacht.

Insgesamt war das Projekt ein Erfolg, und die erlernten Fähigkeiten und Erfahrungen werden in zukünftigen Projekten von grossem Nutzen sein. Die Herausforderungen, denen ich begegnet bin, haben mein Verständnis für containerisierte Anwendungen und deren Verwaltung erheblich vertieft. Dieses Projekt hat gezeigt, dass moderne Technologien wie Docker und Portainer wesentliche Werkzeuge für die Bereitstellung und Verwaltung von IT-Diensten sind.

### Was haben wir zu sagen?
 #### Yanis:
##### Systeminstallation und -konfiguration
Während des Projekts habe ich die Installation und Konfiguration aller benötigten Systeme übernommen. Dazu gehörten die Einrichtung von MediaWiki, Nextcloud und Gogs, sowie die Konfiguration von Portainer zur Überwachung der Container. Diese Aufgaben haben mir geholfen, meine praktischen Fähigkeiten im Umgang mit Docker und verschiedenen Webanwendungen zu vertiefen.

#### Problemlösung und Debugging
Im Laufe des Projekts traten verschiedene technische Herausforderungen auf, die ich erfolgreich gelöst habe. Dies beinhaltete das Beheben von Berechtigungsproblemen, das Anpassen von Konfigurationsdateien und das Sicherstellen der Kommunikation zwischen den Containern. Diese Erfahrungen haben meine Fähigkeiten im Troubleshooting und in der Fehlerbehebung erheblich verbessert.

Ein Problem das ich noch anprechen möchte war beim configurieren des config.php in der nextcloud, es stelle sich aber heraus das es ein einfacher fix gab, man musste einfach die IP von ihm und mir weiterleiten und in das condig.php implementieren:
```bash
 array (
    0 => 'localhost:8080',
    1 => '172.28.1.15',
    2 => '172.28.1.2',
  ),
```
Mit hilfe dieser Konfigurationen konnte Benicio auf meine Lokalen Instanzen zugreifen.

##### Sicherheitsaspekte
Ein wesentlicher Teil meiner Arbeit bestand darin, die Sicherheit der Systeme zu gewährleisten. Dazu habe ich sensible Daten aus den Docker-Compose-Dateien entfernt und in .env-Dateien ausgelagert. Ausserdem habe ich die Konfigurationen angepasst, um unbefugten Zugriff zu verhindern. Diese Massnahmen waren entscheidend, um die Integrität und Sicherheit der installierten Systeme zu gewährleisten.

##### Reflexion
Ich bin stolz auf meine Leistung bei der technischen Umsetzung des Projekts. Die Arbeit hat meine Fähigkeiten im Bereich der Systemadministration und -sicherheit gestärkt. Ich habe gelernt, wie wichtig eine gründliche Planung und Dokumentation ist, um komplexe Projekte erfolgreich durchzuführen.
Alles in allem hat das Projekt spass gemacht und ich habe sehr viel gelernt.


 #### Benicio:
Während des Projekts erstellte ich umfassende Dokumentation, Skizzen und ein Gantt-Diagramm. Diese Dokumente hielten alle Projektschritte fest und informierten uns über den aktuellen Stand. Die Skizzen visualisierten die Systeminteraktionen und halfen, Probleme frühzeitig zu erkennen. Obwohl ich anfänglich Schwierigkeiten mit dem Gantt-Diagramm hatte, konnte ich durch wiederholte Anpassungen und Rücksprache die zeitliche Planung letztendlich erfolgreich strukturieren und den Fortschritt überwachen.
 
