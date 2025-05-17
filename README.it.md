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
- Azure Developer CLI (azd)

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

L'applicazione è configurata per il deployment su Azure utilizzando Azure Developer CLI (azd):

1. Accedi ad Azure:
   ```bash
   azd auth login
   ```

2. Inizializza l'ambiente:
   ```bash
   azd init
   ```

3. Esegui il deployment dell'applicazione:
   ```bash
   azd up
   ```

Questo deployerà:
- Frontend su Azure Static Web Apps
- Backend su Azure App Service
- Servizio Azure OpenAI
- Application Insights per il monitoraggio
- Azure Key Vault per i segreti

## Contribuire

I contributi sono benvenuti! Sentiti libero di inviare una Pull Request.

## Licenza

Questo progetto è rilasciato sotto la Licenza MIT - vedi il file LICENSE per i dettagli.
