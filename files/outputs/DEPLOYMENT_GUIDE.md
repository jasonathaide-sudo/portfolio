# Netlify Deployment & Resume/Certificate Setup Guide

## 📁 Your Local Folder Structure

You've already created:
```
C:\Users\jason\Downloads\files\outputs\
├── portfolio.html          ✅ Main website file
├── Jason_Athaide_photo.jpg ✅ Your hero photo
├── portfolio-content-brief.md
├── README.md
└── (More files here...)
```

---

## 📥 Step 1: Add Your Resume (5 Minutes)

### Option A: Convert Your Resume to PDF (Recommended)

1. **Find your resume file:**
   - Look for: `JASON_ATHAIDE_-_resume.md` or similar in your uploads
   - Or your resume in Word/Google Docs format

2. **Convert to PDF:**
   - **If Word (.docx):** File → Save As → PDF Format → Save
   - **If Google Docs:** File → Download → PDF Document
   - **If already a PDF:** Skip to step 3

3. **Save as `resume.pdf`:**
   - Save/rename to exactly: `resume.pdf` (all lowercase)
   - Place in your outputs folder:
     ```
     C:\Users\jason\Downloads\files\outputs\resume.pdf
     ```

4. **Verify the file exists:**
   - Go to `C:\Users\jason\Downloads\files\outputs\`
   - You should see: `resume.pdf` alongside `portfolio.html`

### Option B: Quick Alternative (Google Drive)

1. Upload resume.pdf to Google Drive
2. Get shareable link
3. Use in HTML instead:
   ```html
   <button class="cta-button cta-secondary" onclick="window.open('https://drive.google.com/uc?export=download&id=YOUR_FILE_ID')">Download Resume</button>
   ```

---

## 📸 Step 2: Add Certificate Images (Optional but Recommended)

### Create Folder Structure

1. **In your outputs folder, create two subfolders:**
   ```
   C:\Users\jason\Downloads\files\outputs\
   ├── portfolio.html
   ├── Jason_Athaide_photo.jpg
   ├── resume.pdf
   ├── Education/          ← Create this folder
   ├── SKILL/              ← Create this folder
   └── README.md
   ```

2. **How to create folders on Windows:**
   - Open File Explorer
   - Navigate to: `C:\Users\jason\Downloads\files\outputs\`
   - Right-click → New → Folder
   - Name it: `Education`
   - Repeat for `SKILL` folder

### Add Certificate Images

You have these certificate files already (from uploads):
- `Be10x_Certificates.md` → Convert to images
- `Certificate_-_CLAUDE_-_AI_Fluency_Framework___Foundations.md` → Image
- `Certificate_-_ANTHROPIC_CLAUDE_101.md` → Image
- `Diploma_-_Clare_s_Public_Speaking_and_Comms_Skills1.md` → Image
- `FIS_-_LEAP.md` → Image (if applicable)
- And more...

**Steps:**

1. **Screenshot the certificates:**
   - Open each certificate file
   - Take screenshot (Print Screen or Snip Tool)
   - Save as PNG image:
     - AI Agents → `Education/AI-Agents-Cert.png`
     - Claude 101 → `Education/Claude-101-Cert.png`
     - Prompt Engineering → `Education/Prompt-Engineering-Cert.png`
     - n8n → `SKILL/n8n-Cert.png`
     - MCP Integration → `SKILL/MCP-Integration-Cert.png`
     - Lean Six Sigma → `Education/Lean-Six-Sigma-Cert.png`
     - Public Speaking → `Education/Public-Speaking-Cert.png`

2. **Folder structure after adding images:**
   ```
   C:\Users\jason\Downloads\files\outputs\
   ├── portfolio.html
   ├── Jason_Athaide_photo.jpg
   ├── resume.pdf
   ├── Education/
   │   ├── AI-Agents-Cert.png
   │   ├── Claude-101-Cert.png
   │   ├── Prompt-Engineering-Cert.png
   │   ├── Lean-Six-Sigma-Cert.png
   │   └── Public-Speaking-Cert.png
   ├── SKILL/
   │   ├── n8n-Cert.png
   │   └── MCP-Integration-Cert.png
   └── README.md
   ```

3. **Update portfolio.html to display images:**

   Find this section (around line 800):
   ```html
   <div class="cert-item">
       <div class="cert-image" style="background: linear-gradient(135deg, #3b82f6 0%, #1e40af 100%); font-size: 2rem;">🤖</div>
       <div class="cert-info">
           <h4>AI Agents & Autonomous Systems</h4>
   ```

   Replace with:
   ```html
   <div class="cert-item">
       <div class="cert-image">
           <img src="./Education/AI-Agents-Cert.png" alt="AI Agents Certificate" onerror="this.parentElement.style.fontSize='2rem'; this.parentElement.textContent='🤖'">
       </div>
       <div class="cert-info">
           <h4>AI Agents & Autonomous Systems</h4>
   ```

   **Note:** The `onerror` fallback keeps the emoji if image doesn't load, so your site stays beautiful either way.

---

## 🚀 Step 3: Re-Deploy to Netlify

### Quick Method (Drag & Drop - 2 Minutes)

1. **Gather all files from your local folder:**
   ```
   C:\Users\jason\Downloads\files\outputs\
   ```
   Select and copy:
   - portfolio.html
   - Jason_Athaide_photo.jpg
   - resume.pdf ← NEW
   - Education/ folder ← NEW (if added)
   - SKILL/ folder ← NEW (if added)

2. **Go to your Netlify site:**
   - Open: https://app.netlify.com/
   - Log in with your account
   - Click on your portfolio site

3. **Redeploy (Option 1 - Simplest):**
   - Find the **Deploys** section
   - Click **Triggers** → **Deploy site**
   - Netlify will grab the latest files from wherever you deployed from

4. **Redeploy (Option 2 - Drag & Drop):**
   - Find the **Deploys** section
   - Look for **Drag and drop your site folder here**
   - Drag all files from `C:\Users\jason\Downloads\files\outputs\` onto that area
   - Wait 30 seconds for deploy to finish ✅
   - Your site updates automatically

5. **Verify deployment:**
   - Go to your portfolio URL
   - Click "Download Resume" button
   - Should download `Jason_Athaide_Resume.pdf` ✅
   - Scroll to Certifications section
   - Should see certificate images (or fallback emojis)

---

## 🔧 Advanced: Manual HTML Updates (If Needed)

If you want to update certificate display before deploying, edit `portfolio.html`:

### Replace emoji with image (Example for AI Agents):

**BEFORE:**
```html
<div class="cert-image" style="background: linear-gradient(135deg, #3b82f6 0%, #1e40af 100%); font-size: 2rem;">🤖</div>
```

**AFTER:**
```html
<div class="cert-image">
    <img src="./Education/AI-Agents-Cert.png" alt="AI Agents Certificate" onerror="this.parentElement.style.fontSize='2rem'; this.parentElement.textContent='🤖'">
