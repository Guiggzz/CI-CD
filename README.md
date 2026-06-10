# CI/CD — Niveau 1

## Pipeline

La pipeline se lance à la main dans GitHub Actions (`workflow_dispatch`).

Elle fait deux choses :
1. Vérifie que `nginx.conf`, `index.html` et `Dockerfile` sont présents
2. Build l'image Docker et teste la config nginx avec `nginx -t`

Si un fichier manque ou si la config nginx est cassée, la pipeline échoue.
