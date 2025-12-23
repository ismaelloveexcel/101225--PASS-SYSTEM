# Deployment Guide

This guide explains how to set up automatic deployment for the Math Quest game to GitHub Pages.

## Overview

The game is automatically deployed using GitHub Actions. Every time changes are pushed to the `main` branch, the workflow will deploy the updated game to GitHub Pages.

## Setup Instructions

### 1. Enable GitHub Pages

1. Go to your repository on GitHub
2. Navigate to **Settings** → **Pages**
3. Under **Source**, select **GitHub Actions** from the dropdown
4. Save the settings

### 2. Verify Workflow

1. Go to the **Actions** tab in your repository
2. You should see the "Deploy Game to GitHub Pages" workflow
3. If the workflow hasn't run yet, you can trigger it manually by:
   - Clicking on the workflow
   - Clicking "Run workflow" button
   - Selecting the `main` branch
   - Clicking "Run workflow"

### 3. Access Your Deployed Game

Once the workflow completes successfully:
- Your game will be live at: `https://ismaelloveexcel.github.io/101225--PASS-SYSTEM/`
- The URL is also shown in the workflow run details

## How It Works

### Automatic Deployment

The workflow (`.github/workflows/deploy.yml`) automatically:
1. Checks out the code
2. Sets up GitHub Pages
3. Uploads all files as an artifact
4. Deploys to GitHub Pages

### Trigger Points

Deployment happens automatically when:
- Code is pushed to the `main` branch
- Pull requests are merged to the `main` branch
- You manually trigger the workflow from the Actions tab

### What Gets Deployed

Everything in the repository is deployed, including:
- `index.html` - The main game file
- `README.md` - Documentation (accessible at `/README.md`)
- Any other files in the repository

Files in `.gitignore` are not deployed.

## Workflow Configuration

### Permissions

The workflow has these permissions:
- `contents: read` - To read repository files
- `pages: write` - To deploy to GitHub Pages
- `id-token: write` - For secure deployment

### Concurrency

The workflow uses concurrency control to:
- Prevent multiple deployments running simultaneously
- Cancel in-progress deployments if a new one starts

## Testing Deployment

### Local Testing

Before deploying, test locally:

```bash
# Option 1: Open directly in browser
open index.html

# Option 2: Use Python's built-in server
python -m http.server 8000
# Then visit http://localhost:8000
```

### Verify Deployment

After deployment:
1. Visit your GitHub Pages URL
2. Test all game features
3. Check browser console for any errors
4. Test on mobile devices (the game is mobile-first)

## Troubleshooting

### Workflow Fails

If the deployment workflow fails:
1. Check the Actions tab for error details
2. Ensure GitHub Pages is enabled in Settings
3. Verify the `main` branch protection rules allow workflows to run
4. Check that the workflow file syntax is valid

### Game Doesn't Load

If the game doesn't load after deployment:
1. Check browser console for errors
2. Verify all Three.js CDN links are accessible
3. Clear browser cache and reload
4. Check if GitHub Pages is properly configured

### Manual Deployment

To manually deploy:
1. Go to Actions tab
2. Select "Deploy Game to GitHub Pages" workflow
3. Click "Run workflow"
4. Select `main` branch
5. Click "Run workflow" button

## Updating the Game

To deploy updates:
1. Make changes to `index.html` or other files
2. Commit changes to a branch
3. Create a pull request to `main`
4. Merge the pull request
5. Deployment happens automatically!

## Additional Notes

- **No Build Process**: The game is static HTML, so no build step is needed
- **Fast Deployment**: Typical deployment takes 1-2 minutes
- **Automatic Updates**: Every change to `main` deploys immediately
- **Version Control**: All deployments are tracked in Actions history

## Support

For issues with:
- **GitHub Actions**: Check the [GitHub Actions documentation](https://docs.github.com/en/actions)
- **GitHub Pages**: Check the [GitHub Pages documentation](https://docs.github.com/en/pages)
- **The Game**: Open an issue in this repository
