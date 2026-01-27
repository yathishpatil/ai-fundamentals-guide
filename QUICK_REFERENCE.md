# 🚀 Quick Deployment Reference

## One-Time Setup

```bash
# 1. Update package.json homepage with your GitHub username
# Edit: "homepage": "https://YOUR_USERNAME.github.io/ai-fundamentals-guide"

# 2. Initialize and push to GitHub
git init
git add .
git commit -m "Initial commit: AI Fundamentals Guide"
git remote add origin https://github.com/YOUR_USERNAME/ai-fundamentals-guide.git
git branch -M main
git push -u origin main

# 3. Install and deploy
npm install
npm run deploy

# 4. Enable GitHub Pages
# Go to: Settings → Pages → Source: gh-pages branch
```

## Updating After Changes

```bash
git add .
git commit -m "Update content"
git push
npm run deploy
```

## Your Site URL
```
https://YOUR_USERNAME.github.io/ai-fundamentals-guide
```

## Troubleshooting Commands

```bash
# Check Node.js version
node --version

# Check npm version
npm --version

# Clean install
rm -rf node_modules package-lock.json
npm install

# Test locally before deploying
npm start
# Open: http://localhost:3000

# Force redeploy
npm run deploy -- --force
```

## Alternative: Deploy to Netlify (No GitHub needed)

1. Go to [netlify.com](https://netlify.com)
2. Drag & drop your `/mnt/user-data/outputs/` folder
3. Done! Get instant URL

## File Structure
```
ai-fundamentals-guide/
├── public/
│   └── index.html
├── src/
│   ├── App.js (main component)
│   ├── index.js
│   └── index.css
├── package.json
├── README.md
├── DEPLOYMENT_GUIDE.md
├── QUICK_REFERENCE.md (this file)
└── .gitignore
```

---

**Remember:** Replace `YOUR_USERNAME` with your actual GitHub username everywhere!
