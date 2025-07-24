# 📬 Gmail Smart Auto-Responder & Classifier (n8n + LLM)

This project is a **Gmail automation workflow built in n8n** that:
- Automatically **detects new Gmail messages** every minute.
- Extracts the **sender's name** using LLM-powered information extraction.
- Uses AI to **classify the email** into one of four categories.
- Adds appropriate **labels** in Gmail based on classification.
- Sends an **auto-reply email** with a personalized greeting.

> Built by [Darsh Tayal](https://www.linkedin.com/in/darsh-tayal-48442b25a/), Founder & CEO-in-the-making at 16.

---

## ⚙️ What It Does

### 1. Trigger on New Emails
- Gmail Trigger polls every minute.
- Ignores spam/trash by default.

### 2. Extract Sender’s Name
- Uses LangChain’s Information Extractor.
- If sender's name is found → personalizes the email.
- If not → uses a fallback greeting ("Hey").

### 3. Personalized Response Crafting
- Constructs a greeting like `Dear John` or `Hey`.

### 4. Classify Email Content
- Classifies incoming emails into one of 4 categories using LLM:
  - `n8n Messages`
  - `LangGraph Messages`
  - `Personal Messages`
  - `Any Messages`

### 5. Label the Email Accordingly
- Each category maps to a specific Gmail label (custom IDs).

### 6. Send Auto-Response
- Sends a contextual reply based on the classification.
- Replies differ based on whether the email is personal, about n8n, LangGraph, or generic.

---

## 🧠 Tech Stack

| Tool         | Purpose                                   |
|--------------|-------------------------------------------|
| `n8n`        | Workflow automation                       |
| `LangChain`  | AI-powered data extraction and classification |
| `Gmail API`  | Trigger, label, and send replies          |
| `Groq` + `Gemma 2 9B It` | Fast inference for LLM tasks  |
| `LLM Nodes`  | Extract sender name, classify message intent |

---

## 🧪 Sample Use Case

You're a solo founder or freelancer who:
- Gets inquiries across topics (e.g., AI projects, MUN invites, personal check-ins).
- Wants to organize them fast and send back instant, polite, human-like replies.

This setup automates that *completely*.

---

## 🏷️ Label Mapping

| Category           | Gmail Label ID                  |
|--------------------|----------------------------------|
| `n8n Messages`     | Label_3054083856440685021       |
| `LangGraph Messages` | Label_3359117729413329405    |
| `Personal Messages`| Label_7359500805631620889       |
| `Any Messages`     | Label_7359500805631620889       |

> You can customize label IDs inside Gmail and update them in the workflow.

---

## 📨 Sample Auto-Reply (Personal Message)

