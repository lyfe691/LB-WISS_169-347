# Skizze
![169Skizze drawio](https://github.com/lyfe691/LB-WISS_169-347/assets/111024477/9afc5e0c-469f-4d20-a6de-f652af23306f)

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
    - Installation vorhanden, Konfiguration ist abgespeichert
    - Startseite Erreichbar
    - Neues Wiki funktioniert und beeinhaltet alle Seite

- **Benutzerverwaltung**
  - Erstellen und Verwalten von Benutzerkonten.
  - Überprüfen der Zugriffsrechte.

  -- **Erwartete Resultate**
    - Benutzer werden erfolgreich erstellt und sind verfügbar
    - Benutzer Berechtigungen funktionieren

- **Datenintegrität und -sicherheit**
  - Testen von Backup- und Wiederherstellungsprozessen.
  - Überprüfen der Datenbankverbindung und -konsistenz.
 
  -- **Erwartete Resultate**
    - Backups werden richtig gespeichert und auch Wiederhergestellt
    - Datenbank ist erreichbar mit allen Daten

##### 4.2 Nextcloud

- **Installation und Grundkonfiguration**
  - Testen der Installation und Grundkonfiguration von Nextcloud.
  - Überprüfen, ob die Weboberfläche zugänglich ist.
  - Hochladen und Teilen von Dateien.
 
  -- **Erwartete Resultate**
    - Installation vorhanden
    - Web-Overlay ist erreichbar
    - Daten werden erfolgreich hochgeladen und gespeichert

- **Benutzerverwaltung**
  - Erstellen und Verwalten von Benutzerkonten.
  - Überprüfen der Zugriffsrechte und Freigabeeinstellungen.
 
  -- **Erwartete Resultate**
    - Benutzer werden richtig erstellt und gespeichert
    - Benutzer Rechte funktionieren

- **Datenintegrität und -sicherheit**
  - Testen von Backup- und Wiederherstellungsprozessen.
  - Überprüfen der Datenbankverbindung und -konsistenz.
 
  -- **Erwartete Resultate**
    - Backup ist erfolgreich gespeichert und auch wiederhergestellt
    - Datenbank ist funktional und konsistent

##### 4.3 Gogs

- **Installation und Grundkonfiguration**
  - Testen der Installation und Grundkonfiguration von Gogs.
  - Überprüfen, ob die Weboberfläche zugänglich ist.
  - Erstellen eines neuen Repositorys.
 
  -- **Erwartete Resultate**
    - Gogs existiert und richtig konfiguiert
    - Gogs ist erreichbar per Browser
    - Repositorys werden gespeichert und richtig erstellt

- **Benutzerverwaltung**
  - Erstellen und Verwalten von Benutzerkonten.
  - Überprüfen der Zugriffsrechte.
 
  -- **Erwartete Resultate**
    - Benutzer können richtig verwaltet und erstellt werden
    - Benutzer haben gewisse berechtigungen die auch funktional sind

- **Datenintegrität und -sicherheit**
  - Testen von Backup- und Wiederherstellungsprozessen.
  - Überprüfen der Datenbankverbindung und -konsistenz.
 
  -- **Erwartete Resultate**
    - Backups funktionieren und werden auch wiederherrgestellt
    - Datenbank verbindent richtig und besteht aus allen daten

##### 4.4 Portainer

- **Installation und Grundkonfiguration**
  - Testen der Installation und Grundkonfiguration von Portainer.
  - Überprüfen, ob die Weboberfläche zugänglich ist.
  - Verwalten von Containern und Images.
 
  -- **Erwartete Resultate**
    - Portrainer ist erfolgreich installiert und die Konfigurationen sind bestehend
    - Weboberfläche von Portrainer ist erreichbar
    - Portrainer steuert und verwaltet jegliche Docker erfolgreich

- **Benutzerverwaltung**
  - Erstellen und Verwalten von Benutzerkonten.
  - Überprüfen der Zugriffsrechte.
 
  -- **Erwartete Resultate**
    - Benutzerkonten sind richtig erreichbar und funktional
    - Benutzer können auf Portrainer zugreifen und sich anmelden

#### 5. Testdurchführung

##### 5.1 MediaWiki
 - Die Installation ist korrekt abgespeichert die Grundkonfiguration sind erhalten. Startseite ist erreiichbar und man kann erfolgreich neue Wikis und Seiten hinzufügen.

##### 5.2 Nextcloud
 - Die Installation ist korrekt abgespeichert die Grundkonfiguration sind erhalten. Startseite ist erreiichbar und man kann erfolgreich neue Wikis und Seiten hinzufügen. Benutzer verwaltung ist erreichbar und änderbar dazu ist auch noch die Volle sicherheit gewährleistet vorallem weil das passwort nicht öffentlich sichtbar ist.

##### 5.3 Gogs
 - Installation ist verfügbar und Repositorys sind verfügbar und funktionieren dazu kann man neue einfach erstellen. Die Seite ist auch erreichbar sowie die Benutzer verwaltung ist verfügbar und funktionsfähig auch die Sicherheit ist vollkommen gewährleistet in dem das Passwort nicht öffentlich ist.

##### 5.4 Portainer
 - Portainer ist erreichbar und die verwaltung der Container und der Images ist vollkommen funktionsfähig dabei sind die Benutzer auch richtig konfiguiert und sichergestellt das die Passwörter nicht öffentlich sind.
   
#### 6. Testabschluss

kommt noch


