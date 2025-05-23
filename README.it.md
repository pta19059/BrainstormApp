# App per il Brainstorming Aziendale

Un'applicazione web moderna che aiuta a generare e sviluppare idee di business utilizzando i servizi Azure OpenAI.

## Panoramica

Questa applicazione combina React, TypeScript e Tailwind CSS per il frontend con un backend Node.js/Express, sfruttando Azure OpenAI per generare idee di business innovative.

## Struttura del Progetto

```
├── frontend/               # Applicazione frontend in React TypeScript
│   ├── src/               # Codice sorgente
│   │   ├── components/    # Componenti React
│   │   └── ...           # Altri file sorgente frontend
│   └── package.json       # Dipendenze frontend
├── api-server/            # Backend Node.js/Express
│   ├── src/              # Codice sorgente
│   │   ├── routes/       # Route API
│   │   └── server.ts     # Configurazione server
│   └── package.json      # Dipendenze backend
└── infra/                # Infrastruttura Azure come codice
    ├── main.bicep        # Definizione principale dell'infrastruttura
    └── main.parameters.json # Parametri dell'infrastruttura
```

## Caratteristiche

- UI moderna e responsive con Tailwind CSS
- Generazione di idee di business in tempo reale
- TypeScript per una migliore qualità del codice
- Integrazione con Azure OpenAI per suggerimenti basati su AI
- Deployment sicuro e scalabile su cloud Azure

## Prerequisiti

- Node.js 18 o successivo
- Sottoscrizione Azure
- Azure CLI
- Visual Studio Code con l'estensione "Azure Tools"

## Sviluppo Locale

1. Clona il repository
2. Installa le dipendenze:
   ```bash
   # Installa le dipendenze frontend
   cd frontend
   npm install

   # Installa le dipendenze backend
   cd ../api-server
   npm install
   ```

3. Configura le variabili d'ambiente:
   ```bash
   # Frontend
   REACT_APP_API_URL=http://localhost:3001

   # Backend
   AZURE_OPENAI_API_KEY=tua-api-key
   AZURE_OPENAI_API_ENDPOINT=tuo-endpoint
   AZURE_OPENAI_API_MODEL=gpt-35-turbo
   ```

4. Avvia i server di sviluppo:
   ```bash
   # Avvia il frontend (nella directory frontend)
   npm start

   # Avvia il backend (nella directory api-server)
   npm run dev
   ```

## Deployment

Il modo consigliato per pubblicare questa applicazione è tramite Visual Studio Code e la funzione "Deploy to Web App":

1. **Crea le risorse Azure:**
   - Usa il portale Azure o l'estensione Azure Tools di VS Code per creare:
     - Una Azure Web App per il backend (Node.js)
     - Una Azure Web App o Azure Static Web App per il frontend (React)
     - Una risorsa Azure OpenAI
     - Azure Key Vault (per i segreti)
     - (Opzionale) Application Insights per il monitoraggio

2. **Configura le variabili d'ambiente:**
   - Per il backend (App Service): imposta le Application Settings in Azure:
     - `AZURE_OPENAI_ENDPOINT` = il tuo endpoint Azure OpenAI
     - `AZURE_OPENAI_KEY` = la tua chiave Azure OpenAI
     - `AZURE_OPENAI_DEPLOYMENT` = il nome del deployment (es. gpt-4)
     - `PORT` = 3001 (o altro se necessario)
   - Per il frontend: imposta la variabile d'ambiente in `.env`:
     - `REACT_APP_API_URL=https://<nome-backend-app>.azurewebsites.net/api`

3. **Aggiorna l'URL API nel codice:**
   - In `frontend/src/App.tsx`, sostituisci eventuali URL API hardcoded con:
     ```js
     const apiUrl = process.env.REACT_APP_API_URL + '/api/generate';
     ```
     Oppure usa direttamente la variabile d'ambiente.

4. **Deploy da VS Code:**
   - Apri le cartelle frontend e backend in VS Code.
   - Clicca col destro sulla cartella del progetto e seleziona **Deploy to Web App** (sia per frontend che per backend).
   - Segui le istruzioni per selezionare le risorse Azure corrette.

5. **Verifica il deployment:**
   - Visita gli URL del frontend e backend pubblicati per verificare che tutto funzioni.

Per maggiori dettagli, consulta la [documentazione di Azure Tools per VS Code](https://learn.microsoft.com/it-it/azure/developer/vscode/).

## Contribuire

I contributi sono benvenuti! Sentiti libero di inviare una Pull Request.

## Licenza

Questo progetto è rilasciato sotto la Licenza MIT - vedi il file LICENSE per i dettagli.
