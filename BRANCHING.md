# Branching Strategy

Branches:
- main — production (protected)
- develop — integration for next release
- feature/<name> — developer branches
- release/<ver> — release prep
- hotfix/<name> — emergency fixes

Workflow:
1. Branch from develop for new work.
2. Open PR into develop.
3. Merge develop -> main via release branch when ready.
