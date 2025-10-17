# GitHub Pages Setup Checklist

Save here for future references

Follow these steps to enable GitHub Pages for your documentation:

## ✅ Step-by-Step Guide

### 1. Push Changes to GitHub

First, commit and push all the documentation files:

```bash
git add .
git commit -m "Add MkDocs documentation site"
git push origin main
```

### 2. Enable GitHub Pages

1. Go to your repository on GitHub: `https://github.com/pinnlabs/fastapi-env-banner`
2. Click on **Settings** (top right)
3. In the left sidebar, click **Pages**
4. Under **Build and deployment**:
   - **Source**: Select **GitHub Actions**
5. Click **Save** (if there's a save button)

### 3. Verify Workflow

1. Go to the **Actions** tab in your repository
2. You should see a workflow called "Deploy Documentation"
3. If it hasn't run yet, it will run automatically on the next push to `main`
4. Or you can manually trigger it:
   - Click on "Deploy Documentation"
   - Click "Run workflow"
   - Select branch `main`
   - Click "Run workflow"

### 4. Wait for Deployment

- The workflow takes about 1-2 minutes to complete
- You can watch the progress in the Actions tab
- Once complete, you'll see a green checkmark ✅

### 5. Access Your Documentation

Once deployed, your documentation will be available at:

**https://pinnlabs.github.io/fastapi-env-banner/**

## 🔍 Troubleshooting

### Workflow Fails

If the workflow fails:

1. Check the error message in the Actions tab
2. Common issues:
   - Missing dependencies (already added to `pyproject.toml`)
   - Build errors (test locally with `mkdocs build --strict`)
   - Permissions issues (check repository settings)

### Documentation Not Appearing

If the site doesn't load:

1. Wait a few minutes (can take up to 10 minutes for first deployment)
2. Check that GitHub Pages is enabled in Settings → Pages
3. Verify the workflow completed successfully
4. Try accessing the URL in an incognito/private window (cache issue)

### 404 Error

If you get a 404 error:

1. Make sure the workflow has completed
2. Check that the source is set to "GitHub Actions" (not "Deploy from a branch")
3. Wait a few more minutes and try again

## 🔄 Updating Documentation

After the initial setup, updating is easy:

1. Edit any `.md` file in the `docs/` directory
2. Commit and push to `main`:
   ```bash
   git add docs/
   git commit -m "Update documentation"
   git push origin main
   ```
3. The workflow will automatically rebuild and deploy
4. Changes will be live in 1-2 minutes

## 🧪 Testing Before Deploy

Always test locally before pushing:

```bash
# Build to check for errors
uv run mkdocs build --strict

# Preview locally
uv run mkdocs serve
```

Then open http://127.0.0.1:8000 to verify everything looks good.

## 📝 Custom Domain (Optional)

If you want to use a custom domain:

1. Add a `CNAME` file to the `docs/` directory with your domain
2. Configure DNS settings with your domain provider
3. Update the `site_url` in `mkdocs.yml`
4. See [GitHub Pages custom domain docs](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site)

## ✨ You're Done!

Once GitHub Pages is enabled and the workflow runs successfully, your documentation will be live and automatically updated with every push to `main`.

**Documentation URL:** https://pinnlabs.github.io/fastapi-env-banner/

---

Need help? Check the [GitHub Pages documentation](https://docs.github.com/en/pages) or open an issue.