</div>
```

### All Certificate Image Replacements:

**Find section starting around line 775** in portfolio.html and replace:

```html
<!-- AI Agents -->
<div class="cert-image">
    <img src="./Education/AI-Agents-Cert.png" alt="AI Agents Certificate" onerror="this.parentElement.style.fontSize='2rem'; this.parentElement.textContent='🤖'">
</div>

<!-- AI Fluency -->
<div class="cert-image">
    <img src="./Education/AI-Fluency-Cert.png" alt="AI Fluency Certificate" onerror="this.parentElement.style.fontSize='2rem'; this.parentElement.textContent='🧠'">
</div>

<!-- Claude 101 -->
<div class="cert-image">
    <img src="./Education/Claude-101-Cert.png" alt="Claude 101 Certificate" onerror="this.parentElement.style.fontSize='2rem'; this.parentElement.textContent='📚'">
</div>

<!-- n8n Automation -->
<div class="cert-image">
    <img src="./SKILL/n8n-Cert.png" alt="n8n Workflow Automation Certificate" onerror="this.parentElement.style.fontSize='2rem'; this.parentElement.textContent='⚙️'">
</div>

<!-- Lean Six Sigma -->
<div class="cert-image">
    <img src="./Education/Lean-Six-Sigma-Cert.png" alt="Lean Six Sigma Certificate" onerror="this.parentElement.style.fontSize='2rem'; this.parentElement.textContent='🎯'">
</div>

<!-- Public Speaking -->
<div class="cert-image">
    <img src="./Education/Public-Speaking-Cert.png" alt="Public Speaking Certificate" onerror="this.parentElement.style.fontSize='2rem'; this.parentElement.textContent='🎤'">
