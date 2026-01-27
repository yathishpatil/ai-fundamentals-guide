# GitHub Pages Deployment Guide

Complete step-by-step instructions to deploy your AI Fundamentals Guide to GitHub Pages.

## 📋 Prerequisites

- Git installed on your computer
- A GitHub account ([sign up here](https://github.com/join))
- Node.js installed (version 14+) - [download here](https://nodejs.org/)

## 🚀 Method 1: Deploy via Command Line (Recommended)

### Step 1: Prepare the Files

You already have all the necessary files in `/mnt/user-data/outputs/`. Download this entire folder to your computer.

### Step 2: Create GitHub Repository

1. Go to [GitHub](https://github.com) and log in
2. Click the **"+"** icon (top-right) → **"New repository"**
3. Repository settings:
   - **Name:** `ai-fundamentals-guide` (or your preferred name)
   - **Description:** "Comprehensive visual guide to AI fundamentals and security"
   - **Public** (required for free GitHub Pages)
   - ❌ **Do NOT** initialize with README (we already have one)
4. Click **"Create repository"**

### Step 3: Update package.json

Before uploading, edit `package.json` and replace:
```json
"homepage": "https://YOUR_GITHUB_USERNAME.github.io/ai-fundamentals-guide"
```

With your actual GitHub username:
```json
"homepage": "https://svenkat.github.io/ai-fundamentals-guide"
```

### Step 4: Upload to GitHub

Open terminal/command prompt in the downloaded folder and run:

```bash
# Initialize git repository
git init

# Add all files
git add .

# Commit files
git commit -m "Initial commit: AI Fundamentals Guide"

# Add your GitHub repository as remote
# Replace YOUR_USERNAME with your GitHub username
git remote add origin https://github.com/YOUR_USERNAME/ai-fundamentals-guide.git

# Push to GitHub
git branch -M main
git push -u origin main
```

### Step 5: Install Dependencies and Deploy

```bash
# Install all required packages
npm install

# Deploy to GitHub Pages
npm run deploy
```

This will:
- Build the React app
- Create a `gh-pages` branch
- Deploy the built files to GitHub Pages

### Step 6: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click **"Settings"** tab
3. Scroll down to **"Pages"** in left sidebar
4. Under **"Source"**, select:
   - Branch: `gh-pages`
   - Folder: `/ (root)`
5. Click **"Save"**

### Step 7: Access Your Site

Your site will be live at:
```
https://YOUR_USERNAME.github.io/ai-fundamentals-guide
```

⏱️ **Note:** It may take 2-5 minutes for the site to become available after first deployment.

---

## 🖱️ Method 2: Deploy via GitHub Desktop (Easier for Beginners)

### Step 1: Install GitHub Desktop

Download from [desktop.github.com](https://desktop.github.com/)

### Step 2: Create Repository

1. Open GitHub Desktop
2. **File** → **New Repository**
   - Name: `ai-fundamentals-guide`
   - Local Path: Choose where to save
   - ✅ Initialize with README: **No**
3. Click **"Create Repository"**

### Step 3: Add Your Files

1. Copy all files from `/mnt/user-data/outputs/` to the repository folder
2. GitHub Desktop will show all files as changes
3. Update `package.json` homepage (see Method 1, Step 3)
4. Write commit message: "Initial commit"
5. Click **"Commit to main"**
6. Click **"Publish repository"**
   - ✅ Public repository
   - Click **"Publish Repository"**

### Step 4: Deploy from Terminal

Open terminal in the repository folder:

```bash
npm install
npm run deploy
```

### Step 5: Enable GitHub Pages

Follow Step 6 from Method 1 above.

---

## 🔄 Updating Your Site

After making changes:

```bash
# Add changes
git add .

# Commit changes
git commit -m "Description of changes"

# Push to GitHub
git push

# Redeploy to GitHub Pages
npm run deploy
```

---

## 🛠️ Troubleshooting

### Issue: "npm: command not found"
**Solution:** Install Node.js from [nodejs.org](https://nodejs.org/)

### Issue: "gh-pages branch not found"
**Solution:** Run `npm run deploy` first - it creates the branch automatically

### Issue: "404 - Page not found"
**Solutions:**
1. Wait 5 minutes - deployment takes time
2. Check GitHub Pages settings (Settings → Pages)
3. Ensure `gh-pages` branch is selected as source
4. Clear browser cache and try again

### Issue: "Permission denied" when pushing
**Solutions:**
1. Set up GitHub authentication: [docs.github.com/authentication](https://docs.github.com/en/authentication)
2. Use GitHub Desktop instead
3. Use personal access token instead of password

### Issue: Site shows but styling is broken
**Solution:** 
- Check that `homepage` in `package.json` matches your GitHub Pages URL exactly
- Redeploy: `npm run deploy`

---

## 📱 Sharing Your Site

Once deployed, share your guide:

- **Direct link:** `https://YOUR_USERNAME.github.io/ai-fundamentals-guide`
- **Embed in website:** Use an iframe
  ```html
  <iframe src="https://YOUR_USERNAME.github.io/ai-fundamentals-guide" 
          width="100%" height="2000px"></iframe>
  ```
- **QR Code:** Generate at [qr-code-generator.com](https://www.qr-code-generator.com/)

---

## 🎯 Alternative Hosting (If GitHub Pages Issues)

### Netlify (Easiest)
1. Create account at [netlify.com](https://netlify.com)
2. Drag & drop the entire `/mnt/user-data/outputs/` folder
3. Get instant URL: `yoursite.netlify.app`
4. Free custom domain support

### Vercel
1. Create account at [vercel.com](https://vercel.com)
2. Import GitHub repository
3. Auto-deploys on every push
4. Get URL: `yourproject.vercel.app`

### Cloudflare Pages
1. Create account at [pages.cloudflare.com](https://pages.cloudflare.com)
2. Connect GitHub repository
3. Free unlimited bandwidth
4. Get URL: `yourproject.pages.dev`

---

## ✅ Checklist

Before deploying:
- [ ] Updated `homepage` in `package.json` with your GitHub username
- [ ] Created GitHub repository
- [ ] All files uploaded to GitHub
- [ ] Ran `npm install` successfully
- [ ] Ran `npm run deploy` successfully
- [ ] Enabled GitHub Pages in repository settings
- [ ] Waited 5 minutes for deployment
- [ ] Tested site URL

---

## 📞 Need Help?

If you run into issues:
1. Check the [GitHub Pages documentation](https://docs.github.com/en/pages)
2. Search [Stack Overflow](https://stackoverflow.com/questions/tagged/github-pages)
3. Use GitHub Desktop for simpler workflow

---

**Pro Tip:** Once deployed, you can update content by editing files, committing, and running `npm run deploy` again. Changes appear in 1-2 minutes!
