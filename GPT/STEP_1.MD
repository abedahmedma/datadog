Cosmos DB doit être en auto scaling 

Prérequis
├── Techniques
│   ├── Activer les resources provider
│   ├── S'assurer de l'éligibilité à Azure Open AI
│   ├── Avoir les droits sur le groupe de ressources
│   └── Disposer d'une app registration
├── Métiers
│   ├── Définir le nom du bot
│   └── Définir les fonctionnalités et personnalisations
└──

Complémentaires
    └── Valider les paramètres réseau

Préparation de la livraison
├── Configuration de l'application Azure AD
│   ├── Copier la valeur Application (client) ID
│   ├── Créer un rôle BYOD
│   └── Créer un secret client
├── Création d'une nouvelle branche releases/<client>
├── Publication de l'image Docker
│   ├── Exécuter le pipeline Docker Publish
│   ├── Créer un scope map
│   └── Créer un token
└── [Optionnel] Déploiement de Bing Search



==========================================================

Prerequisites
│   ├── Enable Open AI service deployment
│   ├── Enable Azure resource providers

Deployment
│   ├── Create a Bing search tier S2 resource
│   ├── Configure the app registration
│   ├── Create a Docker image
│   └── Deploy infrastructure and application

Configuration
│   ├── Enable/disable application features
│   └── Integrate SharePoint and Azure Cognitive Search


==========================================================
Enable Resource providers : 
│   ├── Microsoft.OperationalInsights
│   ├── Microsoft.Bing
│   ├── Microsoft.CognitiveServices
│   ├── microsoft.insights
│   ├── Microsoft.AppConfiguration
│   ├── Microsoft.Web
│   └── Microsoft.DocumentDB



Configure Azure AD Application Registration for GPT 4 Enterprise
│   ├── Create Application
│   │   ├── Connect to Entra
│   │   ├── Invite External Users to Administer Application
│   │   ├── Create Application Registration
│   │   ├── Name Application SPN_<application>
│   │   ├── Select Single Tenant Mode
│   │   └── Leave Redirect URI Field Empty
│   ├── Define Owners
│   │   ├── In Owners Menu, Click Add Owners
│   │   ├── Select Accounts to Administer Application
│   │   └── Click Select
│   └── Assign API Permissions
│       ├── In API Permissions Menu, Click Grant Admin Consent for <tenant>
│       └── Click Yes

Prepare GPT 4 Enterprise Delivery
│   ├── Configure Azure AD Application
│   │   ├── Copy Application (client) ID
│   │   ├── Create App Role (BYOD)
│   │   ├── Generate Client Secret
│   ├── Initialize Container Registry
│   │   ├── Run Docker Publish Pipeline
│   │   ├── Create Scope Map (<client>-pull)
│   │   ├── Create Token (<client>-pull-devops)
│   │   └── Generate Token Password
│   ├── Deploy Bing Search (Optional)
│   │   ├── Create Bing Search Resource
│   │   ├── Copy Bing Search API Key
│   ├── Apply Client Customizations
│   ├── Commit/Pull Request to /releases/<client> Branch
│   └── Rerun Docker Publish Pipeline (without -alpha)
│       ├── Update Parameters File (<client>-gpt.parameters.json)
│       │   ├── Set applicationVersion
│       │   ├── Set AzureAdClientId
│       │   ├── Set AzureAdClientSecret
│       │   ├── Set containerRegistryPassword
│       │   ├── Set projectShortName
│       │   ├── Set containerRegistryUser
│       │   ├── Set AzureAdDomain
│       │   └── Set BingSearchApiKey (or "-")
│       └── Deploy Application to Client


Deploy GPT 4 Enterprise to Client
│   ├── Verify Prerequisites
│   │   ├── Check Successful Completion of 0 - Prerequisites and 1 - Preparation
│   │   ├── Ensure Azure CLI Installed
│   │   ├── Verify Repository Cloned and releases/<client> Branch Checked Out
│   │   └── Validate Existence of /path-gpt.parameters.json File
│   ├── Execute Deployment Procedure
│   │   ├── Open PowerShell Command Prompt
│   │   ├── Navigate to Solution Directory
│   │   ├── Connect to Azure with 'az login' Command
│   │   └── Set Client Subscription with 'az account set' Command
│   │       ├── Deploy Application Infrastructure
│   │       │   ├── Create Resource Group with 'az deployment group create' Command
│   │       │   ├── Utilize main.bicep Template File
│   │       │   └── Specify Parameters/client-gpt.parameters.json File
│   │       └── Validate Deployment Success in Resource Group Deployments Menu
│   ├── Retrieve App Service Default Domain
│   ├── Configure Azure AD Application for App Service Default Domain
│   │   ├── Open App Registration in AD - App registration
│   │   ├── Navigate to Authentication Menu and Click Add Platform
│   │   ├── Select Web Platform and Enter Default Domain in Redirect URIs
│   │   └── Click Configure Button
│   └── Create New Work Item in Project Backlog
│       ├── Specify Client Name, Application Version, and Delivery Date
│       ├── Describe Deployment Tasks
│       └── Assign Work Item to Responsible Individuals




