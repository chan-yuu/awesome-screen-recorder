# 🚀 GitHub Pages Deployment Guide

This guide will help you deploy the Awesome Screen Recorder website to GitHub Pages using GitHub Actions.

## 📋 Prerequisites

- A GitHub account
- Git installed on your local machine
- A repository on GitHub (can be your fork of this project)

## 🎯 Quick Deployment (Recommended)

### Step 1: Push to GitHub

```bash
# Navigate to the project directory
cd awesome-screen-recorder

# Initialize git repository (if not already done)
git init

# Add all files
git add .

# Commit changes
git commit -m "Initial commit: Awesome Screen Recorder website"

# Add your GitHub repository as remote
git remote add origin https://github.com/YOUR-USERNAME/awesome-screen-recorder.git

# Push to main branch
git push -u origin main
```

### Step 2: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click on **Settings** tab
3. In the left sidebar, click **Pages**
4. Under **Build and deployment**:
   - **Source**: Select `GitHub Actions`
5. The workflow will automatically deploy your site

### Step 3: Verify Deployment

1. Go to **Actions** tab
2. You should see the "Deploy to GitHub Pages" workflow running
3. Once completed (green checkmark ✅), your site will be live at:
   ```
   https://YOUR-USERNAME.github.io/awesome-screen-recorder/
   ```

## 🔧 Manual Workflow Trigger

If you need to manually trigger deployment:

1. Go to **Actions** tab
2. Click on **Deploy to GitHub Pages** workflow
3. Click **Run workflow** button
4. Select the branch (main/master)
5. Click **Run workflow**

## 📁 Project Structure

```
awesome-screen-recorder/
├── .github/
│   └── workflows/
│       └── deploy-pages.yml    # GitHub Actions workflow
├── .nojekyll                    # Disables Jekyll processing
├── index.html                   # Main website
├── README.md                    # Project documentation
├── DEPLOYMENT.md               # This file
├── LICENSE                      # MIT License
└── .gitignore                   # Git ignore rules
```

## ⚙️ Workflow Configuration

The GitHub Actions workflow (`.github/workflows/deploy-pages.yml`) is configured with:

### Triggers
- Push to `main` or `master` branch
- Manual trigger via GitHub UI (workflow_dispatch)

### Permissions
```yaml
permissions:
  contents: read
  pages: write
  id-token: write
```

### Concurrency
- Only one deployment at a time
- In-progress deployments are not cancelled

## 🌐 Custom Domain (Optional)

If you want to use a custom domain:

### Step 1: Create CNAME File

Create a file named `CNAME` (no extension) in the root directory:

```
your-domain.com
```

Or for a subdomain:

```
subdomain.your-domain.com
```

### Step 2: Configure DNS

Configure your domain's DNS settings:

**For apex domain (your-domain.com):**
```
Type    Name    Value
A       @       185.199.108.153
A       @       185.199.109.153
A       @       185.199.110.153
A       @       185.199.111.153
```

**For subdomain (www.your-domain.com):**
```
Type    Name    Value
CNAME   www     YOUR-USERNAME.github.io
```

### Step 3: Configure GitHub Pages

1. Go to **Settings** → **Pages**
2. Under **Custom domain**, enter your domain
3. Click **Save**
4. Check **Enforce HTTPS** (after DNS propagates)

## 🔍 Troubleshooting

### Site Not Deploying

**Check Workflow Status:**
1. Go to **Actions** tab
2. Look for failed workflow runs (red X ❌)
3. Click on the failed run to see error details

**Common Issues:**
- Workflow file syntax error
- Missing permissions
- Branch name mismatch

**Solution:**
```yaml
# Ensure your workflow has correct branch names
on:
  push:
    branches:
      - main
      - master
```

### 404 Error After Deployment

**Causes:**
- `.nojekyll` file missing
- Incorrect file paths
- Deployment not completed

**Solutions:**
1. Ensure `.nojekyll` file exists in root
2. Wait 1-2 minutes after deployment completes
3. Clear browser cache (Ctrl+Shift+R / Cmd+Shift+R)
4. Check that `index.html` is in the root directory

### Assets Not Loading

**Check:**
- All paths are relative (no absolute paths starting with `/`)
- CSS and JS files are in correct locations
- Browser console for 404 errors

**Fix:**
The HTML file uses relative paths, which should work automatically with GitHub Pages.

## 📊 Updating Your Site

### Automatic Deployment

Any push to the `main` branch will automatically trigger deployment:

```bash
# Make your changes
git add .
git commit -m "Update: Added new tools"
git push origin main

# Workflow will automatically deploy
```

### Manual Deployment

For manual control:

1. Go to **Actions** → **Deploy to GitHub Pages**
2. Click **Run workflow**
3. Select branch and run

## 🔒 Security Considerations

### Workflow Permissions

The workflow uses minimal required permissions:
- `contents: read` - Read repository contents
- `pages: write` - Deploy to GitHub Pages
- `id-token: write` - Authenticate with GitHub Pages

### API Keys and Secrets

**⚠️ Important:** This is a static site. Do NOT include:
- API keys in the HTML/JS
- Passwords or credentials
- Private configuration files

All code is publicly visible on GitHub Pages.

## 📈 Performance Tips

### Optimize Images

If you add images:
- Use WebP or optimized PNG/JPG
- Compress images before committing
- Consider using CDN for large assets

### Minify Assets

For production:
- Minify CSS (currently embedded in HTML)
- Minify JavaScript (currently embedded in HTML)
- Enable gzip compression (automatic on GitHub Pages)

### Cache Strategy

GitHub Pages automatically caches assets. To force refresh:
- Add version query string: `style.css?v=2`
- Use browser hard refresh (Ctrl+Shift+R / Cmd+Shift+R)

## 🎨 Customization

### Change Site Title

Edit `index.html`:
```html
<title>🎬 Your Custom Title</title>
```

### Change Colors

Edit CSS variables in `<style>` section:
```css
:root {
    --primary: #6366f1;      /* Main color */
    --secondary: #10b981;    /* Secondary color */
    --accent: #f59e0b;       /* Accent color */
}
```

### Add Analytics

Add before `</head>`:
```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_MEASUREMENT_ID');
</script>
```

## 📞 Support

### GitHub Pages Documentation
- [GitHub Pages Docs](https://docs.github.com/pages)
- [GitHub Actions Docs](https://docs.github.com/actions)

### Common Resources
- [Configuring a publishing source](https://docs.github.com/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
- [About GitHub Pages](https://docs.github.com/pages/getting-started-with-github-pages/about-github-pages)

## ✅ Deployment Checklist

Before deploying, ensure:

- [ ] All files are committed
- [ ] `.github/workflows/deploy-pages.yml` exists
- [ ] `.nojekyll` file exists
- [ ] `index.html` is in root directory
- [ ] No sensitive data in code
- [ ] GitHub Pages enabled in Settings
- [ ] Workflow has correct permissions

## 🎉 Success!

After successful deployment, you'll see:

```
✅ Your site is live at https://YOUR-USERNAME.github.io/awesome-screen-recorder/
```

Share your site with the world! 🌟

---

**Last Updated:** 2025
**Maintained by:** Awesome Screen Recorder Team