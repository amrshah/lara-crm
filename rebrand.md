# AlamiaConnect CRM - Complete Setup Guide

## 📋 Overview

This guide will help you set up AlamiaConnect CRM based on Krayin CRM with:
1. ✅ Automated rebranding (Krayin → AlamiaConnect)
2. ✅ Proper legal attribution (MIT license compliance)
3. ✅ Weekly upstream sync automation
4. ✅ Standardized image filenames

---

## 🚀 Step-by-Step Setup

### **Step 1: Fork Krayin CRM**

1. Go to the [Krayin CRM GitHub repository](https://github.com/krayin/laravel-crm)
2. Click the **"Fork"** button in the top-right corner
3. In the fork dialog:
   - **Owner**: Select `amrshah`
   - **Repository name**: Change to `AlamiaConnect`
   - **Description**: "AlamiaConnect CRM - Customer Relationship Management System by AlamiaSoft"
   - ✅ Check "Copy the main branch only" (you'll sync with upstream via automation)
4. Click **"Create fork"**

---

### **Step 2: Clone Your Fork Locally**

```bash
# Clone your forked repository
git clone https://github.com/amrshah/AlamiaConnect.git
cd AlamiaConnect
```

---

### **Step 3: Add GitHub Actions Workflows**

Create the `.github/workflows` directory and add the workflow files:

```bash
# Create workflows directory
mkdir -p .github/workflows

# Create the rebrand workflow file
# Copy the content from "rebrand.yml" artifact into this file
nano .github/workflows/rebrand.yml
# (Paste the rebrand.yml content, save with Ctrl+O, exit with Ctrl+X)

# Create the upstream sync workflow file
# Copy the content from "sync-upstream.yml" artifact into this file
nano .github/workflows/sync-upstream.yml
# (Paste the sync-upstream.yml content, save with Ctrl+O, exit with Ctrl+X)
```

**Alternative (easier)**: Download the files directly:
- Save `rebrand.yml` from the artifact above
- Save `sync-upstream.yml` from the artifact above
- Place them in `.github/workflows/` directory

---

### **Step 4: Commit and Push Workflows**

```bash
# Add the workflow files
git add .github/workflows/

# Commit
git commit -m "Add automated rebranding and upstream sync workflows"

# Push to your GitHub repository
git push origin main
```

---

### **Step 5: Run the Rebranding Workflow**

1. Go to your GitHub repository: `https://github.com/amrshah/AlamiaConnect`
2. Click on the **"Actions"** tab
3. In the left sidebar, click **"Rebrand Krayin to AlamiaConnect"**
4. Click the **"Run workflow"** dropdown button
5. Click **"Run workflow"** (green button)
6. Wait for the workflow to complete (usually 2-3 minutes)

The workflow will:
- Create a new branch called `rebranding-automated`
- Replace all "Krayin" references with "AlamiaConnect"
- Standardize image filenames (logo.png, favicon.ico, etc.)
- Create legal files (LICENSE, NOTICE.third-party.txt, ATTRIBUTION.md)
- Update configuration files
- Create a Pull Request for you to review

---

### **Step 6: Review and Merge the Rebranding PR**

1. Go to the **"Pull requests"** tab in your repository
2. Open the PR titled: **"🎨 Automated Rebranding: Krayin → AlamiaConnect"**
3. Review all changes carefully:
   - Check that all "Krayin" references are replaced
   - Verify configuration files are correct
   - Review legal files (LICENSE, NOTICE.third-party.txt)
4. If everything looks good, click **"Merge pull request"**
5. Click **"Confirm merge"**
6. Delete the `rebranding-automated` branch (GitHub will prompt you)

---

### **Step 7: Replace Image Files Manually**

Now that the code references have been standardized, replace the actual image files:

```bash
# Pull the latest changes
git pull origin main

# Find and replace these image files with your custom designs:
# - logo.png or logo.svg
# - logo-dark.png or logo-dark.svg (if exists)
# - favicon.ico
# - icon.png

# Example locations (search your repository):
find . -name "logo.png" -o -name "logo.svg" -o -name "favicon.ico"

# Replace the files with your designs (keep the same filenames)
# Then commit
git add .
git commit -m "Add custom branding images for AlamiaConnect"
git push origin main
```

**Image Requirements:**
- **logo.png/logo.svg**: Main logo (recommended: transparent background, ~200x60px)
- **logo-dark.png/logo-dark.svg**: Dark mode logo (if applicable)
- **favicon.ico**: Browser favicon (16x16, 32x32, 48x48px)
- **icon.png**: App icon (recommended: 512x512px)

---

### **Step 8: Verify Upstream Sync Automation**

The upstream sync workflow will run automatically every Monday at 9:00 AM UTC. To test it manually:

1. Go to **"Actions"** tab
2. Click **"Sync with Krayin Upstream"** in the left sidebar
3. Click **"Run workflow"** dropdown
4. Click **"Run workflow"** button

This will:
- Check for new updates from Krayin CRM
- Create a draft PR with upstream changes to the `upstream-sync` branch
- List all new commits from upstream
- Allow you to review before merging

---

## 📁 Files Created by Automation

After the rebranding workflow completes, you'll have these new files:

### **1. NOTICE.third-party.txt**
Contains the MIT License attribution for Krayin CRM (required for legal compliance)

### **2. LICENSE**
Your proprietary EULA (End User License Agreement) for AlamiaConnect CRM

### **3. docs/ATTRIBUTION.md**
Detailed attribution documentation explaining the relationship with Krayin CRM

### **4. Updated README.md**
Includes attribution section mentioning Krayin CRM

### **5. Updated Configuration Files**
- `composer.json` - Package name and description updated
- `package.json` - Package name updated
- `.env.example` - App name and URL updated

---

## 🔄 Ongoing Maintenance

### **Weekly Upstream Sync**

Every Monday, the workflow will automatically:
1. Check for new Krayin CRM updates
2. Create a draft PR if updates exist
3. List all new commits
4. Wait for your review

**To handle upstream updates:**
1. Review the draft PR created by the automation
2. Check for conflicts with your customizations
3. Test thoroughly in a staging environment
4. Mark as "Ready for review" when satisfied
5. Merge the PR

### **Manual Upstream Sync**

You can trigger the sync manually anytime:
1. Go to **Actions** → **Sync with Krayin Upstream**
2. Click **"Run workflow"**

---

## ⚠️ Important Notes

### **Legal Compliance**
- ✅ Keep `NOTICE.third-party.txt` - Required for MIT license compliance
- ✅ Keep `docs/ATTRIBUTION.md` - Documents Krayin attribution
- ✅ Keep the attribution section in README.md
- ✅ Your LICENSE (EULA) governs the use of AlamiaConnect as a whole

### **Image Files**
- All code now references standardized filenames (logo.png, favicon.ico, etc.)
- You only need to replace the actual image files
- Keep the same filenames to avoid breaking references

### **Upstream Merges**
- Always review upstream changes carefully
- Test in staging before merging to production
- Check that your customizations aren't overwritten
- Verify branding remains intact (no Krayin references reintroduced)

### **Conflicts**
If the upstream sync creates conflicts:
1. Clone the `upstream-sync` branch locally
2. Resolve conflicts manually
3. Run tests
4. Push back to the branch
5. Merge the PR

---

## 🛠️ Local Development Setup

After rebranding, set up your local development environment:

```bash
# Install PHP dependencies
composer install

# Install Node dependencies
npm install

# Copy environment file
cp .env.example .env

# Generate application key
php artisan key:generate

# Configure your database in .env file
# DB_CONNECTION=mysql
# DB_HOST=127.0.0.1
# DB_PORT=3306
# DB_DATABASE=alamiaconnect
# DB_USERNAME=your_username
# DB_PASSWORD=your_password

# Run migrations
php artisan migrate

# Seed database
php artisan db:seed

# Build frontend assets
npm run dev

# Start development server
php artisan serve
```

Access your CRM at: `http://localhost:8000/admin`

**Default credentials:**
- Email: `amr.shah@gmail.com`
- Password: `admin123`

⚠️ **Change the default password immediately!**

---

## 📞 Support & Contact

- **Company**: AlamiaSoft
- **Email**: amr.shah@gmail.com
- **Website**: https://amrshah.github.io
- **GitHub**: https://github.com/amrshah/AlamiaConnect

---

## ✅ Checklist

Use this checklist to track your setup progress:

- [ ] Forked Krayin CRM to AlamiaConnect repository
- [ ] Cloned repository locally
- [ ] Added workflow files (.github/workflows/)
- [ ] Pushed workflow files to GitHub
- [ ] Ran the rebranding workflow
- [ ] Reviewed and merged rebranding PR
- [ ] Replaced image files (logo.png, favicon.ico, etc.)
- [ ] Verified legal files (LICENSE, NOTICE.third-party.txt)
- [ ] Tested upstream sync workflow
- [ ] Set up local development environment
- [ ] Changed default admin password
- [ ] Reviewed and understood ongoing maintenance procedures

---

## 🎉 Next Steps

Now that rebranding is complete, you can proceed with:

1. **Step 2: VPS Deployment Automation** (coming next)
   - Automated deployment to your VPS
   - Remote database configuration (client's VPS)
   - CI/CD pipeline setup

Would you like me to create the VPS deployment automation next?

---

**Generated for**: AlamiaConnect CRM Setup  
**Date**: 2025  
**Version**: 1.0