## Projektstart mit Docker

### Voraussetzungen

- [Git](https://git-scm.com/) installiert  
- [Docker](https://www.docker.com/) ≥ v20.10 & Docker Compose v2+ installiert

---

### Installation & Start

1. Repository klonen:

   ```bash
   git clone https://github.com/ClaudeMeier/SwissDRG.git
   cd SwissDRG
   ```

2. Umgebungsvariablen-Datei anlegen:

   ```bash
   cp .env.example .env
   ```

   Trage deinen OpenAI API Key in die Datei `.env` ein:

   ```env
   OPENAI_API_KEY=dein_key_hier
   ```

3. Container bauen & starten:

   ```bash
   docker compose build #Erstellung Docker-Image
   docker compose up    #Erstellung Docker-Container

   ```

4. App im Browser öffnen:

   [http://localhost:4520](http://localhost:4520)

---

### Debug

Es kann vorkommen, dass die in `docker-compose.yml` angegebenen Ports auf deinem Computer bereits von anderen Programmen verwendet werden (`4500`, `4510`, `4520`). In diesem Fall kann Docker die Container nicht starten.

#### Ports anpassen

In `docker-compose.yml` können die Host-Ports angepasst werden. Dies muss in den Zeilen
`7`, `14`, `22`, `23` und `27` entsprechend gemacht werden.

   ```yaml
    ports:
      - "4500:4000" # 4500 = Host-Port, 4000 = Container-Port
   ...
    ports:
      - "4510:5000" # 4510 = Host-Port, 5000 = Container-Port
   ...
      args:
        VITE_API_BASE_URL: http://localhost:4500 # 4500 = Host-Port
        VITE_API_CHAT_URL_Chat: http://localhost:4510 # 4510 = Host-Port
   ...
    ports:
      - "4520:80" # 4520 = Host-Port, 80 = Container-Port
   ```

### Docker Konfigurationen

Mit `Control` + `C` kann im Terminal des gestarteten Docker-Containers der laufende Contaier gestoppt werden. Mit `docker compose up` wird dieser anschliessen wieder gestartet. Dabei bleiben die Umgebungsvariabeln bestehen und somit wird **kein** neuer vector-store erstellt. 

Mit `docker compose down` wird der Containert tatächlich gelöscht. Mit `docker compose down --volumes` werden alle Container und Volumes entfernt.
In beiden Fällen wird bei erneuter Container-Erstellung ein neuer vector-store erstellt.

---

### Tests

Tests laufen komplett im Docker-Container, ganz ohne lokale Node-Installation:

im Projekt-Root:

```bash
docker compose build frontend-test
docker compose run --rm frontend-test
```