</div>
```

---

## ✅ Complete Deployment Checklist

- [ ] **Resume Added**
  - [ ] Created `resume.pdf` from your existing resume
  - [ ] Placed in: `C:\Users\jason\Downloads\files\outputs\resume.pdf`
  - [ ] Tested that file opens correctly

- [ ] **Certificate Folders Created** (Optional)
  - [ ] Created `Education/` folder
  - [ ] Created `SKILL/` folder
  - [ ] Added certificate images to appropriate folders

- [ ] **HTML Updated** (If adding certificate images)
  - [ ] Updated certificate section with image paths
  - [ ] Verified fallback emojis in place for error handling
  - [ ] Tested on local machine first

- [ ] **Re-Deployed to Netlify**
  - [ ] Collected all files from outputs folder
  - [ ] Used Drag & Drop or Deploy Trigger
  - [ ] Waited for green "Published" status

- [ ] **Tested Live Portfolio**
  - [ ] Clicked "Download Resume" button
  - [ ] Verified PDF downloads with correct name
  - [ ] Scrolled to Certifications section
  - [ ] Verified certificate images display correctly

---

## 🐛 Troubleshooting

### Resume Download Not Working

**Problem:** Button shows alert instead of downloading

**Solution:**
1. Make sure file is named exactly: `resume.pdf` (lowercase)
2. Make sure it's in same folder as `portfolio.html`
3. Re-deploy to Netlify using Drag & Drop
4. Wait 1-2 minutes for Netlify to process
5. Hard refresh browser: `Ctrl+Shift+R` (Windows) or `Cmd+Shift+R` (Mac)

### Certificate Images Not Showing

**Problem:** Certificates showing emoji instead of images

**Solution:**
1. Check file paths in HTML match exactly (case-sensitive)
   - Example: `./Education/AI-Agents-Cert.png` must match actual filename
2. Verify image files are in correct folders
3. Check image format: Should be PNG or JPG (not other formats)
4. Re-deploy entire folder to Netlify

### "Resume doesn't exist" Alert Keeps Showing

**Problem:** Can't get rid of alert

**Solution:**
1. Add `resume.pdf` to your outputs folder
2. Re-deploy to Netlify
3. Wait 30 seconds
4. Hard refresh your browser
5. Try again

---

## 📊 File Sizes Reference

Your files should be approximately:
- `portfolio.html` → ~42 KB
- `Jason_Athaide_photo.jpg` → ~27 KB
- `resume.pdf` → ~200-500 KB (typical)
- Each certificate image → ~50-200 KB
- **Total deployment** → ~500 KB - 1 MB (perfectly fine)

Netlify has no size limits for static sites.

---

## 🎯 Your Folder Structure (Final)

```
C:\Users\jason\Downloads\files\outputs\
│
├── portfolio.html                    ✅ Main website
├── Jason_Athaide_photo.jpg          ✅ Hero photo
├── resume.pdf                       ✅ Download button target
│
├── Education/                       📁 Certificate folder
│   ├── AI-Agents-Cert.png
│   ├── Claude-101-Cert.png
│   ├── AI-Fluency-Cert.png
│   ├── Prompt-Engineering-Cert.png
│   ├── Lean-Six-Sigma-Cert.png
│   └── Public-Speaking-Cert.png
│
├── SKILL/                           📁 Skill folder
│   ├── n8n-Cert.png
│   └── MCP-Integration-Cert.png
│
├── portfolio-content-brief.md       📄 Content reference
├── README.md                        📄 Usage guide
└── DEPLOYMENT_GUIDE.md              📄 This file
```

---

## 🚀 Quick Summary

1. **Add resume.pdf** → Save your resume as PDF in outputs folder
2. **Add certificate images** (optional) → Create Education/ and SKILL/ folders, add images
3. **Update HTML** (optional) → Replace emoji with image tags
4. **Re-deploy** → Drag & drop outputs folder to Netlify
5. **Test** → Click Download Resume, scroll to Certifications
6. **Done** → Share your live portfolio! 🎉

---

## 💬 Need Help?

If anything doesn't work:
1. Check file names (must be exact lowercase)
2. Verify folder structure matches above
3. Make sure files are in: `C:\Users\jason\Downloads\files\outputs\`
4. Hard refresh browser: `Ctrl+Shift+R`
5. Wait 1-2 minutes after deploying to Netlify

Your portfolio is live and working! The resume and certificate images just need to be added to make it 100% complete. 🎯
