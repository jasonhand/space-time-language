# GitHub Pages Deployment Guide

This guide will help you deploy the Vector Visualization project to GitHub Pages.

## Prerequisites

1. A GitHub account
2. Git installed on your local machine
3. The project files in a GitHub repository

## Deployment Steps

### 1. Create a GitHub Repository

1. Go to [GitHub](https://github.com) and sign in
2. Click the "+" icon in the top right corner and select "New repository"
3. Name your repository (e.g., `vector-visualization`)
4. Make it public (required for free GitHub Pages)
5. Don't initialize with README (since you already have one)
6. Click "Create repository"

### 2. Push Your Code to GitHub

```bash
# If you haven't already, initialize git and add your files
git init
git add .
git commit -m "Initial commit: Vector visualization project"

# Add your GitHub repository as remote
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git

# Push to GitHub
git branch -M main
git push -u origin main
```

### 3. Enable GitHub Pages

1. Go to your repository on GitHub
2. Click on "Settings" tab
3. Scroll down to "Pages" section (in the left sidebar)
4. Under "Source", select "Deploy from a branch"
5. Choose "main" branch and "/ (root)" folder
6. Click "Save"

### 4. Configure GitHub Actions (Optional but Recommended)

The project includes a GitHub Actions workflow (`.github/workflows/deploy.yml`) that will automatically deploy your site when you push changes to the main branch.

To enable it:
1. Go to your repository settings
2. Click on "Actions" → "General"
3. Under "Workflow permissions", select "Read and write permissions"
4. Check "Allow GitHub Actions to create and approve pull requests"
5. Click "Save"

### 5. Wait for Deployment

- GitHub Pages will take a few minutes to build and deploy your site
- You can monitor the deployment progress in the "Actions" tab
- Once deployed, your site will be available at: `https://YOUR_USERNAME.github.io/YOUR_REPO_NAME`

## Custom Domain (Optional)

If you have a custom domain:

1. Add your domain to the `CNAME` file in the repository root
2. Go to your repository settings → Pages
3. Add your custom domain in the "Custom domain" field
4. Configure your DNS settings to point to GitHub Pages

## File Structure

Your repository should look like this:

```
vector-visualization/
├── index.html          # Main application file
├── README.md           # Project documentation
├── LICENSE             # License file
├── 404.html           # Custom 404 page
├── CNAME              # Custom domain (optional)
├── _site.yml          # Jekyll configuration
├── .github/
│   └── workflows/
│       └── deploy.yml # GitHub Actions workflow
└── DEPLOYMENT.md      # This file
```

## Troubleshooting

### Site Not Loading
- Check that your repository is public
- Verify that GitHub Pages is enabled in repository settings
- Wait a few minutes for the initial deployment

### Changes Not Appearing
- Make sure you pushed changes to the main branch
- Check the Actions tab for deployment status
- Clear your browser cache

### Custom Domain Issues
- Verify DNS settings are correct
- Check that the CNAME file contains your domain
- Wait up to 24 hours for DNS propagation

## Performance Tips

1. **Optimize Images**: Use compressed images if you add any
2. **Minimize HTTP Requests**: The current setup is already optimized
3. **Enable Caching**: GitHub Pages automatically handles this
4. **Use CDN**: GitHub Pages serves content from CDN globally

## Security Considerations

- The site is static HTML/CSS/JavaScript, so it's secure by default
- No server-side code means no security vulnerabilities
- All interactions happen client-side

## Support

If you encounter issues:
1. Check the GitHub Pages documentation
2. Review the Actions logs for deployment errors
3. Verify all files are properly committed and pushed

Your vector visualization should now be live and accessible to anyone with an internet connection! 