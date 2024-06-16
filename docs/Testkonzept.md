# Skizze, wird später noch verbessert
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

- **Benutzerverwaltung**
  - Erstellen und Verwalten von Benutzerkonten.
  - Überprüfen der Zugriffsrechte.

- **Datenintegrität und -sicherheit**
  - Testen von Backup- und Wiederherstellungsprozessen.
  - Überprüfen der Datenbankverbindung und -konsistenz.

##### 4.2 Nextcloud

- **Installation und Grundkonfiguration**
  - Testen der Installation und Grundkonfiguration von Nextcloud.
  - Überprüfen, ob die Weboberfläche zugänglich ist.
  - Hochladen und Teilen von Dateien.

- **Benutzerverwaltung**
  - Erstellen und Verwalten von Benutzerkonten.
  - Überprüfen der Zugriffsrechte und Freigabeeinstellungen.

- **Datenintegrität und -sicherheit**
  - Testen von Backup- und Wiederherstellungsprozessen.
  - Überprüfen der Datenbankverbindung und -konsistenz.

##### 4.3 Gogs

- **Installation und Grundkonfiguration**
  - Testen der Installation und Grundkonfiguration von Gogs.
  - Überprüfen, ob die Weboberfläche zugänglich ist.
  - Erstellen eines neuen Repositorys.

- **Benutzerverwaltung**
  - Erstellen und Verwalten von Benutzerkonten.
  - Überprüfen der Zugriffsrechte.

- **Datenintegrität und -sicherheit**
  - Testen von Backup- und Wiederherstellungsprozessen.
  - Überprüfen der Datenbankverbindung und -konsistenz.

##### 4.4 Portainer

- **Installation und Grundkonfiguration**
  - Testen der Installation und Grundkonfiguration von Portainer.
  - Überprüfen, ob die Weboberfläche zugänglich ist.
  - Verwalten von Containern und Images.

- **Benutzerverwaltung**
  - Erstellen und Verwalten von Benutzerkonten.
  - Überprüfen der Zugriffsrechte.

#### 5. Testdurchführung

kommt nocj
#### 6. Testabschluss

kommt noch


