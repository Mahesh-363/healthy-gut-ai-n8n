# Healthy Gut AI — Medical SEO Article Generator (n8n + Google Gemini)

An automated system that generates **SEO-optimized, medically accurate long-form articles** using **n8n workflows**, **Google Gemini AI**, and reusable prompt templates.

This project showcases workflow automation, API integration, prompt engineering, and professional repo organization.

---

## 🚀 Project Overview

Healthy Gut AI is an automated article-generation pipeline that:

- Accepts a medical topic as input (e.g., IBS, IBD, Crohn’s disease)
- Injects it into structured SEO prompt templates
- Sends the data to Google Gemini via authenticated HTTP Request
- Generates a 2,000–3,000 word medical article
- Extracts clean text using Edit Fields + JS nodes
- Saves samples inside `/examples/`

---

## 📁 Repository Structure


healthy-gut-ai-n8n/
│
├── examples/
│   ├── ibs-article.md
│   ├── ibd-article.md
│   ├── crohns-disease-article.md
│   └── ulcerative-colitis-article.md
│
├── n8n-workflows/
│   └── Input_Article_Topic.json
│
├── .gitkeep
│
├── prompts/
│   ├── prompt1.md
│   └── prompt2.md
│
├── .env.example
│
├── .gitignore
│
└── README.md


## 🔧 Environment Setup

Use the **n8n Credential Manager** (recommended),  
or create a local `.env` file with:

GEMINI_API_KEY=
GROQ_API_KEY=
GITHUB_TOKEN=


**⚠️ Never commit real API keys to GitHub.**
Your .env.example is for documentation only.

## 🤖 Workflow Breakdown

## Step 1 — Input Node

User enters a topic:

topic = "Inflammatory Bowel Disease"

## Step 2 — Prompt Injection

Topic is inserted into Prompt 1 and Prompt 2.

These templates define structure, SEO rules, tone, and medical accuracy guidelines.

## Step 3 — Gemini API Call (HTTP Request)

POST request with:

Headers

Content-Type: application/json
x-goog-api-key: {{ $credentials.myGoogleApi.apiKey }}



**Body includes:**

- Model name
- System instructions
- Prompt template
- User topic

## Step 4 — Extract Raw Article Text

Text is retrieved from:

json.candidates[0].content.parts[0].text


## Step 5 — Final JavaScript Node Output

Expected output:

json
{
  "article": "final article text here..."
}


## Step 6 — Save Article Manually

Paste the final generated article into:

/examples/


Name files like:

-ibs-article.md

-ibd-article.md

-crohns-disease-article.md

-ulcerative-colitis-article.md

## 🧩 Prompt Engineering

**Prompt 1 — Structure Template**

Defines:

-Section flow

-Intro + metadata

-Medical rules

-SEO rules

-Tone

**Prompt 2 — Advanced SEO Template**

Adds:

-Keyword strategy

-Metadata

-Rich formatting

-Readability constraints

Together they guarantee medical accuracy + SEO optimization.

## 📌 Included Article Examples

Inside /examples/:

-IBS long-form article

-IBD long-form article

-Crohn’s Disease long-form article

-Ulcerative Colitis long-form article

Each includes:

-SEO Title

-Meta description

-Full 2000+ words

-Medical accuracy

-Markdown formatting
