# OMNA People — End-to-End AI HR Automation System

An automated, multi-workflow HR and Recruitment platform built with **n8n**, **Google Workspace (Sheets, Drive, Gmail)**, and **LLMs (Gemini & Groq)**.

## Live Demo
🔗 **[Open OMNA People Portal](https://adhmabbas.github.io/OMNA-People-HR-Automation/)**  
*(Note: Backend runs on a local Docker n8n instance exposed via ngrok; status badge indicates live availability).*

## System Architecture (6 Workflows)

1. **Recruitment 1 - Intake:** Public job application form with server-side validation, duplicate application detection, Google Drive CV archiving, and Google Sheets logging.
2. **Recruitment 2 - AI Screening:** Scheduled pipeline that extracts text from PDF/scanned CVs (with OCR fallback), evaluates candidates against job requirements using structured JSON outputs, assigns a 0–100 score, generates tailored interview questions, and sends automated acceptance/rejection emails.
3. **Recruitment 3 - Error Handler:** Centralized fault-tolerance workflow that catches runtime errors across all pipelines, logs incidents to Google Sheets, prevents alert fatigue via throttling, and sends instant admin email alerts.
4. **RAG + AI HR Assistant:** Conversational chatbot grounded in company HR policy documents using an In-Memory Vector Store and Gemini Embeddings.
5. **Policy Loader:** Automated knowledge-base synchronization workflow triggered on n8n startup and daily schedules to keep the vector store updated from Google Drive.
6. **Job Application Coach:** AI-powered career tool that analyzes a candidate's CV against a target job description and emails a detailed gap-analysis and improvement report.

## Tech Stack
* **Orchestration:** n8n (Self-hosted via Docker)
* **AI & RAG:** Google Gemini, Groq, In-Memory Vector Store, Structured Output Parsers
* **Integrations:** Google Drive API, Google Sheets API, Gmail OAuth2
* **Frontend:** Vanilla HTML/CSS/JS hosted on GitHub Pages