# Informieren

## Anforderungen:
1. Media-Wiki auf port 8085 für wegen firma.
2. Nextcloud auf Port 8080 für Filesharing.
3. Eigeness Gitlab für Quellcodeverwaltung.
4. Persistente speicherung aller Daten.
5. Überwachung der Dienste mit Porttainer.
6. Systemdokumentation und Konfigurationsdateien sollen auf privatem Github-Account versioniert werden.

## Schritt 2: Planen
### Arbeitsplan:
1. Informieren: 1 Stunde
2. Planen: 30 Minuten
3. Entscheiden:
    - Systemüberblick skizzieren: 1 Stunde
    - Testkonzept und Testplan erstellen: 1 Stunde
    - Sicherheitsanforderungen definieren: 1 Stunde
4. Realisieren: (für jedes Teilsystem)
    - docker-compose erstellen: 2 Stunden pro Teilsystem
    - Testen und protokollieren: 1 Stunde pro Teilsystem
5. Kontrollieren: 1 Stunde
6. Auswerten: 1 Stunde

## Schritt 3: Entscheiden

### Systemüberblick skizzieren:
- **Media-Wiki**: Container auf Port 8085, persistent volume für Daten
- **Nextcloud**: Container auf Port 8080, persistent volume für Daten
- **Gitlab**: Container mit persistent volume
- **Porttainer**: Container für Überwachung
- **Datenablage**: Nutzung von Docker Volumes für persistente Daten

### Testkonzept und Testplan:
- Installation und Start der Container
- Zugriffstests auf Webinterfaces (Media-Wiki, Nextcloud, Gitlab)
- Datenpersistenztests (Daten hinzufügen, Container neustarten, Datenverfügbarkeit überprüfen)
- Überwachungstest mit Porttainer (Containerstatus überwachen)

### Sicherheitsanforderungen:
- Netzwerkisolierung der Container
- Nutzung von SSL/TLS für sichere Verbindungen (Reverse Proxy z.B. Traefik)
- Regelmäßige Backups der persistenten Daten

## Schritt 4: Realisieren
docker-compose.yaml files erstellen für jeden Dienst.

## Schritt 5: Kontrollieren

### Abweichungen vom Arbeitsplan:
- **Verzögerungen bei der Installation?**
    Ein paar Netzwerkprobleme sonst lief es recht Gut.
- **Probleme bei der Datenpersistenz?**
    Gar keine werden automatisch richtig abgespeichert.

## Schritt 6: Auswerten

### Erfahrungen:
- Verbesserung der Docker- und Containerisierungskenntnisse
- Wichtige Erkenntnisse über die Netzwerksicherheit und Datenpersistenz
- Effektive Nutzung von Porttainer zur Überwachung und Verwaltung von Containern

### Dokumentation auf Github:
- Erstellen eines privaten Repositories
- Hochladen der docker-compose.yaml und der Systemdokumentation
