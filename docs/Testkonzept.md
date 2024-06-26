

# Testkonzept für das LB-Projekt

#### 1. Einleitung

Dieses Testkonzept beschreibt die Teststrategie und -verfahren für die im Rahmen des Projekts eingerichteten und konfigurierten Dienste: MediaWiki, Nextcloud, Gogs und Portainer. Ziel ist es, die Funktionalität, Sicherheit und Performance der Dienste sicherzustellen.

#### 2. Ziele und Umfang

Ziel der Tests ist es, sicherzustellen, dass alle Dienste ordnungsgemäss eingerichtet sind und wie erwartet funktionieren. Der Testumfang umfasst:

- Installation und Grundkonfiguration
- Benutzerverwaltung
- Datenintegrität und -sicherheit
- Performance- und Lasttests
- Backup und Wiederherstellung

#### 3. Teststrategie

##### 3.1 Testumgebung

Die Tests werden in der gleichen Umgebung durchgeführt, in der die Dienste bereitgestellt werden. Folgende Komponenten sind Teil der Testumgebung:

- Docker und Docker-Compose
- GitLab zur Versionskontrolle
- Browser zum Zugriff auf die Weboberflächen

##### 3.2 Testmethoden

- **Funktionstests**: Überprüfen der Grundfunktionalität der Dienste.
- **Sicherheitstests**: Überprüfen der Zugriffskontrollen und Datensicherheit.
- **Leistungstests**: Messen der Antwortzeiten und Belastbarkeit.
- **Integrationstests**: Sicherstellen, dass alle Dienste miteinander kompatibel sind.

#### 4. Testfälle

##### 4.1 MediaWiki

- **Installation und Grundkonfiguration**
  - Testen der Installation und Grundkonfiguration von MediaWiki.
  - Überprüfen, ob die Startseite erreichbar ist.
  - Erstellen eines neuen Wikis und Hinzufügen von Seiten.
 
  -- **Erwartete Resultate**
    - Installation vorhanden, Konfiguration ist abgespeichert.
    - Startseite erreichbar.
    - Neues Wiki funktioniert und beinhaltet alle Seiten.

- **Benutzerverwaltung**
  - Erstellen und Verwalten von Benutzerkonten.
  - Überprüfen der Zugriffsrechte.

  -- **Erwartete Resultate**
    - Benutzer werden erfolgreich erstellt und sind verfügbar.
    - Benutzerberechtigungen funktionieren.

- **Datenintegrität und -sicherheit**
  - Testen von Backup- und Wiederherstellungsprozessen.
  - Überprüfen der Datenbankverbindung und -konsistenz.
 
  -- **Erwartete Resultate**
    - Backups werden richtig gespeichert und auch wiederhergestellt.
    - Datenbank ist erreichbar, mit allen Daten erreichbar.
 
  -- **Herausforderungen**
    - Fehler bei der Datenbankverbindung, durch Überprüfung der Umgebungsvariablen gelöst

##### 4.2 Nextcloud

- **Installation und Grundkonfiguration**
  - Testen der Installation und Grundkonfiguration von Nextcloud.
  - Überprüfen, ob die Weboberfläche zugänglich ist.
  - Hochladen und Teilen von Dateien.
 
  -- **Erwartete Resultate**
    - Installation vorhanden.
    - Web-Overlay ist erreichbar.
    - Daten werden erfolgreich hochgeladen und gespeichert.

- **Benutzerverwaltung**
  - Erstellen und Verwalten von Benutzerkonten.
  - Überprüfen der Zugriffsrechte und Freigabeeinstellungen.
 
  -- **Erwartete Resultate**
    - Benutzer werden richtig erstellt und gespeichert.
    - Benutzerrechte funktionieren.

- **Datenintegrität und -sicherheit**
  - Testen von Backup- und Wiederherstellungsprozessen.
  - Überprüfen der Datenbankverbindung und -konsistenz.
 
  -- **Erwartete Resultate**
    - Backup ist erfolgreich gespeichert und auch wiederhergestellt.
    - Datenbank ist funktional und konsistent.

  -- **Herausforderungen**
    - Nextcloud-Datenbankfehler, durch Neuinstallation der Datenbank gelöst
      
