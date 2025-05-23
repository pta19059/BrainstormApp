# Business Brainstorming App

A modern web application that helps generate and develop business ideas using Azure OpenAI services.

## Overview

This application combines React, TypeScript, and Tailwind CSS for the frontend with a Node.js/Express backend, leveraging Azure OpenAI to generate innovative business ideas.

## Project Structure

```
├── frontend/               # React TypeScript frontend application
│   ├── src/               # Source code
│   │   ├── components/    # React components
│   │   └── ...           # Other frontend source files
│   └── package.json       # Frontend dependencies
├── api-server/            # Node.js/Express backend
│   ├── src/              # Source code
│   │   ├── routes/       # API routes
│   │   └── server.ts     # Server configuration
│   └── package.json      # Backend dependencies
└── infra/                # Azure infrastructure as code
    ├── main.bicep        # Main infrastructure definition
    └── main.parameters.json # Infrastructure parameters
```

## Features

- Modern, responsive UI with Tailwind CSS
- Real-time business idea generation
- TypeScript for enhanced code quality
- Azure OpenAI integration for AI-powered suggestions
- Secure and scalable Azure cloud deployment

## Prerequisites

- Node.js 18 or later
- Azure subscription
- Azure CLI
- Visual Studio Code with the "Azure Tools" extension pack

## Local Development

1. Clone the repository
2. Install dependencies:
   ```bash
   # Install frontend dependencies
   cd frontend
   npm install

   # Install backend dependencies
   cd ../api-server
   npm install
   ```

3. Set up environment variables:
   ```bash
   # Frontend
   REACT_APP_API_URL=http://localhost:3001

   # Backend
   AZURE_OPENAI_API_KEY=your-api-key
   AZURE_OPENAI_API_ENDPOINT=your-endpoint
   AZURE_OPENAI_API_MODEL=gpt-35-turbo
   ```

4. Start the development servers:
   ```bash
   # Start frontend (in frontend directory)
   npm start

   # Start backend (in api-server directory)
   npm run dev
   ```

## Deployment

The recommended way to deploy this application is using Visual Studio Code and the "Deploy to Web App" feature:

1. **Create Azure Resources:**
   - Use the Azure portal or the Azure Tools extension in VS Code to create:
     - An Azure Web App for the backend (Node.js)
     - An Azure Web App or Azure Static Web App for the frontend (React)
     - An Azure OpenAI resource
     - Azure Key Vault (for secrets)
     - (Optional) Application Insights for monitoring

2. **Configure Environment Variables:**
   - For the backend (App Service): set the following Application Settings in Azure:
     - `AZURE_OPENAI_ENDPOINT` = your Azure OpenAI endpoint
     - `AZURE_OPENAI_KEY` = your Azure OpenAI key
     - `AZURE_OPENAI_DEPLOYMENT` = your deployment name (e.g. gpt-4)
     - `PORT` = 3001 (or as needed)
   - For the frontend: set the environment variable in `.env`:
     - `REACT_APP_API_URL=https://<your-backend-app-name>.azurewebsites.net/api`

3. **Update API URL in Code:**
   - In `frontend/src/App.tsx`, replace any hardcoded API URLs with:
     ```js
     const apiUrl = process.env.REACT_APP_API_URL + '/api/generate';
     ```
     Or use the environment variable directly.

4. **Deploy from VS Code:**
   - Open the frontend and backend folders in VS Code.
   - Right-click the project folder and select **Deploy to Web App** (for both frontend and backend).
   - Follow the prompts to select the correct Azure resources.

5. **Verify Deployment:**
   - Visit the URLs of your deployed frontend and backend to ensure everything works.

For more details, see the [Azure Tools for VS Code documentation](https://learn.microsoft.com/en-us/azure/developer/vscode/).

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the LICENSE file for details.
