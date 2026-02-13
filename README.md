# Auto CV Tailoring Pipeline (n8n + Notion → PDF)

## Overview

Applying to jobs often means rewriting your CV over and over again. 
You adjust a few lines here, reword a paragraph there, tweak the summary, change the skills… and repeat the process for every new application.

I built this project to remove that friction.

The idea is simple: write the Job Description in Notion, trigger the workflow, and receive a tailored, clean PDF version of your CV. No manual formatting, no repetitive edits, no broken layouts.

Everything runs locally using Docker containers, including the language model. There are no external AI APIs involved. The model is downloaded and executed directly on my machine, which keeps the entire pipeline private, controllable, and cost-free.

---

## Why This Exists

Manually tailoring a CV is not hard — it’s just inefficient. It consumes time, introduces inconsistencies, and makes it easy to over-edit sections that should remain stable.

What I wanted was not just automation, but controlled automation.

This system standardizes the process. It limits what the AI is allowed to modify. It keeps the structure intact. It reduces hallucination risk by forcing structured outputs. And it ensures that formatting remains predictable and stable across every generated version.

In short: it turns a messy manual workflow into a repeatable system.

---

## Infrastructure and Local-First Design

One of the key design decisions was to run everything locally.

The orchestration is handled by n8n running inside a Docker container.  
The LLM is downloaded and hosted locally.  
PDF rendering is containerized as well.

This setup ensures:

- Full data privacy (CVs never leave the machine)
- Zero API costs
- Offline capability
- Full control over model behavior and system architecture

It also makes the system reproducible and infrastructure-aware, rather than just being a “prompt + API call” demo.

---

## How the System Works

At a high level, the process flows like this:

A Job Description is written in Notion.  
n8n reads it and orchestrates the workflow.  
The local LLM processes the relevant CV sections under strict constraints.  
The output is validated as structured JSON.  
That structured content is injected into a stable HTML template.  
Finally, the system generates a clean, print-ready PDF.

Each step is intentionally separated and controlled to minimize risk and maximize reliability.

---

## Design Philosophy

This project is intentionally opinionated.

The AI is not allowed to rewrite the entire CV. It only modifies specific sections.  
The output must conform to a structured format before rendering.  
Everything runs locally inside containers.  
Credentials are never stored in the repository.  

The goal is not flashy AI automation.  
The goal is to demonstrate system design thinking applied to real-world workflow automation.

---

## If This Were Production

If this were deployed at scale, I would extend it with:

Multi-model fallback logic.  
Retry mechanisms for malformed model outputs.  
Centralized logging and observability.  
Version-controlled CV templates.  
A/B testing across tailored variants.  

The foundation is here. The production hardening would be the next layer.

---

## Final Note

This project is part of my portfolio to demonstrate practical AI orchestration, local infrastructure design, and workflow automation.

It’s not about generating a PDF.

It’s about building controlled, privacy-aware systems that reduce repetitive cognitive work and turn manual processes into structured pipelines.
