# 🐙 MCP Server — GitHub

Serveur MCP pour interagir avec GitHub depuis Claude Desktop.

## Description
Permet à Claude de :
- Lire les repos, branches, commits
- Créer et gérer des issues
- Créer des pull requests
- Accéder au contenu des fichiers dans les repos
- Gérer les releases

## Installation

```bash
npx -y @modelcontextprotocol/server-github
```

## Configuration dans Claude Desktop
Ajoutez dans votre `claude_desktop_config.json` :

```json
{
  "mcpServers": {
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "votre_token_ici"
      }
    }
  }
}
```

## Créer un token GitHub
1. GitHub → Settings → Developer settings → Personal access tokens
2. Scopes recommandés : `repo`, `read:org`, `read:user`

## ⚠️ Sécurité
Ne committez jamais votre token ! Utilisez des variables d'environnement.
