# Testkonzept V1

- **Erstellt von:** Julian Mauerhofer  
- **Datum:** 11.03.2025  

## 1. Unit Tests
- **Ziel des Tests:** Die einzelnen Units testen.
- **Gewünschte Anforderungen (aktuelle Schätzung):** Jede Funktion soll die sich für Unit-Tests eignet, soll die erwarteten Outputs liefern.
- **Testvorgehen:** Die React App und die einzelnen Komponenten eignen sich gut für Unit-Tests, und wir werden sie damit testen. Falls es beim remote gehosteten LLM ebenfalls Funktionen gibt, die sich für Unit-Tests eignen, erstellen wir für diese ebenfalls Unit-Tests. Ob es geeignete Funktionen geben wird, ist aber noch nicht klar, unter anderem natürlich, weil bei einem LLM der Output nicht vorhersehbar und auch nicht für denselben Input immer derselbe Output ist. 

## 2. Datenbank Tests
In unseren Architekturskizzen gehen wir sehr stark davon aus, dass es keine Datenbank geben wird, weil wir andere Approaches für weit vielversprechender halten. Deswegen werden wir voraussichtlich keine Datenbanktests durchführen.

## 3. Integrationstest
- **Ziel des Tests:** Sicherstellen, dass alle Komponenten, also die React App, API und LLM zusammen reibungslos funktionieren.
- **Gewünschte Anforderungen (aktuelle Schätzung):** 
- Die React-App muss zuverlässig die Anfragen an das LLM senden und die Antworten müssen zuverlässig zurückgesendet und in der Chatbox angezeigt werden.
- **Testvorgehen:** Wir erstellen einen automatisierten Test, der den gesamten Ablauf simuliert: Eine Frage wird in der Chatbox eingegeben, die Anfrage wird an die API und das  LLM weitergeleitet, und die Antwort wird in der App dargestellt. Zudem werden Fehlerfälle (wie Ausfall des LLM-APIs) getestet.


## 4. Installationstest
- **Ziel des Tests:** Überprüfen, dass die Installation und Konfiguration ohne Probleme möglich sind.
- **Gewünschte Anforderungen (aktuelle Schätzung):** Die Installation muss für die Benutzer einfach und verständlich sein. Die Installation der React-App soll fehlerfrei funktionieren.
- **Testvorgehen:** 
- Wir testen die Installation der React App selber auf Windows, Linux und Mac. Ausserdem fragen wir möglicherweise auch Personen mit weniger grossem IT-Wissen, um zu sehen, ob sie es auch könnten. Ob unsere App auch von technisch weniger versierten Personen bedient wird, werden wir in unserem nächsten Kundengespräch herausfinden und basierend darauf entscheiden, ob ein solcher Test sinnvoll ist.


## 5. GUI Test
- **Ziel des Tests:** Sicherstellen, dass das GUI korrekt funktioniert und benutzerfreundlich ist.
- **Gewünschte Anforderungen (aktuelle Schätzung):** Die React-App muss die Medikamententabelle und die Chatbox klar und intuitiv anzeigen. Alle Bedienelemente sollen leicht zugänglich und praktisch zu bedienen sein.
- **Testvorgehen:** 
  - Automatisierte Tests prüfen, ob alle UI-Komponenten wie zum Beispiel die  Tabelle und die Chatbox korrekt geladen und dargestellt werden.
  - Manuelle Tests mit Personen überprüfen die Usability: Navigation, Interaktion und visuelle Klarheit.

## 6. Stress Test
- **Ziel des Tests:** Überprüfen, wie sich das System verhält, wenn die Auslastung hoch ist, um gute Performance sowie Stabilität sicherzustellen.
- **Gewünschte Anforderungen (aktuelle Schätzung):**
- Das System muss auch stabil sein, wenn mehrere Personen es gleichzeitig nutzen, und die Antwortzeit des LLM sollte nicht zu stark zunehmen.
- **Testvorgehen:** 
- Der lokale Teil des Programms, also der lokale Teil der React App, sollte unseren Erwartungen nach keine Probleme haben, für die ein Stresstest nützlich wäre. Wir fokussieren uns deshalb beim Stresstest auf das LLM. Wir führen durch:
  - Simulation hoher Nutzerzahlen, die gleichzeitig die Chatbox nutzen.
  - Überprüfung der Latenz der Antworten und der Stabilität des Systems.


## 7. Usability Test
- **Ziel des Tests:** Überprüfen, ob die Anwendung intuitiv bedienbar ist und von den Mitarbeitern der SwissDRG als gut eingeschätzt wird.
- **Gewünschte Anforderungen (aktuelle Schätzung):** 
- Die App muss klar bedienbar sein, sodass die User bei der SwissDRG ohne viel Zeit mit dem Lesen von Anleitungen zu verbringen, die App sofort nutzen können. Selbstverständlich muss die App auch ohne technische Vorkenntnisse leicht zu bedienen sein. 
- **Testvorgehen:** 
  - Wir suchen Testpersonen mit wenigen technischen Vorkenntnissen und lassen sie die App ausprobieren. Sie sollen die wichtigsten Funktionen wie die Chatbox und die Tabelle ausprobieren.
  - Wir holen direktes Feedback ein, durch Umfragen und durch kurze Interviews der Testpersonen.
  - Wir werten das Feedback aus zur Identifikation von Usability-Problemen und Verbesserungspotenzialen.
 
