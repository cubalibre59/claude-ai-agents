# Workflow — Déploiement assisté par Claude

## Vue d'ensemble
Ce workflow guide le déploiement d'une application avec vérifications assistées par IA.

## Durée estimée : 30–60 min

---

## Étape 1 — Vérification pré-déploiement

**Prompt à envoyer :**
```
Je prépare un déploiement en [staging / production].
Voici ma checklist pré-déploiement :
- Application : [nom et version]
- Changements inclus : [liste des features / fixes]
- Migrations DB : [oui / non]
- Variables d'environnement modifiées : [liste]

Aide-moi à identifier les risques et vérifications à faire.
```

---

## Étape 2 — Revue des migrations

Si des migrations sont incluses :
```
Voici mes migrations de base de données. Analyse-les pour :
1. Risques de perte de données
2. Impact sur les performances (tables volumineuses ?)
3. Réversibilité (down() correct ?)
[collez vos migrations]
```

---

## Étape 3 — Vérification des variables d'environnement

```
Voici mon fichier .env.example. Compare avec les variables nécessaires
pour la nouvelle version et liste ce qui doit être ajouté / modifié
en production :
[contenu du .env.example]
```

---

## Étape 4 — Plan de rollback

```
Génère un plan de rollback pour ce déploiement, incluant :
1. Étapes pour revenir à la version précédente
2. Comment annuler les migrations DB si nécessaire
3. Points de contrôle pour détecter un problème rapidement
```

---

## Checklist de déploiement
- [ ] Tests passants sur la branche
- [ ] Revue de code approuvée
- [ ] Migrations vérifiées
- [ ] Variables d'environnement à jour
- [ ] Plan de rollback documenté
- [ ] Fenêtre de maintenance communiquée (si prod)
- [ ] Monitoring en place
