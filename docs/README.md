# Projektübersicht

## Einführung und Ziele

Dieses Projekt beinhaltet die praktische Anwendung von Backend-Services und Frontend-Clients unter Verwendung von Container-Technologie. Der Fokus liegt auf der Architektur von Container-Umgebungen, den Abhängigkeiten von Services und der Bereitstellung von Diensten mithilfe von Infrastructure as Code (IaC).

## Aufgabenbeschreibung

**Ausgangslage:**
Wir sind damit beauftragt, wichtige Dienste für ein IT-Unternehmen einzurichten, indem du docker-compose zur Verwaltung von Microservices verwendest.

**Anforderungen:**

- MediaWiki auf Port 8085 für interne Zwecke.
- Nextcloud auf Port 8080 für Dateifreigabe und Zusammenarbeit.
- Internes Code-Management mit GitLab oder Gogs.
- Persistente Datenspeicherung über alle Dienste hinweg.
- Überwachung der Dienste mit Portainer.

## Implementierungsschritte (IPERKA-Methode)

1. **Informieren:** Anforderungen sorgfältig analysieren.
2. **Planen:** Einen umfassenden Zeitplan für alle Aufgaben entwickeln.
3. **Entscheiden:**
   - Ein detailliertes Systemübersicht entwerfen.
   - Testverfahren und Sicherheitsmaßnahmen festlegen.
4. **Realisieren:** Jedes Teilsystem mit docker-compose implementieren und Tests dokumentieren.
5. **Kontrollieren und Auswerten:** Abweichungen und Lernergebnisse bewerten.

## Hardware- und Softwareanforderungen

- Mindestens 4GB RAM und 16GB SSD für GitLab; Gogs als ressourcenschonendere Alternative.
- Dienste werden innerhalb einer VirtualBox-Umgebung mit einer Ubuntu-VM implementiert und verwaltet.

## Zusätzliche Informationen

Für detaillierte Implementierungsanleitungen und Ressourcenvorgaben, besuche die [offizielle Dokumentation von Docker](https://docs.docker.com/config/containers/resource_constraints/).
