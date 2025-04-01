# Testkonzept V2

- **Erstellt von:** Julian Mauerhofer  
- **Datum:** 1.04.2025  
- **Version:** V1 
---

## 1. Unit Tests

### Ziel
Überprüfung der Funktionalität einzelner Komponenten (Units) im Frontend und Backend.

### Umfang
- **Frontend:** Tests der React-Komponenten (z. B. Medihub-Tabellenlogik, Medibot-Interaktionen).
- **Backend:** Tests der API-Endpunkte und der Logik zur Aufbereitung der Anfragen an die OpenAI API.
- Einsatz von Testframeworks wie Jest und React Testing Library für das Frontend sowie Mocha/Chai für das Backend.

### Begründung
Unit Tests ermöglichen eine schnelle und isolierte Überprüfung der Kernfunktionen. Sie helfen dabei, Fehler frühzeitig zu erkennen und die Wartbarkeit des Codes zu sichern, ohne den kompletten Systemkontext simulieren zu müssen.

---

## 2. Datenbank Tests

- **Ziel:**  
  Sicherstellen, dass alle Datenspeicherungen korrekt erfolgen – sofern in Zukunft eine Datenbank zum Einsatz kommt.

- **Umfang:**  
 Wird sehr wahrscheinlich nicht getestet, da sehr wahrscheinlich nie eine Datenbank existieren wird.

- **Begründung:**  
  Ohne Datenbank entfällt dieser Testbereich.
---

## 3. Integrationstest

### Ziel
Validierung des Zusammenspiels aller Softwarekomponenten und der korrekten Umsetzung der definierten Use Cases.

### Umfang
 Prüfung der wichtigsten Anwendungsfälle, z. B.:
  - Abfrage von Medikamentendaten über den Medibot.
  - Automatische Weiterleitung der Benutzeranfragen an die OpenAI API.
  - Darstellung und Aktualisierung der Medihub-Tabelle.
- **Spezial- und Grenzfälle:** Testen von unvollständigen oder fehlerhaften Eingaben, extrem langen Datensätzen und Netzwerkunterbrechungen.

### Begründung
Integrationstests gewährleisten, dass die Interaktion zwischen Frontend, Backend und externen Schnittstellen (OpenAI API) reibungslos funktioniert. Durch realitätsnahe Testszenarien wird das Gesamtsystem unter praxisnahen Bedingungen validiert.

---

## 4. Installationstest

### Ziel
Überprüfung der korrekten Installation und Konfiguration der Software auf verschiedenen Systemen.

### Umfang
- **Systeme:** Tests auf den gängigen Betriebssystemen (Windows, macOS, Linux).
- **Prozesse:** Durchführung der Installation anhand der bereitgestellten Installationsanweisungen, gefolgt von einem Funktionstest der Grundkomponenten.

### Begründung
Ein reibungsloser Installationsprozess ist essenziell für die nützlichkeit unseres tools. Durch Tests auf verschiedenen Plattformen stellen wir sicher, dass unsere Software in auf den grossen Betriebssystemen ohne Probleme läuft.

---

## 5. GUI Test

### Ziel
Sicherstellen, dass die grafische Benutzeroberfläche den Anwendern eine intuitive und fehlerfreie Bedienung ermöglicht.

### Umfang
- **Testverfahren:** 
  - Automatisierte Tests für kritische UI-Komponenten (z. B. Klick-Aktionen, Formulareingaben) mit Tools wie Jest und Testing Library.
- **Testfälle:** Überprüfung von Responsivität, Fehleranzeigen und interaktiven Elementen (z. B. Rechtsklick zur Öffnung des Medibot).

### Begründung
Wir wollen diese Tests ebenfalls automatisiert durchführen, da sie so immer wieder wiederholt werden können, auch wenn dies einen grösseren initialen Aufwand bedeutet.

---

## 6. Stress-Tests

- **Ziel:**  
  Überprüfen, ob die Software auch unter hoher Last stabil bleibt.

- **Umfang:**  
    - Aufgrund der geringen Nutzerzahlen und der seltenen Nutzung wäre höchstens ein kleiner Stress-Test denkbar. Wahrscheinlich wird aber gar keiner durchgeführt. 

- **Begründung:**  
  Nur sehr wenige Mitarbeiter der SwissDRG werden unsere Software nutzen und ihre Nutzung wird selten sein. Noch unwahrscheinlicher ist es, dass alle Nutzer das System gleichzeitig nutzen. Deswegen halten wir es für sinnvoller, unsere Zeit in andere Test-Arten zu investieren, um das Produkt möglichst gut zu machen.


---

## 7. Usability-Test

### Ziel
Ermittlung der Bedienbarkeit und Anwenderfreundlichkeit der Software aus Sicht der Endbenutzer.

### Umfang
- **Zielgruppe:** Mitarbeiter der SwissDRG mit medizinischem, aber nicht zwingend technischem Vorwissen
- **Testverfahren:** 
  - Wir bitten verschiedene Personen, auch solche ohne technische fachkentnisse, unser tool auszuprobieren. Falls sie schwierigkeiten mit der Bedienung haben, passen wir das tool entsprechend an.
  
### Begründung
Dieser Test muss manuell erfolgen. Da die SwissDRG leider nicht viel kapazitäten hat um unser tool zu testen, werden wir die Usability-Tests mit Personen durchführen, die nicht bei der SwissDRG arbeiten. Da für diese Tests keine medizinische Vorkenntnisse erforderlich sind, sollte dies kein Problem darstellen.

---
