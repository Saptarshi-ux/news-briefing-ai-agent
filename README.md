# The Daily News Briefing AI Agent  
**Automated Multi-Domain News Intelligence using n8n + Google Gemini**
##### The full description of this model is on my YouTube channel, the video reference is: 
###### https://www.youtube.com/watch?v=LUNaH5AH1pc
---

## Project Overview

**The Daily News Briefing AI Agent** is an end-to-end workflow automation built using **n8n** and **Google Gemini AI** that eliminates information overload by transforming **100+ raw global news headlines** into a **single, concise, 15-bullet daily email briefing**.

Instead of manually browsing multiple news sources, this AI agent:
- Fetches news from multiple authoritative RSS feeds
- Filters noise and duplicates
- Categorizes stories across key domains
- Summarizes them into short, neutral, high-impact bullet points
- Delivers the final brief automatically every morning via email

This project demonstrates **real-world AI orchestration, data aggregation, and automation design** using a low-code platform.

---

##  Objective

> To reduce information overload by automatically delivering a balanced, AI-curated daily news briefing across sports, technology, finance, government policy, and geopolitics.

---


---

## Workflow Breakdown

<img width="1669" height="674" alt="news_update_ai_agent_2" src="https://github.com/user-attachments/assets/5fc8a3e1-f8f5-407f-8c35-dcb3d5a79b47" />



### Precision Scheduling (Trigger Layer)
- **Node:** Schedule Trigger  
- **Configuration:** Daily at **7:00 AM**
- **Purpose:** Ensures the AI agent runs automatically at a fixed time every morning without manual intervention.

---

###  Multichannel Data Collection (Ingestion Layer)

Five independent **RSS Read nodes** are used to collect real-time headlines from high-authority sources:

| Category | Description |
|--------|------------|
|  Sports | Cricket, football, tennis, and global sports updates |
|  Tech / AI | Artificial intelligence, startups, and tech innovation |
|  Markets & Business | Stock market movements, corporate news, economy |
|  Government Policies | Indian policy updates, regulations, official announcements |
|  Geopolitics | Global political events and international affairs |

Each RSS node runs in parallel, enabling fast and scalable data ingestion.

---

###  Data Processing: Noise Reduction Funnel

This is the **core technical optimization** of the workflow.

####  Merge Node (Append Mode)
- Acts as a **central hub**
- Combines outputs from all RSS sources into **one unified stream**
- Ensures all news items are aligned for downstream processing

####  Aggregate Node (Zipping Function)
- RSS feeds often return **hundreds of individual items**
- Without aggregation, the AI would be triggered **once per headline**
- The Aggregate node:
  - Zips all items into **one single payload**
  - Prevents unnecessary API calls
  - Enables batch processing by the AI agent

This design significantly improves **performance, cost efficiency, and scalability**.

---

### Intelligence Layer: Gemini AI as an “Editor-in-Chief”

- **Model:** Google Gemini (via API)
- **Role:** Professional news editor

The AI agent performs:
- De-duplication of overlapping headlines
- Importance ranking across domains
- Category balancing (sports, finance, policy, geopolitics, etc.)
- Neutral, factual summarization
- Structured formatting with headers and bullet points

**Final Output:**
- Exactly **15 high-impact news bullets**
- Clean, readable, email-ready format
- No sensationalism or opinion bias

---

### Automated Delivery (Distribution Layer)

- **Node:** Gmail
- **Action:** Send email
- **Recipient:** Personal inbox
- **Result:**  
  A mobile-friendly, professionally formatted daily news briefing delivered automatically every morning.

---

## Key Features

- 1. Multi-source RSS ingestion  
- 2. AI-based filtering and summarization  
- 3. Category-aware content balancing  
- 4. Noise and duplication removal  
- 5. Fully automated scheduling  
- 6. Zero manual intervention  
- 7. Scalable and extensible design  

---

## Tech Stack

| Technology | Purpose |
|----------|--------|
| n8n | Workflow orchestration and automation |
| Google Gemini API | AI summarization and reasoning |
| RSS read Feeds | Real-time news ingestion |
| Gmail API | Automated email delivery |
| Low-Code Architecture | Rapid development & scalability |

---

##  Why This Project Matters

This workflow simulates how **real production AI agents** operate:
- Aggregating unstructured data
- Applying intelligent reasoning
- Delivering structured insights
- Running reliably on a schedule

It demonstrates practical skills in:
- AI agent design
- Prompt engineering
- Data funneling
- Automation architecture
- API orchestration

---

##  Future Enhancements

- User-selectable categories (via Telegram or form)
- Region-specific news filters (India-only / Global)
- Weekend vs weekday summaries
- Google Docs or Notion export
- Multi-user email subscriptions
- Historical trend analysis

---

## Author

**Saptarshi Bandyopadhyay**  
Analytics & Automation Enthusiast  


---

##  License

This project is intended for **educational and portfolio purposes**.


