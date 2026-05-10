# 🚀 Guide de démarrage rapide

## Prérequis
- Claude Desktop installé
- Node.js 18+
- Git

---

## 1. Configurer Claude Desktop

Le fichier de configuration se trouve à :
- **Windows** : `%APPDATA%\Claude\claude_desktop_config.json`

Exemple de configuration complète avec tous les MCP servers :

```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-filesystem",
        "C:/Users/cecil/projects",
        "D:/claude-ai-agents",
        "D:/projetClaude"
      ]
    },
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "votre_token_github"
      }
    },
    "browser": {
      "command": "npx",
      "args": ["-y", "@playwright/mcp", "--browser", "chromium"]
    }
  }
}
```

---

## 2. Installer les dépendances MCP

```bash
# Installer Playwright et son navigateur
npx playwright install chromium
```

Les autres serveurs MCP sont installés automatiquement via `npx -y`.

---

## 3. Utiliser un agent

1. Ouvrez Claude Desktop
2. Allez dans **Paramètres → Prompts système**
3. Copiez le contenu de `agents/[nom-agent]/system-prompt.md`
4. Commencez votre conversation !

---

## 4. Utiliser un template de prompt

1. Ouvrez le fichier dans `prompts/templates/`
2. Copiez le contenu
3. Remplacez les `{{placeholders}}` par vos valeurs
4. Envoyez à Claude

---

## 5. Suivre un workflow

1. Ouvrez le workflow dans `workflows/examples/`
2. Suivez les étapes dans l'ordre
3. Adaptez les prompts à votre contexte

---

## ❓ Problèmes fréquents

**MCP server ne démarre pas**
→ Vérifiez que Node.js est installé : `node --version`

**GitHub MCP : erreur d'authentification**
→ Vérifiez votre token dans la config et ses permissions

**Browser MCP : navigateur non trouvé**
→ Exécutez `npx playwright install chromium`
