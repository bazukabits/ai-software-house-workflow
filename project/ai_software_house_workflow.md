# AI Software House Workflow

## Git Branching & Deployment

### 1. Create Feature Branch
```bash
git checkout -b feat/contact-form
```

### 2. Develop & Commit
```bash
write_file components/Contact.js "<form>...</form>"
git add .
git commit -m "feat: contact form"
```

### 3. Open Pull Request
```bash
gh pr create --base main --head feat/contact-form
```

### 4. Test & Merge
```bash
npm test  # Run tests
gh pr merge --squash
```

### 5. Deploy to Production
```bash
nanobot cron add --name "deploy" --every 3600 --exec "gh workflow run deploy.yml"
```

### 6. Clean Up Branch
```bash
git branch -d feat/contact-form
git push origin --delete feat/contact-form
```