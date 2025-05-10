# GitHub Workflows (centralisés)

Ce dépôt contient des **workflows GitHub Actions réutilisables** que tu peux inclure dans plusieurs projets (comme `mailedge-api`, `mailedge-ui`, etc.).

## ✅ Workflow disponibles

### 🔧 `build.yml` – Vérifie que l'app build correctement

- Lit automatiquement la version de Node définie dans `package.json > volta.node`
- Installe les dépendances (`npm ci`)
- Lance le build (`npm run build`)

## 🚀 Comment l’utiliser dans un projet

1. Dans ton repo (ex: `mailedge-api`), crée le fichier suivant :  
   `.github/workflows/build.yml`

2. Mets ce contenu :

```yaml
name: Build (via reusable workflow)

on:
  push:
    branches: [main]
  pull_request:
    branches: [main]

jobs:
  build:
    uses: mrz1880/github-workflows/.github/workflows/build.yml@main
