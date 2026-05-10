# 📁 MCP Server — Filesystem

Serveur MCP pour accéder et manipuler le système de fichiers local depuis Claude Desktop.

## Description
Permet à Claude d'accéder à vos fichiers locaux pour :
- Lire et écrire des fichiers
- Lister des répertoires
- Rechercher dans les fichiers

## Installation

```bash
npx -y @modelcontextprotocol/server-filesystem
```

## Configuration dans Claude Desktop
Ajoutez dans votre `claude_desktop_config.json` :

```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "C:/Users/cecil/projects", "D:/claude-ai-agents"]
    }
  }
}
```

## ⚠️ Sécurité
Ne donnez accès qu'aux répertoires nécessaires. Évitez d'exposer des répertoires système.
