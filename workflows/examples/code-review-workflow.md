# Workflow — Revue de code avec Claude

## Vue d'ensemble
Ce workflow guide la revue d'une Pull Request ou d'un fichier de code avec l'aide du coding-agent.

## Durée estimée : 15–30 min

---

## Étape 1 — Préparer le contexte

**Prompt à envoyer :**
```
Je vais te soumettre du code pour une revue. Voici le contexte du projet :
- Framework : [Symfony 7 / Angular 17]
- Objectif du code : [description]
- Branche / PR : [nom de la branche]
Prêt à commencer ?
```

---

## Étape 2 — Soumettre le code

Utilisez le template `prompts/templates/code-review.md` en collant votre code.

---

## Étape 3 — Itérer sur les suggestions

**Prompt de suivi :**
```
Pour le problème [X] que tu as identifié, peux-tu :
1. Expliquer pourquoi c'est problématique
2. Montrer la version corrigée
3. Ajouter un test unitaire pour valider la correction
```

---

## Étape 4 — Valider les corrections

**Prompt de validation :**
```
Voici le code corrigé suite à tes suggestions. Confirme que les problèmes
identifiés sont bien résolus et signale tout nouveau point d'attention :
[code corrigé]
```

---

## Checklist finale
- [ ] Tous les problèmes critiques sont résolus
- [ ] Les tests couvrent les nouveaux cas
- [ ] La documentation est à jour
- [ ] Le code respecte les conventions du projet
