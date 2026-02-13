# Auto CV Tailoring Pipeline (n8n + Notion → PDF)

## 🚀 Overview

Applying to jobs usually means editing your CV again and again for each new role.  
This project automates that process.

You paste a Job Description in Notion, and the system generates a tailored, clean PDF version of your CV — ready to send.

Everything runs locally using Docker containers, including a locally hosted LLM model.  
No external AI APIs are required.

---

## 🧠 Why I Built This

Tailoring a CV for every job application is:

- Repetitive  
- Time-consuming  
- Easy to break formatting  
- Inconsistent  

I wanted a system that:

- Standardizes the process  
- Reduces manual effort  
- Preserves formatting stability  
- Minimizes AI hallucinations  
- Runs fully locally for privacy and control  

This pipeline transforms a manual task into a structured, automated system.

---

## 🏗 Infrastructure (Local-First Design)

The entire system runs locally inside Docker containers:

- n8n (workflow orchestration)
- Local LLM model (downloaded and hosted on my machine)
- PDF rendering service
- Supporting services if required

No external LLM APIs are used.  
The model is downloaded and executed locally, ensuring:

- Full data privacy  
- No API costs  
- Full control over model behavior  
- Offline capability  

This makes the system reproducible, private, and infrastructure-aware.

---

## ⚙️ How It Works (High-Level)

Notion (Job Description)
↓  
n8n (Docker container)
↓  
Local LLM Model (running on host)
↓  
Structured JSON validation
↓  
HTML Template Rendering
↓  
PDF Generation
↓  
Final CV Output  

Each step is isolated and controlled to reduce risk and improve reliability.

---

## 🔐 Design Philosophy

This project is intentionally opinionated.

- The LLM is restricted to editing only selected CV sections.
- Output is forced into structured JSON before rendering.
- Everything runs locally inside containers.
- No credentials are stored in this repository.
- Workflow is exported for transparency and reproducibility.

The focus is system design, reliability, and infrastructure awareness — not just AI automation.

---

## 📌 What I Would Improve in Production

If deployed at scale, I would add:

- Multi-model fallback (local + cloud provider)
- Automatic retry mechanism for malformed JSON
- Centralized logging
- CV template versioning
- Monitoring and observability layer
- A/B testing between tailored variants

---

## 📂 Repository Structure

- `/n8n/workflow.json` → Exported n8n workflow
- `/docs` → Public project page (GitHub Pages)
- `README.md` → Project explanation and design notes

---

## 🎥 Demo

(Demo GIF will be added here)

---

## 📎 Final Note

This project demonstrates practical AI orchestration, local-first infrastructure design, and workflow automation.

It is not just about generating a PDF.

It is about building controlled, privacy-aware AI systems that solve repetitive real-world problems using containerized infrastructure.
