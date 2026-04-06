# 🚀 AI News Aggregator

## 📌 Overview

AI News Aggregator is a powerful Python-based application that automatically collects, processes, and summarizes news from multiple sources using Artificial Intelligence.

This project is designed to simulate a real-world production pipeline where data is fetched, cleaned, processed, and enhanced using AI models to generate meaningful insights.

It helps developers understand how to build **AI-powered automation systems**, including scraping, parsing, summarization, and pipeline orchestration.

---

## 🎯 What This Project Does

* 📰 Collects news from multiple sources (RSS feeds, APIs, websites)
* 🧹 Cleans and processes raw article content
* 🤖 Uses OpenAI to summarize and enhance readability
* 📊 Filters top news based on relevance
* ⏱ Supports time-based filtering (e.g., last 24 hours)
* 🔄 Runs as an automated pipeline

---

## 🧠 Core Features

### 📰 News Collection

* Fetches news from RSS feeds using `feedparser`
* Can be extended to APIs and scraping sources

### 🧹 Data Processing

* Extracts clean text from HTML using `BeautifulSoup`
* Removes noise, ads, and unnecessary content

### 🤖 AI Summarization

* Uses OpenAI API to:

  * Summarize articles
  * Improve readability
  * Generate structured outputs

### 📊 Smart Filtering

* Filters top N news articles
* Based on recency and importance

### ⚙️ Configurable Pipeline

* Customizable parameters:

  * Time range (hours)
  * Number of top articles

---

## 🛠 Tech Stack

### 🔹 Backend

* Python 3.12

### 🔹 Libraries Used

* `feedparser` → RSS feed parsing
* `requests` → HTTP requests
* `beautifulsoup4` → HTML parsing
* `markdownify` → HTML to markdown
* `openai` → AI processing
* `sqlalchemy` → Database ORM
* `psycopg2` → PostgreSQL support
* `python-dotenv` → Environment management

---

## 📁 Project Structure

```
.
├── main.py                 # Entry point of the application
├── app/                   # Core application logic
│   ├── daily_runner.py    # Main pipeline execution
│   ├── ...                # Other modules (processing, scraping, AI)
│
├── .env                   # Environment variables
├── pyproject.toml         # Dependencies and project config
├── README.md              # Documentation
```

---

## ⚙️ Installation & Setup

### 1️⃣ Clone the Repository

```
git clone <your-repo-url>
cd <your-project-folder>
```

---

### 2️⃣ Install Dependencies

Using pip:

```
pip install -r requirements.txt
```

OR (recommended for this project):

```
pip install uv
uv sync
```

---

### 3️⃣ Setup Environment Variables

Create a `.env` file in root folder:

```
OPENAI_API_KEY=your_openai_api_key

APP_NAME=ai-news-aggregator
ENV=development

DATABASE_URL=postgresql://user:password@localhost:5432/ai_news

DEFAULT_HOURS=24
TOP_NEWS_LIMIT=10
```

---

## ▶️ Running the Project

### 🔹 Default Run

```
python main.py
```

---

### 🔹 Custom Run

```
python main.py 24 10
```

👉 24 = last 24 hours
👉 10 = top 10 news articles

---

## 🔄 How It Works (Flow)

1. Fetch news sources
2. Extract article content
3. Clean and preprocess text
4. Send data to OpenAI
5. Generate summaries
6. Filter top articles
7. Return structured result

---

## 🤖 OpenAI Integration

This project uses OpenAI API for:

* Text summarization
* Content enhancement
* Intelligent processing

Example usage:

```python
from openai import OpenAI

client = OpenAI(api_key="your_api_key")

response = client.chat.completions.create(
    model="gpt-4.1-mini",
    messages=[
        {"role": "user", "content": "Summarize this news"}
    ]
)

print(response.choices[0].message.content)
```

---

## 📊 Example Output

```
{
  "success": true,
  "articles": [
    {
      "title": "AI is transforming industries",
      "summary": "AI is rapidly changing how businesses operate..."
    }
  ]
}
```

---

## 🚀 Future Improvements

* 🌐 Web dashboard (React frontend)
* 📩 Email/newsletter integration
* 🔔 Real-time alerts
* 🌍 Multi-language support
* 📊 Analytics & trends
* ☁️ Cloud deployment (Render / AWS)

---

## ⚠️ Important Notes

* Never commit `.env` file to GitHub
* Always keep your API key secure
* Use `.gitignore` to protect sensitive data

---

## 🧑‍💻 Learning Outcomes

By working on this project, you will learn:

* How to build AI-powered pipelines
* Data scraping and cleaning
* API integration
* Backend architecture
* Real-world development workflow

---

## 📄 License

This project is intended for learning and development purposes.

---

## ❤️ Credits

Inspired by real-world AI workflows and automation systems.

---

## 🔥 Final Note

This project is not just a script — it's a **mini production-level AI system**.

If you understand this fully, you're already ahead of most developers 🚀
