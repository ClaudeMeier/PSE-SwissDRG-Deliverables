#  Sitzungsprotokoll 27.02  – Kundenmeeting SwissDRG AG

**Datum:**   27.02 <br>
**Uhrzeit:** 16:15 – ca.17:30 <br>
**Ort:**   Länggassstrasse 31, 3012 Bern <br>
**Sitzungsleiter:** Dimoth, Seva <br>
**Protokollführerin:** Anjaly  <br>
**Teilnehmer*innen:** Felix, Samuel, Florin, Dimoth, Seva, Claude, Julian, Anjaly

---

## 1️ Einführung & Ziel des Projekts
- **Vorstellung SwissDRG AG:** SwissDRG berechnet Fallpauschalen für Spitäler und Versicherungen im Bereich Medikamentenkosten.
- **Herausforderung:** Neue und teure Medikamente (z. B. 80.000 CHF pro Einheit) müssen klassifiziert und in bestehende Systeme eingegliedert werden.
- **Projektziel:** Entwicklung eines spezialisierten OpenLLaMA-Modells, das als Chatbot in einer React-Komponente integriert wird, um strukturierte Medikamentendaten aus verschiedenen Quellen (z. B. BAG, ATC-Codes der WHO) abzurufen und zu nutzen

---

## 2️ Projektumfang & Meilensteine

###  2.1 Erste Iteration: Exploration & Datenanalyse
- Identifikation relevanter **Datenquellen** (z. B. BAG-Datenbank)  
- Entscheidung über **LLM-Modell**  
- Einrichtung von Entwicklungsumgebungen (**Colab, Hugging Face**)

### 2.2 Entwicklung des Systems
1. **Modellauswahl & Training**
2. **Software-Architektur** definieren & Infrastruktur aufbauen
3. **Implementierung** einer React-Komponente für UI
4. **Integration** der Modelle & Testphase

#### Anforderungen für UI
- Textsuche
- Sortierbare Spalten
- Durchsuchbare Medikamentenliste

---

## 3️ Technische Details & Umsetzung
- **Datenquellen:** BAG-Datenbank (Medikamentenzulassungen, Indikationen)
- **Modelloptionen:** Erste Überlegung: LLaMA, weitere Tests mit anderen Modellen
- **Plattform für Modelltraining:** Google Colab oder alternative Serverlösung von SwissDRG
- **Hosting des Modells:** Möglichst auf einer skalierbaren Infrastruktur
- **Entwicklung mit React:** SwissDRG setzt bereits auf React-Komponenten

---

## 4️ Organisatorische Punkte
### Kommunikation
- **WhatsApp für internes Team**
- **Slack** für direkten **Austausch mit SwissDRG**
- **GitHub & Notion für Dokumentation und Projektmanagement**

### Budget
- **Kleiner dreistelliger Betrag** insgesamt
- Google Colab kostet ca. 10 Euro pro Monat

###  Evaluierung durch SwissDRG
- Messung der **Effektivität** (z. B. wie viel Arbeitszeit das System einspart)
- Falls nur minimale Einsparungen → keine Weiterführung des Projekts

---

## 5️ Nächste Schritte bis zum nächsten Meeting
**Bis zur nächsten Sitzung (in 2 Wochen, 16:15 Uhr, gleicher Ort) sollen folgende Punkte geklärt werden:**
- Entscheidung über **Modellwahl & Datenquelle**
- Grobe **Bereinigung und Strukturierung der Daten**
- Klärung der **LLM-Tuning-Strategie**
- Erstellung eines **Slack-Workspaces mit dem Kunden**
- Freischaltung des **Notion-Boards für SwissDRG**
- Entscheidung über **Google Colab oder alternative Infrastruktur**

**Buchempfehlung für das Team:** „Hands-on Natural Language Processing“ (O'Reilly) 
