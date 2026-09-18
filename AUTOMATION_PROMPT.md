# Financial News Automation Agent Prompt

## 🎯 Objective
Fetch the latest financial and company news, identify the top 2 trending stories, create readable summaries (60-second read), generate Instagram image prompts (9:16 aspect ratio), and commit everything to the repository.

## 📋 Steps

### 1. Fetch Latest News
- Search for trending financial news from the past 3 hours
- Look for:
  - Stock market movements & major indices
  - Company earnings & announcements
  - Merger & acquisition news
  - Regulatory changes affecting markets
  - Economic data releases
  - Cryptocurrency/crypto market news
  - Tech company news affecting finance
  - Banking & financial sector updates

### 2. Curate Top 2 Stories
- Identify the 2 most impactful/trending stories
- **Deduplication**: Check `tracking/seen-news.json` for today's date
  - If a headline was posted before, only include if there's a NEW UPDATE
  - Add new headlines to the tracking file

### 3. Create News Summaries
For each story, write:
- **Headline**: Catchy, under 10 words
- **Source**: Publication name
- **Summary**: Exactly 60 seconds read time (~150 words)
  - Start with impact
  - Include key numbers/facts
  - End with implications
- **Sentiment**: Bullish/Bearish/Neutral
- **Impact Level**: High/Medium/Low
- **Link**: Direct source URL

### 4. Generate Instagram Prompts
For each news story, create a prompt for AI image generation:

**Format**:
```
Topic: [News headline]
Style: Modern financial design, clean minimalist aesthetic
Colors: Professional palette (navy, gold, white, green for gains)
Main Text: "[Punchy 1-line headline - max 50 chars]"
Supporting Text: "[1 impactful stat or fact]"
Element: Chart, arrow, money bag, or relevant financial icon
Aspect Ratio: 9:16 (vertical for Instagram Stories/Reels)
Tone: Informative yet engaging
```

### 5. Save Files
- **Location**: `news-archive/` folder
- **Filename**: Create/append to `YYYY-MM-DD.md`
- **Format**: See README.md for template
- Include all 4 time slots (8 AM, 1 PM, 5 PM, 8 PM)

- **IG Prompts**: `instagram-prompts/YYYY-MM-DD.md`
- Include 2 prompts per time slot (if available)

### 6. Update Deduplication Tracking
- Add each posted headline to `tracking/seen-news.json`
- Include: headline, hash, posted_at timestamp, source
- Format by date for easy lookup

### 7. Commit to Git
```bash
git add .
git commit -m "Daily financial news briefing - YYYY-MM-DD [TIME SLOT]"
git push origin main
```

## ⚡ Requirements

✅ **Accuracy**: Use authoritative financial news sources  
✅ **Timeliness**: Fetch news from the past 3 hours only  
✅ **Deduplication**: Never post the same headline twice (unless updated)  
✅ **Quality**: 60-second summaries must be readable and informative  
✅ **Format**: Follow template exactly  
✅ **Completeness**: All fields required (no placeholder text)  
✅ **Real Time**: Use web search for current news  

## 🚫 Avoid
- Outdated news (more than 3 hours old)
- Duplicate headlines without updates
- Sensationalism (facts only)
- Incomplete summaries
- Broken links
- Opinion pieces (facts, not analysis)

## ✅ Success Criteria
1. Files created/updated with timestamp
2. Deduplication logic working
3. Git push successful
4. All required fields populated
5. No placeholder text
6. Valid markdown formatting

---

**Note**: This prompt runs automatically every 3 hours. Make it robust and fail gracefully if news is limited.
