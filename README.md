# Test Actions Repo (v2)

This archive contains a ready-to-run scaffold with your workflows and serverless file.

## Included
- `.github/workflows/auto-merger.yml` (your auto merge workflow)
- `.github/workflows/build-and-deploy.yml` (build/deploy workflow)
- `.github/workflows/branch-demo.yml` (simple visibility workflow for `f1..f9`)
- `serverless-part1.yml` (at repo root)

## How to use
1. Extract into your repository directory.
2. Commit & push the files:
   ```bash
   git add .
   git commit -m "chore: add workflows (v2)"
   git push
   ```
3. Push to `dev`, `temp2`, `uat`, or any of `f1..f9` to see the workflows run.
