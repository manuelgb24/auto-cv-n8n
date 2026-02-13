# 🚀 Auto CV Tailoring Pipeline  
### Local-First AI Automation (n8n + Notion → PDF)

---

## 🎬 Live Demo

<video src="demo.mp4" controls width="900"></video>

---

## 🧠 What This Project Does

This system automates CV tailoring from a Job Description written in Notion and generates a clean, print-ready PDF.

Everything runs locally using Docker containers — including the LLM model.

---

## ⚙️ How It Works

Job Description (Notion)
↓
n8n Workflow (Docker)
↓
Local LLM (Ollama - Gemma)
↓
Structured JSON Validation
↓
Stable HTML Template Rendering
↓
PDF Generation
↓
Tailored CV Output


Each layer is intentionally separated to ensure control, reliability, and predictable output.

---

## 🏗 Architecture Overview

The entire system runs locally:

- 🐳 n8n orchestrates the workflow
- 🤖 A locally hosted LLM processes content
- 🧾 Output is validated before rendering
- 🖨 HTML is converted into a structured PDF
- 🔒 No data leaves the machine
 

---

## 🎯 Why This Matters

Tailoring CVs manually is repetitive and inconsistent. 

It demonstrates applied AI orchestration — not just prompt engineering.

---

## 📂 Repository

You can explore the full workflow and design notes in the main repository.
