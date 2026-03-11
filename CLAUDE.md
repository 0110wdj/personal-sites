# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Purpose
Multi-tenant personal homepage collection repository. Hosts multiple independent personal homepages, each accessible via its own subpath URL. Deployed automatically to GitHub Pages.

## Project Structure
```
/
├── index.html                # Blank landing page with hint text
├── liujie/
│   └── index.html           # 刘杰的个人主页 (access via /liujie/) - draggable card interface
├── lishuang/
│   └── index.html           # 李爽的个人主页 (access via /lishuang/) - under construction
└── .github/
    └── workflows/
        └── deploy.yml       # GitHub Pages deployment workflow
```

## Common Commands
### Local Development
```bash
# Run local static server (port 8000)
python3 -m http.server 8000

# Or with Node.js
npx serve .
```
Then visit http://localhost:8000 in your browser.

### Adding New Personal Site
1. Create a new directory with the username as the directory name: `mkdir newuser`
2. Create `newuser/index.html` with the personal homepage content
3. Add a link to the new site in the root `index.html` landing page
4. Push to main branch, GitHub Actions will auto-deploy

## Deployment
- Auto-deployed to GitHub Pages on every push to `main` branch
- Base URL: `https://<username>.github.io/personal-sites/`
- Individual site URLs:
  - 张三: `https://<username>.github.io/personal-sites/zhangsan/`
  - 李四: `https://<username>.github.io/personal-sites/lisi/`
  - New sites: `https://<username>.github.io/personal-sites/<directory-name>/`

## GitHub Pages Setup Instructions
1. Push this repository to GitHub
2. Go to repository Settings → Pages
3. Under "Build and deployment", set "Source" to "GitHub Actions"
4. First deployment will run automatically, subsequent deployments trigger on push to main
