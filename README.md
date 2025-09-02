# Test Actions Repo (Auto-Merger + Serverless)

Ye repo aap ke diye gaye 3 workflows **as-is** use karta hai:

- `.github/workflows/auto-merger.yml` (unchanged)
- `.github/workflows/build-and-deploy.yml` (unchanged)
- `.github/workflows/serverless-part1.yml` (unchanged)

## Local Setup (optional)
- Node.js 18+ install kar lein.
- `npm install`

## Serverless Deploy Pre-req
GitHub Secrets add karein (repo → Settings → Secrets and variables → Actions):
- `AWS_ACCESS_KEY_ID`
- `AWS_SECRET_ACCESS_KEY`
- `AWS_REGION` (e.g. `us-east-1`)

Agar workflows mein aur secrets ka reference ho to woh bhi add karen (exact names yml files me dekh sakte hain).

## Branch Model (test run)
1. Remote par nayi empty repository banaien (GitHub).
2. Locally ye commands run karein:
```bash
git init
git add .
git commit -m "chore: initial scaffold"
git branch -M dev
git remote add origin <YOUR_GITHUB_REPO_URL>
git push -u origin dev
# Feature branches
for b in f1 f2 f3 f4 f5 f6 f7 f8 f9; do git branch "$b"; done
git push origin --all
```
3. Ab `dev` ya relevant branch par push karne se aap ke workflows trigger honge.
4. `f1` par push/PR se `serverless-part1.yml` wali job run hogi (aap ke given file ke mutabiq).

## Notes
- `serverless.yml` minimal hai taake deploy commands pass ho saken.
- AWS par deploy ke liye aap ke account me permissions aur sahi region zaroori hai.
