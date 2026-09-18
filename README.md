# 📰 Daily Financial News Automation

Automated daily financial news briefing system that runs 4 times daily (8 AM, 1 PM, 5 PM, 8 PM IST) to curate trending financial and company news.

## Features

✨ **Automatic Daily Updates** - Runs at 8 AM, 1 PM, 5 PM, 8 PM (IST)  
📊 **Top 2 Trending News** - Curated financial & company news  
🎨 **Instagram Ready** - Image prompts in 9:16 aspect ratio  
⏱️ **60-Second Reads** - Concise, impactful summaries  
🚫 **Deduplication** - Avoids repeating news unless updated  
🔄 **Git Auto-Commit** - Summaries saved and tracked in git  

## 📂 Directory Structure

```
.
├── README.md
├── .gitignore
├── news-archive/           # Historical news storage
│   └── 2026-09-18.md       # Daily news files
├── instagram-prompts/      # Image generation prompts
│   └── 2026-09-18.md
├── tracking/               # Deduplication tracking
│   └── seen-news.json      # Hash of previously posted news
└── .github/
    └── workflows/          # Optional: CI/CD workflows
```

## 📝 File Formats

### Daily News Files (news-archive/)
```markdown
# Financial News Briefing - 2026-09-18

## 📍 Slot 1: 8:00 AM IST

### Trending News #1: [Headline]
- **Source**: News Source Name
- **Summary**: 60-second summary...
- **Impact**: Market/investor impact
- **Link**: [URL]

### Trending News #2: [Headline]
- **Source**: News Source Name
- **Summary**: 60-second summary...
- **Impact**: Market/investor impact
- **Link**: [URL]

---

## 📍 Slot 2: 1:00 PM IST
[Similar format for next update]

---

## 📍 Slot 3: 5:00 PM IST
[Similar format for next update]

---

## 📍 Slot 4: 8:00 PM IST
[Similar format for next update]
```

### Instagram Prompts (instagram-prompts/)
```markdown
# Instagram Visual Prompts - 2026-09-18

## 8:00 AM IST

### Prompt #1
**Topic**: [News headline]
**Style**: Modern financial design, clean typography
**Colors**: [Color palette]
**Text**: "[Concise 1-line headline for IG]"
**Aspect Ratio**: 9:16 (vertical)

### Prompt #2
[Similar format]

---
## 1:00 PM IST, 5:00 PM IST, 8:00 PM IST
[Repeat structure for each time slot]
```

## 🔐 Deduplication (tracking/seen-news.json)

```json
{
  "2026-09-18": [
    {
      "headline": "Market news headline",
      "hash": "sha256_hash_of_headline",
      "posted_at": "2026-09-18T08:00:00Z",
      "source": "Source Name"
    }
  ]
}
```

## 🚀 Setup Instructions

### 1. Create GitHub Repository
```bash
# Create a new empty repo on GitHub named: financial-news-automation
# Then push this local copy
git init
git add .
git commit -m "Initial commit: Financial news automation setup"
git branch -m main
git remote add origin https://github.com/YOUR_USERNAME/financial-news-automation.git
git push -u origin main
```

### 2. Automation Schedule
- **Model**: Claude Sonnet 5
- **Frequency**: Every 3 hours starting 8 AM IST (2:30 AM UTC)
- **Runs**: 4 times daily
- **Output**: Auto-committed to GitHub

### 3. What Gets Tracked
✅ Daily news summaries  
✅ Instagram image prompts  
✅ Duplicate detection  
✅ Source attribution  
✅ Historical archive  

## 📊 Usage

The automation agent will:
1. Fetch latest financial news via web search
2. Identify top 2 trending stories (avoiding duplicates)
3. Write 60-second summaries
4. Generate Instagram image prompts (9:16)
5. Commit everything to GitHub with timestamp

Check the `news-archive/` folder for daily summaries.  
Check the `instagram-prompts/` folder for visual content prompts.

---

**Last Updated**: 2026-09-18  
**Automation Status**: Ready to deploy
