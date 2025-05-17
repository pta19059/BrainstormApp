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
- Azure Developer CLI (azd)

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

The application is configured for deployment to Azure using Azure Developer CLI (azd):

1. Login to Azure:
   ```bash
   azd auth login
   ```

2. Initialize the environment:
   ```bash
   azd init
   ```

3. Deploy the application:
   ```bash
   azd up
   ```

This will deploy:
- Frontend to Azure Static Web Apps
- Backend to Azure App Service
- Azure OpenAI service
- Application Insights for monitoring
- Azure Key Vault for secrets

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the LICENSE file for details.
