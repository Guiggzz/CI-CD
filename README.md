# CI/CD — Niveau 1

## Pipeline

La pipeline se lance à la main dans GitHub Actions (`workflow_dispatch`).

Elle fait deux choses :
1. Vérifie que `nginx.conf`, `index.html` et `Dockerfile` sont présents
2. Build l'image Docker et teste la config nginx avec `nginx -t`

Si un fichier manque ou si la config nginx est cassée, la pipeline échoue.

# CI/CD — Niveau 2

## Pipeline

La pipeline se déclenche sur `push` et `pull_request` sur `main`.

Elle fait quatre choses :
1. Vérifie que `nginx.conf`, `index.html` et `Dockerfile` sont présents
2. Build l'image Docker
3. Lance le conteneur et teste la réponse HTTP
4. Teste l'endpoint `/health`

Si un fichier manque ou si un test échoue, la pipeline échoue.
