# Setting Up GitHub Pages

## Make Repository Public & Enable GitHub Pages

### Step 1: Make Repository Public

1. Go to: https://github.com/cengkuru/ai-framework
2. Click **Settings** (top right)
3. Scroll to bottom → **Danger Zone**
4. Click **Change visibility**
5. Select **Make public**
6. Type repository name to confirm

### Step 2: Enable GitHub Pages

1. In **Settings**, click **Pages** (left sidebar)
2. Under **Source**, select:
   - Branch: `main`
   - Folder: `/ (root)`
3. Click **Save**
4. Wait 1-2 minutes for deployment

### Step 3: Access Your Site

Your visualization will be live at:
```
https://cengkuru.github.io/ai-framework/
```

Or directly:
```
https://cengkuru.github.io/ai-framework/cost-knowledge-map.html
```

## Quick Access via GitHub CLI (Alternative)

If you have GitHub CLI installed:

```bash
# Make repository public
gh repo edit cengkuru/ai-framework --visibility public

# Enable GitHub Pages
gh api repos/cengkuru/ai-framework/pages \
  --method POST \
  -H "Accept: application/vnd.github+json" \
  -f source[branch]=main \
  -f source[path]=/
```

## Verify Setup

Check deployment status:
1. Go to **Actions** tab in your repository
2. Look for "pages build and deployment" workflow
3. Green checkmark = successfully deployed

## Troubleshooting

**Still getting 404?**
- Wait 5 minutes after enabling Pages (first deployment takes time)
- Clear browser cache
- Check repository is public
- Verify Pages is enabled in Settings → Pages

**Build failed?**
- Check Actions tab for error details
- Ensure `index.html` or `cost-knowledge-map.html` exists in root
- Verify branch name is `main` not `master`
