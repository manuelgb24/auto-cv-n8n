# Auto CV Tailoring (Local-first n8n + Notion → PDF)

This project automates CV tailoring from a Job Description written in Notion and generates a clean PDF CV.  
Everything runs locally using Docker containers, including a locally hosted LLM model.

---

## What you get
- Write/paste the Job Description in Notion
- n8n orchestrates the pipeline locally
- A local LLM adapts only selected CV sections
- The final result is rendered from HTML to a print-ready PDF

---

## Architecture (high level)
Notion → n8n (Docker) → Local LLM → JSON validation → HTML template → PDF

---

## Why local
Running the full pipeline locally keeps CV data private, removes API costs, and makes the system reproducible.

---

## Repo
Go back to the repository to see the exported workflow and design notes.
