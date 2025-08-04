```
██████   █████  ████████  █████  ██████  ██████  ██  ██████ ██   ██ ███████ 
██   ██ ██   ██    ██    ██   ██ ██   ██ ██   ██ ██ ██      ██  ██  ██      
██   ██ ███████    ██    ███████ ██████  ██████  ██ ██      █████   ███████ 
██   ██ ██   ██    ██    ██   ██ ██   ██ ██   ██ ██ ██      ██  ██       ██ 
██████  ██   ██    ██    ██   ██ ██████  ██   ██ ██  ██████ ██   ██ ███████ 
```

# dbx-cli: Databricks Command Line AI Assistant



**dbx-cli** is a community fork of [Google's Gemini CLI](https://github.com/google-gemini/gemini-cli) that extends support to Databricks foundational models. Built with the excellent Gemini CLI architecture, it brings the power of Databricks AI to your terminal while maintaining full compatibility with the original interface.

## Fork Attribution

This project is a fork of the official [Google Gemini CLI](https://github.com/google-gemini/gemini-cli), licensed under the Apache License 2.0. We maintain attribution to the original authors and comply with all license requirements. This is an independent community project and is not affiliated with or endorsed by Google.

## Key Features

With dbx-cli you can:

- **Access Databricks Models**: Connect directly to your Databricks serving endpoints

## Installation

### Prerequisites

- [Node.js version 20](https://nodejs.org/en/download) or higher
- A Databricks workspace with deployed serving endpoints
- A Databricks Personal Access Token (PAT)

### Install from npm

```bash
npm install -g @dbx-cli/cli
```

Then run the CLI from anywhere:

```bash
dbx
```

## Quick Start

### 1. Configure Databricks Authentication

Set your Databricks workspace URL and Personal Access Token:

```bash
export DATABRICKS_URL="https://your-workspace.databricks.com"
export DBX_PAT="your_personal_access_token"
```

Or configure interactively within the CLI:

```bash
dbx
> /databricks set --url=https://your-workspace.databricks.com --pat=your_token
> /databricks enable
```

### 2. Select a Model

The default model is `databricks-claude-sonnet-4`. To see available models in your workspace:

```bash
> /model list
```

To change the model:

```bash
> /model set databricks-meta-llama-3-3-70b-instruct
```

### 3. Start Using dbx-cli

Now you're ready to interact with your Databricks models:

```bash
> Write a Python function to analyze customer churn
> Explain how Unity Catalog works
> Help me optimize this Spark query
```

## Authentication Options

dbx-cli supports multiple authentication methods through the `/auth` command:

### Databricks (Recommended for this fork)

Configure your Databricks credentials as shown above, then:

```bash
> /auth
# Select "Databricks" from the menu
```

### Other Supported Providers

The fork maintains support for all original authentication methods:

- **Google OAuth**: Sign in with your Google account
- **Gemini API Key**: Use a key from [Google AI Studio](https://aistudio.google.com/apikey)
- **Vertex AI**: Use Google Cloud credentials

For detailed authentication options, see the [authentication guide](./docs/cli/authentication.md).

## Databricks-Specific Commands

### `/databricks` (aliases: `/dbx`, `/db`)

Manage your Databricks connection:

```bash
# Show current configuration
> /databricks show

# Set credentials
> /databricks set --url=https://workspace.databricks.com --pat=your_token

# Enable Databricks authentication
> /databricks enable

# Clear configuration
> /databricks clear
```

### `/model`

Manage model selection:

```bash
# Show current model
> /model show

# List available models (dynamically fetched from your workspace)
> /model list

# Set a different model
> /model set databricks-llama-4-maverick

# Refresh model list from workspace
> /model refresh
```

### `/auth`

Switch between authentication providers:

```bash
> /auth
# Interactive menu to select between Databricks, Gemini, Vertex AI, or Google OAuth
```

## Contributing

We welcome contributions! This is a community project focused on enhancing Databricks support. Please:

1. Focus PRs on Databricks-related functionality
2. Maintain compatibility with the original Gemini CLI
3. Include tests for new features
4. Update documentation as needed



## Uninstall

To uninstall dbx-cli:

```bash
npm uninstall -g @dbx-cli/cli
```


## License & Attribution

This project is licensed under the Apache License 2.0, the same as the original Google Gemini CLI. We maintain full attribution to the original authors and comply with all license requirements.

**Important**: This is an independent community fork and is not affiliated with, endorsed by, or supported by Google or Databricks.