##### 4.3 Gogs

- **Installation und Grundkonfiguration**
  - Testen der Installation und Grundkonfiguration von Gogs.
  - Überprüfen, ob die Weboberfläche zugänglich ist.
  - Erstellen eines neuen Repositorys.
 
  -- **Erwartete Resultate**
    - Gogs existiert und richtig konfiguriert.
    - Gogs ist erreichbar per Browser.
    - Repositorys werden gespeichert und richtig erstellt.

- **Benutzerverwaltung**
  - Erstellen und Verwalten von Benutzerkonten.
  - Überprüfen der Zugriffsrechte.
 
  -- **Erwartete Resultate**
    - Benutzer können richtig verwaltet und erstellt werden.
    - Benutzer haben gewisse Berechtigungen, die auch funktional sind.

- **Datenintegrität und -sicherheit**
  - Testen von Backup- und Wiederherstellungsprozessen.
  - Überprüfen der Datenbankverbindung und -konsistenz.
 
  -- **Erwartete Resultate**
    - Backups funktionieren und werden auch wiederhergestellt.
    - Datenbank verbindet sich richtig und besteht aus allen Daten.

  -- **Herausforderungen**
    - Fehler bei der Datenbankverbindung, durch Überprüfung der Umgebungsvariablen gelöst
      
##### 4.4 Portainer

- **Installation und Grundkonfiguration**
  - Testen der Installation und Grundkonfiguration von Portainer.
  - Überprüfen, ob die Weboberfläche zugänglich ist.
  - Verwalten von Containern und Images.
 
  -- **Erwartete Resultate**
    - Portrainer ist erfolgreich installiert und die Konfigurationen sind bestehend.
    - Weboberfläche von Portrainer ist erreichbar.
    - Portrainer steuert und verwaltet jegliche Docker erfolgreich.

- **Benutzerverwaltung**
  - Erstellen und Verwalten von Benutzerkonten.
  - Überprüfen der Zugriffsrechte.
 
  -- **Erwartete Resultate**
    - Benutzerkonten sind richtig erreichbar und funktional.
    - Benutzer können auf Portrainer zugreifen und sich anmelden.

  -- **Herausforderungen**
    - Portainer-Containerstartprobleme, durch Anpassung der docker-compose.yml gelöst
 
#### 5. Andere Herausforderungen
-- **Tests und Überprüfungen der installierten Dienste**
  - Testfehler bei Nextcloud-Dateifreigabe, durch Anpassung der Freigabeeinstellungen gelöst
  - Fehler bei der Wiederherstellung der Nextcloud-Datenbank, durch Überprüfung der Backup-Skripte (config.php) gelöst
  - Vollständigkeit und Klarheit der Dokumentation sicherstellen
      
#### 6. Testdurchführung

##### 6.1 MediaWiki
 - Die Installation ist korrekt abgespeichert, die Grundkonfiguration ist erhalten. Die Startseite ist erreichbar und man kann erfolgreich neue Wikis und Seiten hinzufügen.

##### 6.2 Nextcloud
 - Die Installation ist korrekt abgespeichert, die Grundkonfiguration ist erhalten. Die Startseite ist erreichbar und man kann erfolgreich neue Wikis und Seiten hinzufügen. Benutzerverwaltung ist erreichbar und änderbar, dazu ist auch noch die volle Sicherheit gewährleistet, vor allem weil das Passwort nicht öffentlich sichtbar ist.

##### 6.3 Gogs
 - Installation ist verfügbar und Repositorys sind verfügbar und funktionieren, dazu kann man neue einfach erstellen. Die Seite ist auch erreichbar sowie die Benutzerverwaltung ist verfügbar und funktionsfähig, auch die Sicherheit ist vollkommen gewährleistet, indem das Passwort nicht öffentlich ist.

##### 6.4 Portainer
 - Portainer ist erreichbar und die Verwaltung der Container und der Images ist vollkommen funktionsfähig; dabei sind die Benutzer auch richtig konfiguriert und sichergestellt, dass die Passwörter nicht öffentlich sind.
