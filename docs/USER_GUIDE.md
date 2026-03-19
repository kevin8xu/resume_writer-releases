# Intelligent Resume Writer - User Guide

**Version:** 1.4.3 Alpha
**Platform:** macOS
**Last Updated:** March 18, 2026

---

## What's New in v1.4.3

### 🎉 Local AI Mode - Complete Privacy!

You can now run AI models **entirely on your computer** with no internet connection required!

**Benefits:**
- ✅ Complete privacy - data never leaves your machine
- ✅ Works offline - no internet needed
- ✅ No API costs - free after setup
- ✅ Open source models

**Setup:** Settings → Local AI → Install Ollama → Download Models (~10-15 min)

**Performance:** ~2-3 minutes per resume (vs ~1 minute with cloud)

---

## Table of Contents

1. [What is Intelligent Resume Writer?](#what-is-intelligent-resume-writer)
2. [Getting Started](#getting-started)
3. [Configuration](#configuration)
4. [Using the App](#using-the-app)
5. [Features](#features)
6. [Troubleshooting](#troubleshooting)
7. [FAQ](#faq)
8. [Feedback & Support](#feedback--support)

---

## What is Intelligent Resume Writer?

Intelligent Resume Writer is an AI-powered resume generation tool that helps you create targeted, professional resumes tailored to specific job descriptions.

### Key Features

- **Career Vault:** Store and manage all your professional experiences
- **Smart Merge:** Automatically combines duplicate experiences from multiple resume uploads
- **Job Description Analysis:** Extracts key requirements from job postings
- **AI-Powered Generation:** Creates customized resumes using AI
- **Professional Templates:** Choose from 4 professional resume templates
- **PDF Export:** Download your resume as a professional PDF

### How It Works

1. **Import your resume** (PDF, Word, or text) → App extracts your experiences
2. **Upload job description** → App analyzes requirements
3. **Generate resume** → AI creates a targeted resume matching the job
4. **Download PDF** → Ready to submit!

---

## Getting Started

### Installation

1. **Download** the `.dmg` file from Google Drive
2. **Open** the `.dmg` file
3. **Drag** "Intelligent Resume Writer" to your Applications folder
4. **Launch** the app from Applications

### First Launch

**Important:** On first launch, you'll see a warning:

> "Intelligent Resume Writer" can't be opened because Apple cannot check it for malicious software.

**This is normal for alpha software.** To bypass:

**Option 1: Right-Click Method (Recommended)**
1. Right-click (or Control-click) the app icon
2. Select "Open" from the menu
3. Click "Open" in the warning dialog

**Option 2: System Preferences**
1. Try to open the app (warning appears)
2. Click "OK"
3. Go to: Apple Menu → System Preferences → Security & Privacy
4. Click "Open Anyway"
5. Enter your password if prompted

---

## Configuration

### AI Configuration (Required)

The app needs an AI provider to generate resumes.

#### Option 1: OpenAI (Recommended)

1. **Get API Key:**
   - Go to: https://platform.openai.com/api-keys
   - Sign in or create account
   - Click "Create new secret key"
   - Copy the key (starts with `sk-...`)

2. **Configure in App:**
   - Open Intelligent Resume Writer
   - Go to **Settings** tab
   - Enter your API key
   - Base URL: `https://api.openai.com/v1`
   - Model: `gpt-4o` (or `gpt-4o-mini` for cheaper/faster)
   - Click "Save Settings"

**Cost:** ~$0.01-0.05 per resume generation

#### Option 2: Ollama (Local AI - Recommended for Privacy)

**New in v1.4.3!** Run AI models locally on your computer for complete privacy.

**One-Click Setup (Recommended):**

1. **Open Settings → Local AI**
2. **Click "Install Ollama"** (automatic, ~2 minutes)
3. **Click "Download Recommended Models"** (~7 GB, ~10-15 minutes)
   - Llama 3.2 3B - Resume parsing (fast)
   - Llama 3.1 8B - Resume generation (quality)
   - Nomic Embed Text - Semantic search (tiny)
4. **Click "Test Local AI"** to verify
5. **Done!** Ready for private resume generation

**Manual Setup (Advanced):**

1. **Install Ollama:**
   ```bash
   brew install ollama
   ```

2. **Download models:**
   ```bash
   ollama pull llama3.2:3b
   ollama pull llama3.1:8b
   ollama pull nomic-embed-text
   ```

3. **Configure in App:**
   - Settings → Local AI section
   - Status should show: ✅ Installed ✅ Running
   - Models should show: ✅ All installed

**AI Mode Selection:**

Choose your preferred AI mode in Settings → Local AI:

- **Auto (Default):** Use local AI, fall back to cloud if needed
- **Local Only:** Use only local AI (no cloud)
- **Cloud Only:** Use only cloud AI (no local)

**Performance:**

| Task | Cloud AI | Local AI |
|------|----------|----------|
| Resume parsing | ~10-15s | ~15-20s |
| JD analysis | ~10-15s | ~15-20s |
| Resume generation | ~30-45s | ~60-90s |
| **Total** | **~1 min** | **~2-3 min** |

**Requirements:**
- 8GB+ RAM (16GB recommended)
- 10GB disk space
- macOS 11.0+ (Big Sur)

**Cost:** Free! (No API costs after setup)

### Storage Location (Optional)

By default, your data is stored in:
```
~/Library/Application Support/Electron/
```

To change this:
1. Go to **Settings** tab
2. Set "Storage Location" to your preferred folder
3. Click "Save Settings"
4. Restart the app

---

## Using the App

### Main Tabs

The app has 5 main sections:

1. **Vault** - Your career history
2. **Job Descriptions** - Job postings to target
3. **Generate** - Create targeted resumes
4. **History** - View past generated resumes
5. **Settings** - Configure the app
6. **Help** - This user guide

---

### 1. Career Vault

**Purpose:** Store all your professional experiences

#### Import Your Resume

1. Go to **Vault** tab
2. Click **"Import Resume"** button
3. Select your resume file (PDF, Word, or text)
4. App extracts your information automatically

**Supported formats:**
- PDF (.pdf)
- Word (.docx, .doc)
- Plain Text (.txt)
- Markdown (.md)

#### Add Experience Manually

1. Click **"+ Add Experience"** button
2. Fill in the form:
   - Type: Work, Education, Project, or Skill
   - Organization: Company/school name
   - Title: Your role
   - Dates: Start and end dates
   - Description: What you did
   - Tags/Skills: Relevant skills (comma-separated)
3. Click "Add Experience"

#### Edit Experience

1. Click the **pencil icon** on any experience card
2. Modify the information
3. Click "Save Changes"

#### Delete Experience

1. Click the **trash icon** on any experience card
2. Confirm deletion

#### Smart Merge

When you import multiple resumes:
- App **automatically detects duplicates**
- **Merges** similar experiences
- **Flags conflicts** for your review
- Keeps your Master Profile up-to-date

---

### 2. Job Descriptions

**Purpose:** Store and analyze job postings

#### Add Job Description

**Option 1: Upload File**
1. Go to **Job Descriptions** tab
2. Click **"Upload File"**
3. Select job description file (PDF, Word, or text)
4. App analyzes and extracts requirements

**Option 2: Paste Text**
1. Copy job description from website/email
2. Paste into text area
3. Click **"Analyze JD"**

#### What Gets Extracted

- Job title
- Company name
- Key skills and keywords
- Requirements
- Summary

#### Using Stored JDs

- All analyzed JDs are saved
- Select one when generating resume
- Reuse for multiple resume versions

---

### 3. Generate Resume

**Purpose:** Create targeted resumes

#### Step-by-Step

1. **Select Profile**
   - Choose your Master Profile (or specific profile)

2. **Select Job Description**
   - Choose from your stored JDs

3. **Choose Template**
   - **Modern:** Clean, contemporary (tech/startups)
   - **Classic:** Traditional, professional (finance/law)
   - **Minimal:** Simple, clean (design/academia)
   - **Executive:** Sophisticated (leadership roles)

4. **Select Experiences (Optional)**
   - Click "Select Experiences" dropdown
   - Uncheck irrelevant experiences
   - Keep only relevant ones for this job

5. **Generate Resume**
   - Click "Generate Resume"
   - Wait 30-60 seconds
   - Review the generated content

6. **Review & Export**
   - Toggle between **Markdown** and **PDF** views
   - Review carefully
   - Download PDF using built-in controls

#### Tips for Best Results

- ✅ **Select relevant experiences** for the specific job
- ✅ **Choose appropriate template** for the industry
- ✅ **Review AI output** before submitting
- ✅ **Customize further** if needed
- ✅ **Generate multiple versions** for different roles

---

### 4. Resume History

**Purpose:** View and manage past resumes

#### View Generated Resume

1. Go to **History** tab
2. Click on any resume card
3. Toggle between Markdown and PDF views

#### Delete Old Resume

1. Click the **trash icon** on resume card
2. Confirm deletion
3. Both database record and files are deleted

#### Version Tracking

- Multiple resumes for same job are versioned (v1, v2, v3...)
- Compare different approaches
- Revert to previous versions if needed

---

### 5. Settings

**Purpose:** Configure the app

#### AI Configuration

- **API Key:** Your OpenAI or other provider key
- **Base URL:** API endpoint
- **Generation Model:** Model for resume generation
- **Extraction Model:** Model for parsing resumes/JDs

#### Storage

- **Storage Location:** Where your data is stored
- Default: `~/Library/Application Support/Electron/`

#### Smart Merge Preferences

- **Auto-Merge Threshold:** When to merge automatically (default: 80%)
- **Review Threshold:** When to flag for review (default: 50%)
- **Prefer Newer Dates:** Use more recent date ranges
- **Prefer Longer Descriptions:** Keep more detailed content
- **Notify on Auto-Merge:** Show notifications

---

### 6. Help

**Purpose:** Access documentation

- Click **Help** button in top navigation
- Browse sections
- Search for topics

---

## Features

### Career Management

- ✅ Import multiple resumes
- ✅ Manual experience entry
- ✅ Edit and delete experiences
- ✅ Tag experiences with skills
- ✅ Filter by type (work, education, project, skill)
- ✅ Automatic duplicate detection
- ✅ Smart merge with conflict resolution

### Job Description Analysis

- ✅ Upload or paste JDs
- ✅ Extract key requirements
- ✅ Identify keywords
- ✅ Store for future use

### Resume Generation

- ✅ AI-powered content generation
- ✅ 4 professional templates
- ✅ Experience selection
- ✅ Targeted to specific JDs
- ✅ PDF export
- ✅ Version tracking

### User Experience

- ✅ Clean, modern interface
- ✅ Intuitive navigation
- ✅ Real-time preview
- ✅ Comprehensive help system

---

## Troubleshooting

### App Won't Open

**Problem:** "App can't be opened" warning

**Solution:**
1. Right-click app icon
2. Select "Open"
3. Click "Open" in warning dialog

Or:
1. System Preferences → Security & Privacy
2. Click "Open Anyway"

---

### Build Fails

**Problem:** `npm run build` fails

**Solution:**
```bash
# Clean reinstall
rm -rf node_modules package-lock.json
npm install
npm run build
```

---

### AI Generation Fails

**Problem:** "Generation failed" error

**Possible Causes:**
1. **Invalid API key** - Check your API key in Settings
2. **No internet** - Check your connection
3. **API quota exceeded** - Check OpenAI dashboard
4. **Invalid model** - Try `gpt-4o-mini` instead

**Solution:**
1. Go to Settings
2. Verify API key
3. Test with different model
4. Check OpenAI account status

---

### PDF Won't Download

**Problem:** Can't save PDF

**Solution:**
- Use browser's built-in PDF controls
- Click print icon in PDF viewer
- Choose "Save as PDF"

---

### Merge Not Working

**Problem:** Duplicate experiences not merging

**Solution:**
1. Go to Settings → Smart Merge Preferences
2. Lower "Auto-Merge Threshold" (try 70%)
3. Re-import resume

---

## FAQ

### Is my data secure?

**Yes.** All data is stored locally on your computer. Nothing is sent to external servers except:
- Your resume/JD text to the AI provider (OpenAI, Ollama, etc.) for processing
- Only when you generate resumes or analyze JDs

### Do I need an OpenAI account?

**Yes, for cloud AI.** You need an OpenAI API key for the default AI provider.

**Alternative:** Use Ollama for free, local AI (no account needed).

### How much does it cost?

**App:** Free (alpha version)

**AI Usage:**
- **OpenAI:** ~$0.01-0.05 per resume
- **Ollama:** Free (uses your computer's resources)

### Can I use it on Windows or Linux?

**Currently:** macOS only (alpha)

**Future:** Windows and Linux versions planned

### Is the source code available?

**Currently:** Private repository

**Future:** May become open source

### How do I report bugs?

**Email:** [Your Email Here]

**Include:**
- What you were trying to do
- What happened
- Error messages (if any)
- Screenshots (helpful)

---

## Feedback & Support

### Report Issues

**Email:** [Your Email Here]  
**Subject:** [Alpha Feedback] Brief description

### Feature Requests

We'd love to hear what features you'd like to see!

**Email:** [Your Email Here]  
**Subject:** [Feature Request] Feature name

### General Feedback

How's the app working for you? What do you like? What needs improvement?

**Email:** [Your Email Here]

---

## Known Limitations (Alpha)

- ❌ No LaTeX templates (HTML/CSS only)
- ❌ No template customization
- ❌ No semantic search for experiences
- ❌ No collaborative features
- ❌ No cloud sync
- ❌ macOS only

## Roadmap

### Phase 8: LaTeX Support
- Professional typesetting
- Academic templates
- Better formatting control

### Phase 9: Semantic Search
- Find experiences by meaning
- Better experience selection
- Smart recommendations

### Phase 10: Refinement UI
- Interactive feedback
- Multi-iteration generation
- Version comparison

### Phase 11: Production Build
- Code signing
- Auto-updates
- Windows/Linux support

---

**Thank you for participating in the alpha test!** 🎉

Your feedback helps make Intelligent Resume Writer better for everyone.

---

**Last Updated:** March 9, 2026  
**Version:** 1.4.0 Alpha
