# 🏛️ Architecture du projet

## Vue d'ensemble

```
claude-ai-agents/
├── agents/          # Définitions des agents IA (prompts + configs)
├── mcp/             # Configurations des serveurs MCP
├── prompts/         # Templates de prompts réutilisables
├── workflows/       # Processus de développement assistés par IA
└── docs/            # Documentation du projet
```

---

## Composants

### 🤖 Agents
Les agents sont des configurations d'IA spécialisées.
Chaque agent contient :
- `system-prompt.md` : Le prompt système qui définit le comportement
- `config.json` : Paramètres (modèle, température, outils autorisés)
- `README.md` : Documentation de l'agent

**Agents disponibles :**
| Agent | Spécialité |
|-------|-----------|
| `coding-agent` | Développement généraliste |
| `symfony-agent` | PHP / Symfony |
| `angular-agent` | TypeScript / Angular |

---

### ⚙️ MCP Servers
Les serveurs MCP étendent les capacités de Claude avec des outils externes.

**Servers disponibles :**
| Server | Rôle |
|--------|------|
| `filesystem` | Accès aux fichiers locaux |
| `github` | Interaction avec GitHub |
| `browser` | Navigation web automatisée |

---

### 📝 Prompts
Templates réutilisables pour des tâches courantes.
Placeholders au format `{{nom_du_placeholder}}`.

---

### ⚙️ Workflows
Séquences d'étapes guidées pour des tâches complexes.
Chaque workflow inclut des prompts pré-rédigés et des checklists.

---

## Flux de travail typique

```
Utilisateur
    │
    ▼
Claude Desktop (avec system-prompt de l'agent)
    │
    ├── MCP Filesystem ──► Lecture/écriture fichiers locaux
    ├── MCP GitHub ───────► Issues, PRs, repos
    └── MCP Browser ──────► Navigation web, scraping
```
