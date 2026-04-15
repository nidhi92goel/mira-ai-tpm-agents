# Mira: AI TPM Agent Suite

Mira is a set of AI-powered workflow agents built using **n8n** to automate high-impact **Technical Program Management (TPM)** tasks.

This project includes two core agents:
1. **Project Planning Agent** → Converts unstructured project inputs into a structured project plan  
2. **Kanban Summariser Agent** → Generates weekly status reports from Trello boards and sends stakeholder-ready emails  

Built as part of an **Applied Agentic AI for TPMs Capstone**, this project demonstrates how LLMs and workflow automation can reduce manual overhead and improve execution visibility.

---

## Problem Statement

In fast-moving teams, TPMs often face:
- Multiple concurrent projects with limited bandwidth  
- Manual effort in creating project plans  
- Lack of structured risk and dependency tracking  
- Time-consuming status reporting for stakeholders  
- Missed milestones due to poor visibility  

---

## Solution

Mira addresses these challenges through **agentic automation**:

### Project Planning Agent
- Monitors project input files from Google Drive  
- Extracts and consolidates content from multiple formats (PDF, DOCX, Excel, text)  
- Uses an LLM to generate a structured project plan  
- Populates a Google Docs template automatically  

### Kanban Summariser Agent
- Fetches task data from Trello boards  
- Groups tasks by status (Done, In Progress, Blocked, Backlog)  
- Generates a weekly status report using an LLM  
- Formats it into a clean HTML email  
- Sends it via Gmail automatically  

---

## Tech Stack

- n8n (workflow automation)
- OpenAI (LLMs)
- Google Drive API
- Google Docs API
- Trello API
- Gmail API
- JavaScript (n8n Code Nodes)

---

## Architecture Overview

### Project Planning Agent Flow
1. Trigger → Manual / Google Drive update  
2. Fetch project files from Drive  
3. Detect file types (PDF, DOCX, XLSX, TXT)  
4. Extract and normalize content  
5. Consolidate into a unified dataset  
6. LLM generates structured project plan (JSON format)  
7. Transform into document-ready format  
8. Populate Google Docs template  

---

### Kanban Summariser Agent Flow
1. Weekly scheduled trigger  
2. Fetch Trello board lists and cards  
3. Transform task data into structured format  
4. Group tasks by status  
5. LLM generates weekly status report  
6. Convert output into HTML email  
7. Send via Gmail  

---

## Business Impact

- Reduces manual effort in project planning  
- Standardizes project documentation  
- Improves visibility into risks and blockers  
- Automates stakeholder communication  
- Saves time for TPMs and engineering teams  

---

## Repository Structure

mira-ai-tpm-agents/
│
├── workflows/
│ ├── mira-project-planning-agent.json
│ └── mira-kanban-summariser-agent.json
│
├── docs/
│ ├── problem-statement.pdf
│ └── screenshots/
│
├── samples/
│ ├── sample-project-plan-output.md
│ └── sample-weekly-status-email.md
│
└── README.md


---

## Getting Started

### Prerequisites
- n8n (local or cloud)
- OpenAI API key
- Google Drive + Google Docs access
- Trello account
- Gmail account

---

### Setup Instructions

1. Import workflows into n8n:
   - workflows/mira-project-planning-agent.json  
   - workflows/mira-kanban-summariser-agent.json  

2. Configure credentials:
   - OpenAI  
   - Google Drive  
   - Google Docs  
   - Trello  
   - Gmail  

3. Replace placeholders:

- YOUR_GOOGLE_DRIVE_FOLDER_ID
- YOUR_GOOGLE_DOC_TEMPLATE_URL
- YOUR_TRELLO_BOARD_ID
- LIST_ID_DONE
- LIST_ID_BACKLOG
- LIST_ID_IN_PROGRESS
- LIST_ID_BLOCKED
- your-email@example.com


4. Run:
- Project Planning Agent → manual trigger  
- Kanban Agent → scheduled trigger  

---

## Configuration Notes

This repository contains **sanitized workflows**.

Before running:
- Add your own credentials in n8n  
- Replace all placeholder values  
- Connect APIs (Google, Trello, OpenAI, Gmail)  

No sensitive data is included in this repository.

---

## Sample Outputs

### Project Plan
- Executive summary  
- Scope, milestones, risks  
- Stakeholder and governance details  

### Weekly Status Email
- Progress snapshot  
- Completed tasks  
- Blockers and risks  
- Upcoming priorities  
- PM recommendations  

---

## Future Improvements

- RAG-based project context retrieval  
- Risk scoring and dependency mapping  
- Slack/Teams integration for reports  
- Dashboard for project health metrics  
- Multi-project scaling  

---

## Author

**Nidhi Goel**  
Project Manager | AI & Workflow Automation | XR & Tech  

---

## If you found this useful

Feel free to star the repo or fork it!

---

## Tags

n8n, ai-agents, llm, workflow-automation, project-management, openai, trello-api, google-docs, gmail-api, technical-program-manager
