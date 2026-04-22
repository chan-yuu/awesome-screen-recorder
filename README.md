# 🎬 Awesome Screen Recorder

The ultimate collection of the best screen recording tools for every platform and use case — from open-source powerhouses to enterprise-grade solutions.

![GitHub Actions Workflow Status](https://img.shields.io/github/actions/workflow/status/awesome-screen-recorder/deploy-pages.yml?label=Deploy%20Status)
![License](https://img.shields.io/github/license/awesome-screen-recorder?color=blue)

## 🌐 Live Demo

Visit the live site: **[https://awesome-screen-recorder.github.io](https://awesome-screen-recorder.github.io)**

## ✨ Features

### Open Source Tools (13+)
- **OBS Studio** - The undisputed king of free screen recording and live streaming (71.5k ⭐)
- **ShareX** - Windows Swiss Army knife for screenshots and recordings (36k ⭐)
- **ScreenToGif** - Record, edit, and export as GIF/APNG/video (26.6k ⭐)
- **FFmpeg** - Command-line multimedia powerhouse (58.7k ⭐)
- **Open ScreenRecorder** - Modern UWP screen recorder for Windows
- **VokoscreenNG** - Easy-to-use recorder with webcam overlay
- **Kooha** - Beautiful GNOME screen recorder for Wayland

### Commercial Tools (20+)
- **Loom** - Async video messaging for teams ($15/mo)
- **Camtasia** - Professional tutorial creation ($179/yr)
- **ScreenFlow** - macOS professional recorder ($199 perpetual)
- **Bandicam** - High-FPS gaming recorder ($33/yr)
- **NVIDIA ShadowPlay** - Hardware-accelerated for NVIDIA GPUs (Free)
- **Xbox Game Bar** - Built-in Windows game recorder (Free)
- **Apple QuickTime** - Built-in macOS screen recorder (Free)

## 🚀 Quick Start

### Viewing Locally

```bash
# Clone the repository
git clone https://github.com/awesome-screen-recorder/awesome-screen-recorder.git
cd awesome-screen-recorder

# Open directly in browser
open index.html  # macOS
start index.html # Windows
xdg-open index.html # Linux

# Or serve with a local server
python -m http.server 8000
# Visit http://localhost:8000
```

### Deploying to GitHub Pages

This project includes automated deployment via GitHub Actions.

#### Option 1: Fork This Repository

1. **Fork** this repository to your GitHub account
2. Go to **Settings** → **Pages**
3. Under **Build and deployment**:
   - Source: `GitHub Actions`
4. The site will automatically deploy to `https://your-username.github.io/awesome-screen-recorder`

#### Option 2: Manual Deployment

1. Create a new repository on GitHub
2. Push the files to your repository
3. Enable GitHub Actions in repository settings
4. The workflow will automatically deploy on push to `main` branch

#### Manual Workflow Trigger

You can also manually trigger deployment:

1. Go to **Actions** tab
2. Select **Deploy to GitHub Pages** workflow
3. Click **Run workflow**
4. Select branch and click **Run workflow**

## 📁 Project Structure

```
awesome-screen-recorder/
├── .github/
│   └── workflows/
│       └── deploy-pages.yml    # GitHub Actions deployment workflow
├── index.html                   # Main single-page application
├── README.md                    # This file
├── .nojekyll                    # Disables Jekyll processing
└── .gitignore                   # Git ignore file
```

## 🛠️ Customization

### Changing the Site Title

Edit `index.html` and modify the `<title>` tag:

```html
<title>🎬 Your Custom Title - Screen Recorder Collection</title>
```

### Adding New Tools

Find the tool grid section in `index.html` and add a new card:

```html
<article class="tool-card" id="your-tool" data-type="opensource" data-platforms="windows" data-price="free">
    <div class="tool-header">
        <div class="tool-logo">🎥</div>
        <div class="tool-info">
            <div class="tool-name">Your Tool <span class="tool-stars">⭐ Stars</span></div>
            <div class="tool-platforms"><span class="platform-badge">🪟 Windows</span></div>
        </div>
        <span class="tool-type opensource">Open Source</span>
    </div>
    <p class="tool-description">Tool description here...</p>
    <div class="tool-features">
        <span class="feature-tag">Feature 1</span>
        <span class="feature-tag">Feature 2</span>
    </div>
    <div class="tool-pricing">
        <span class="pricing-label">Price:</span>
        <span class="pricing-value">FREE</span>
    </div>
    <div class="tool-links">
        <a href="https://example.com" target="_blank" class="tool-link primary">🌐 Official Site</a>
    </div>
</article>
```

### Changing Colors

Edit the CSS variables in the `<style>` section of `index.html`:

```css
:root {
    --primary: #6366f1;        /* Main accent color */
    --primary-dark: #4f46e5;   /* Darker variant */
    --secondary: #10b981;      /* Secondary color (green) */
    --accent: #f59e0b;         /* Accent color (amber) */
    --bg-dark: #0f172a;        /* Background color */
}
```

## 🔧 GitHub Actions Workflow

The deployment workflow (`.github/workflows/deploy-pages.yml`) does the following:

1. **Triggers** on push to `main`/`master` branch or manual trigger
2. **Builds** the static site
3. **Uploads** as artifact
4. **Deploys** to GitHub Pages environment

### Workflow Permissions

The workflow requires these permissions (already configured):

```yaml
permissions:
  contents: read
  pages: write
  id-token: write
```

## 📊 Features

- ✅ **Bilingual Support** - English/Chinese toggle
- ✅ **Live Search** - Search by name, platform, or features
- ✅ **Smart Filters** - Filter by type, platform, price
- ✅ **Responsive Design** - Works on all devices
- ✅ **Smooth Animations** - Modern UI effects
- ✅ **Dark Theme** - Eye-friendly dark mode
- ✅ **Auto-Deploy** - GitHub Actions deployment

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- All the amazing open-source screen recorder developers
- The communities behind these incredible tools
- GitHub Pages for free hosting

---

**Made with ❤️ for creators worldwide**

[⬆ Back to Top](#awesome-screen-recorder)