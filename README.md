# BuzzHive AI Website

This is a static website for BuzzHive AI, ready to be deployed on GitHub Pages.

## Setup Instructions

### 1. Create a GitHub Repository

1. Go to [GitHub](https://github.com) and create a new repository
2. Name it `buzzhive-ai` (or your preferred name)
3. Make it public (required for free GitHub Pages)

### 2. Upload Files

You can either:
- **Option A**: Use GitHub's web interface
  - Click "uploading an existing file"
  - Drag and drop all files from the `website/` folder
  - Commit the changes

- **Option B**: Use Git command line
  ```bash
  cd website
  git init
  git add .
  git commit -m "Initial website commit"
  git branch -M main
  git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
  git push -u origin main
  ```

### 3. Enable GitHub Pages

1. Go to your repository on GitHub
2. Click **Settings** → **Pages**
3. Under "Source", select **main** branch and **/ (root)** folder
4. Click **Save**
5. Your site will be available at: `https://YOUR_USERNAME.github.io/buzzhive-ai/`

### 4. Add Custom Domain (buzz-hive.com)

1. In your repository, go to **Settings** → **Pages**
2. Under "Custom domain", enter: `buzz-hive.com`
3. Click **Save**
4. GitHub will create a `CNAME` file (or you can create it manually with just `buzz-hive.com` inside)

### 5. Configure DNS

In your domain registrar (where you bought `buzz-hive.com`), add these DNS records:

**Option A: Using A records (recommended)**
```
Type: A
Name: @
Value: 185.199.108.153
TTL: 3600

Type: A
Name: @
Value: 185.199.109.153
TTL: 3600

Type: A
Name: @
Value: 185.199.110.153
TTL: 3600

Type: A
Name: @
Value: 185.199.111.153
TTL: 3600
```

**Option B: Using CNAME (simpler)**
```
Type: CNAME
Name: @
Value: YOUR_USERNAME.github.io
TTL: 3600
```

**Also add for www subdomain:**
```
Type: CNAME
Name: www
Value: YOUR_USERNAME.github.io
TTL: 3600
```

### 6. Add Assets

1. Copy `apps/mobile/assets/buzz-logo.png` to `website/assets/buzz-logo.png`
2. The `buzz-hive-removed-background.png` should already be in `website/assets/`
3. Add your app screenshots to `website/assets/` with these names:
   - `screenshot-diary.png` - Diary/journal feature
   - `screenshot-explore.png` - Map/Explore feature
   - `screenshot-hive.png` - Hive page with buzzes
   - `screenshot-ask.png` - Ask AI agent feature
4. Or update the image filenames in `index.html` if you use different names

### 7. Update App Store Link

In `index.html`, update the App Store link:
- Replace `https://apps.apple.com/app/buzzhive` with your actual App Store URL

## File Structure

```
website/
├── index.html          # Homepage
├── privacy.html         # Privacy Policy
├── terms.html          # Terms of Service
├── dmca.html           # DMCA Policy
├── styles.css          # Shared stylesheet
├── assets/             # Images and other assets
│   ├── buzz-logo.png   # Logo (copy from apps/mobile/assets/)
│   ├── buzz-hive-removed-background.png  # Hive icon (already there)
│   ├── screenshot-diary.png    # Diary feature screenshot
│   ├── screenshot-explore.png  # Map/Explore feature screenshot
│   ├── screenshot-hive.png     # Hive page screenshot
│   └── screenshot-ask.png     # Ask AI feature screenshot
└── README.md           # This file
```

## Customization

- **Colors**: Edit CSS variables in `styles.css` (lines 6-12)
- **Content**: Edit the HTML files directly
- **Logo**: Replace `assets/buzz-logo.png` with your logo

## Notes

- GitHub Pages supports custom domains with HTTPS (automatic SSL)
- Changes may take a few minutes to propagate after pushing
- The site is static HTML/CSS - no server-side processing needed

