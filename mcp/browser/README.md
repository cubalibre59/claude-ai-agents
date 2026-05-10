# 🌐 MCP Server — Browser

Serveur MCP pour contrôler un navigateur web depuis Claude Desktop.

## Description
Permet à Claude de :
- Naviguer sur des pages web
- Extraire du contenu HTML
- Remplir des formulaires
- Faire des captures d'écran
- Automatiser des tâches web (scraping, tests E2E)

## Installation

```bash
# Option 1 : Playwright MCP
npx -y @playwright/mcp

# Option 2 : Puppeteer MCP
npx -y puppeteer-mcp-server
```

## Configuration dans Claude Desktop
Ajoutez dans votre `claude_desktop_config.json` :

```json
{
  "mcpServers": {
    "browser": {
      "command": "npx",
      "args": ["-y", "@playwright/mcp", "--browser", "chromium"]
    }
  }
}
```

## Pré-requis
```bash
npx playwright install chromium
```

## Cas d'usage
- Vérification de pages web
- Tests d'interface utilisateur
- Extraction de données
- Documentation automatique avec captures d'écran
