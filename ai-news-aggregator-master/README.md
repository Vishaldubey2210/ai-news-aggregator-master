

# 🚀 AI News Aggregator (Powered by Groq)

## 📌 Overview

AI News Aggregator is a production-style Python application that automatically collects, processes, and summarizes news using high-speed AI inference powered by **Groq API**.

This project demonstrates how to build a **real-world AI data pipeline**, combining scraping, processing, and LLM-based summarization into a fully automated system.

---

## 🎯 What This Project Does

* 📰 Aggregates news from RSS feeds and external sources
* 🧹 Cleans and extracts meaningful article content
* ⚡ Uses Groq LLMs for ultra-fast summarization
* 📊 Filters top news based on recency & relevance
* ⏱ Supports time-based queries (e.g., last 24 hours)
* 🔄 Runs as a fully automated pipeline

---

## 🧠 Core Features

### 📰 News Collection

* Fetches data from RSS feeds using `feedparser`
* Easily extendable to APIs and web scraping

### 🧹 Data Processing

* Uses `BeautifulSoup` to clean HTML
* Removes ads, scripts, and noise
* Converts content into structured format

### ⚡ AI Summarization (Groq Powered)

* Uses Groq’s ultra-fast inference API
* Performs:

  * News summarization
  * Readability enhancement
  * Structured output generation

### 📊 Smart Filtering

* Filters top N articles
* Based on:

  * Recency
  * Content importance

### ⚙️ Configurable Pipeline

* Adjustable parameters:

  * Time range (hours)
  * Number of articles

---

## 🛠 Tech Stack

### 🔹 Backend

* Python 3.12

### 🔹 Libraries Used

* `feedparser` → RSS parsing
* `requests` → API calls
* `beautifulsoup4` → HTML parsing
* `markdownify` → Content formatting
* `groq` → AI inference
* `sqlalchemy` → ORM
* `psycopg2` → PostgreSQL
* `python-dotenv` → Env management

---

## 📁 Project Structure

```
.
├── main.py                 # Entry point
├── app/
│   ├── daily_runner.py    # Pipeline controller
│   ├── scraper.py         # News fetching
│   ├── processor.py       # Cleaning logic
│   ├── summarizer.py      # Groq AI integration
│   ├── database.py        # DB handling
│
├── .env
├── pyproject.toml
├── README.md
```

---

## ⚙️ Installation & Setup

### 1️⃣ Clone Repo

```bash
git clone <your-repo-url>
cd <project-folder>
```

---

### 2️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

OR (recommended):

```bash
pip install uv
uv sync
```

---

### 3️⃣ Setup Environment Variables

Create `.env` file:

```env
GROQ_API_KEY=your_groq_api_key

APP_NAME=ai-news-aggregator
ENV=development

DATABASE_URL=postgresql://user:password@localhost:5432/ai_news

DEFAULT_HOURS=24
TOP_NEWS_LIMIT=10
```

---

## ▶️ Running the Project

### 🔹 Default Run

```bash
python main.py
```

### 🔹 Custom Run

```bash
python main.py 24 10
```

👉 24 → last 24 hours
👉 10 → top 10 articles

---

## 🔄 Pipeline Workflow

1. Fetch RSS feeds
2. Extract article content
3. Clean & preprocess text
4. Send content to Groq API
5. Generate summaries
6. Filter top articles
7. Return structured JSON

---

## ⚡ Groq AI Integration

This project uses **Groq’s LLM API** for high-speed inference.

### 🔹 Example Code

```python
from groq import Groq

client = Groq(api_key="your_groq_api_key")

response = client.chat.completions.create(
    model="llama3-8b-8192",  # or mixtral / other Groq-supported models
    messages=[
        {"role": "user", "content": "Summarize this news article"}
    ]
)

print(response.choices[0].message.content)
```

---

## 📊 Example Output

```json
{
  "success": true,
  "articles": [
    {
      "title": "AI is transforming industries",
      "summary": "AI is rapidly changing business operations by automating workflows..."
    }
  ]
}
```

---

## 🚀 Future Improvements

* 🌐 React Dashboard (Frontend)
* 📩 Email newsletter automation
* 🔔 Real-time alerts system
* 🌍 Multi-language summaries
* 📊 Trend analysis & insights
* ☁️ Cloud deployment (AWS / Render)

---


