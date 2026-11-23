# IONOS Website Troubleshooting Guide

## Common Issues and Solutions

### 1. Website Not Loading (Most Common)

**Symptoms:**
- Website shows "404 Not Found"
- "Internal Server Error" 
- Blank white page
- "This site can't be reached"

**Solutions:**

#### A. Check File Upload Location
- Files must be uploaded to the **htdocs** or **public_html** folder (not root)
- Main file should be named `index.html` (not `home.html`)
- File names are case-sensitive on IONOS servers

#### B. Check .htaccess File
1. If site doesn't load, try renaming `.htaccess` to `.htaccess-backup`
2. Test if site loads without .htaccess
3. If it works, the .htaccess file was causing issues

#### C. Check File Permissions
- HTML files: 644 or 755
- Images: 644
- .htaccess: 644

### 2. Navigation Issues

**Symptoms:**
- Links between pages don't work
- Images not loading

**Solutions:**

#### A. Check File Paths
- All files should be in the same directory
- Use relative paths: `href="about.html"` ✅
- Not absolute paths: `href="/full/path/about.html"` ❌

### 3. Images Not Loading

**Symptoms:**
- Broken image icons
- Missing logo/pictures

**Solutions:**

#### A. Check File Paths
- Use relative paths: `src="Glideblinds.png"` ✅
- Not absolute paths: `src="/full/path/Glideblinds.png"` ❌

#### B. Verify Upload
- Ensure `Glideblinds.png` is uploaded to same folder as `index.html`
- Check file name matches exactly (case-sensitive)

### 4. Forms Not Working

**Symptoms:**
- Contact form doesn't send emails
- "Method not allowed" errors

**Solutions:**

#### A. Current Setup Uses mailto:
- Our forms use `mailto:` links (client-side)
- Should work without server configuration
- If not working, check browser settings

#### B. For Server-Side Forms (Future)
- Would need PHP support
- IONOS supports PHP on most plans

### 5. Address Autocomplete Not Working

**Symptoms:**
- Address suggestions don't appear
- API errors in browser console

**Solutions:**

#### A. Check Internet Connection
- Feature requires external API calls
- Test on different networks

#### B. Fallback System
- Should show static Ottawa addresses if API fails
- Check browser console for errors

## Step-by-Step Upload Process

### 1. Prepare Files
```
Your files should look like:
├── index.html
├── about.html
├── blog.html
├── contact.html
├── services.html
├── Glideblinds.png
├── .htaccess-simple (rename to .htaccess)
└── ssl-checker.html (optional)
```

### 2. IONOS Upload Steps
1. Log into IONOS control panel
2. Go to "Websites & Domains"
3. Click "File Manager" or use FTP
4. Navigate to `htdocs` or `public_html` folder
5. Upload ALL files to this folder (not subfolders)
6. Rename `.htaccess-simple` to `.htaccess`

### 3. Test Process
1. Visit `http://yourdomain.com` (not HTTPS initially)
2. Check if homepage loads
3. Test navigation between pages
4. Test contact forms
5. Check images display correctly

### 4. Final Testing
1. Test all pages load correctly
2. Test navigation between pages
3. Test contact forms
4. Verify images display properly

## Quick Fixes to Try First

1. **Rename .htaccess temporarily**
   ```bash
   .htaccess → .htaccess-backup
   ```

2. **Check main file name**
   - Must be `index.html` (not `home.html` or `main.html`)

3. **Verify upload location**
   - Files in `htdocs/` or `public_html/` folder
   - Not in root directory

4. **Test your domain**
   - Visit `http://yourdomain.com`
   - Should load the homepage

5. **Check browser console**
   - Press F12 → Console tab
   - Look for error messages

## Contact Information

If issues persist:
- Check IONOS support documentation
- Contact IONOS technical support
- Verify domain DNS settings point to IONOS servers

## Files to Upload

**Essential Files (Upload These):**
- index.html ✅
- about.html ✅
- blog.html ✅
- contact.html ✅
- services.html ✅
- Glideblinds.png ✅
- .htaccess ✅

**Optional Files:**
- README.md
- Documentation files (.md files)

**Do NOT Upload:**
- Development files
- Backup files
- Any files you don't need for the website
