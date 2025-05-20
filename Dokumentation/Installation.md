# Lockale Installtion ohne Docker

Diese Anleitung beschreibt die lokale Ausführung des Projekts ohne Docker. Alle Komponenten werden manuell gestartet. Die Anleitung gilt für **macOS**, **Linux** und **Windows**.

---

## SetUp für Development

### Voraussetzungen:
Folgende Software/Technologien müssen installiert sein:
- Git : https://git-scm.com/downloads
- Node.js (mit npm): https://nodejs.org/en/download
- Python 3 (>= 3.8): https://www.python.org/downloads
- pip (Python Package Installer)


### 1. Repository klonen

```bash
git clone https://github.com/ClaudeMeier/SwissDRG.git
cd SwissDRG
````

### 2. Umgebungsvariablen anlegen

Erstelle in `backend/ChatBot/` ein `.env` file mit:
```js
OPENAI_API_KEY=your_openai_key_here
PORT=4510
````

Erstelle in `backend/core-server/` ein `.env` file mit:
```js
PORT=4500
````

Erstelle in `frontend/` ein `.env` file mit:
```js
VITE_API_BASE_URL=http://localhost:4500
VITE_API_CHAT_URL_Chat=http://localhost:4510
````


### 3. Backend starten
3.1 Core-Server (Node.js)

Erstelle ein Terminal im Projektordner:
```bash
cd backend/core-server
npm install
npm start
````
3.2 ChatBot-Sever (Python)

Erstelle ein weiteres Terminal im Projektordner:
```bash
cd backend/chatBot
python3 -m venv venv

# MacOS & Linux
source venv/bin/activate 

# Windows (cmd): 
venv\Scripts\activate

# Windows (PowerShell): 
.\venv\Scripts\Activate.ps1

pip3 install flask flask-cors python-dotenv openai openai-agents # Alternativ: pip install -r requirements.txt
python3 config_fileSearch/filesearch_agent_init.py # Einmalige erstellung von vector-store
python3 server.py
````

### 4. Frontend starten
Erstelle ein weiteres Terminal im Projektordner:
```bash
cd frontend
npm install
npm run dev -- --port=4520
````

Das Projekt läuft nun im Dev-Mode:

- backend/core-server auf Port :  4500
- backend/chatBot auf Port :      4510
- frontend und damit die Applikation auf : http://localhost:4520.

## Debug und Konfiguration

Es kann vorkommen, dass angegebenen Ports bereits von anderen Programmen auf dem Computer verwendet werden (`4500`, `4510`, `4520`).
In diesem Falle müssen die Ports in der obigen Anleitung selbst angepasst werden.


---

## SetUp fürs Deployment

### Voraussetzungen:
Folgende Software/Technologien müssen installiert sein:
- Git : https://git-scm.com/downloads
- Node.js (mit npm): https://nodejs.org/en/download
- Python 3 (>= 3.8): https://www.python.org/downloads
- pip (Python Package Installer)


### 1. Repository klonen

```bash
git clone https://github.com/ClaudeMeier/SwissDRG.git
cd SwissDRG
````

### 2. Umgebungsvariablen anlegen

Erstelle in `backend/ChatBot/` ein `.env` file mit:
```js
OPENAI_API_KEY=your_openai_key_here
````

Erstelle in `backend/core-server/` ein `.env` file mit:
```js
PORT=4500
````

Erstelle in `frontend/` ein `.env` file mit:
```js
VITE_API_BASE_URL=http://localhost:4500
VITE_API_CHAT_URL_Chat=http://localhost:4510
````


### 3. Backend starten
3.1 Core-Server (Node.js)

Erstelle ein Terminal im Projektordner:
```bash
cd backend/core-server
npm install
npm start
````
3.2 ChatBot-Sever (Python)

Erstelle ein weiteres Terminal im Projektordner:
```bash
cd backend/chatBot
python3 -m venv venv

# MacOs & Linux
source venv/bin/activate 

# Windows (cmd): 
venv\Scripts\activate

# Windows (PowerShell): 
.\venv\Scripts\Activate.ps1

pip install -r requirements.txt
python3 config_fileSearch/filesearch_agent_init.py

# MacOS & Linux
gunicorn -b 0.0.0.0:4510 server:app --timeout 120 

# Windows (cmd oder PowerShell): 
python server.py
````

### 4. Frontend starten
Erstelle ein weiteres Terminal im Projektordner:
```bash
cd frontend
npm install
npm run build
npx serve -s dist -l 4520
````

Das Projekt läuft nun:

- backend/core-server auf Port :  4500
- backend/chatBot auf Port :      4510
- frontend und damit die Applikation auf : http://localhost:4520.

## Debug und Konfiguration

Es kann vorkommen, dass angegebenen Ports bereits von anderen Programmen auf dem Computer verwendet werden (`4500`, `4510`, `4520`).
In diesem Falle müssen die Ports in der obigen Anleitung selbst angepasst werden.
