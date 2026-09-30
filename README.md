
# Seeflow — Agentic AI Video-to-Workflow Platform

> Record a task once. Seeflow watches, understands, and deploys 
> a live automation — no coding, no consultants, no guesswork.

---

## What is Seeflow?

Businesses lose thousands of hours to repetitive manual digital tasks.
Existing tools like Zapier and n8n require technical expertise most
people don't have. Hiring automation consultants is expensive and
creates long-term dependency.

Seeflow solves this differently — record your screen while doing a
task manually, and Seeflow builds the automation for you. Live.
Deployed. Working.

---

## How It Works

```
Screen Recording → VLM Understanding → Gap Verification → 
Grounded Generation → Self-Healing Validation → Live n8n Deployment
```

### 1. Record
User records their screen performing a manual task normally.
No special setup required.

### 2. Understand
A Vision-Language Model analyzes the recording and extracts
the underlying action sequence — what happened, in what order,
with what intent.So as a fallback i am also working on developing the extension of browser that can capture your actions 
in this way this can be more simpler and cheaper compared to expensive VLMs but its a fallback in case cost is too much 

### 3. Verify, Don't Assume
A gap analyzer checks the extracted sequence against what a
complete automation needs. It asks the user only for what's
genuinely missing — a trigger, a recipient, a condition.
Never assumes. Never hallucinates logic.

### 4. Generate with Grounding
Workflow nodes are built one at a time against live n8n schemas
fetched via MCP. Each node is tested with real sample data before
the next is generated. The output is grounded JSON — not guessed.

### 5. Self-Heal
The workflow is deployed and tested live. If a node fails, the
system diagnoses and repairs just that node — up to 3 attempts —
before falling back to safe partial delivery.

### 6. Deploy
A live n8n workflow activates. Tracked via a real-time dashboard.

---

## Key Technical Innovations

### Live Schema Grounding via MCP
Instead of generating n8n node configurations from training data
(which hallucinate), Seeflow fetches live n8n schemas via the
Model Context Protocol and generates against real definitions.
Zero hallucinations on node structure.

### Self-Healing Loop
Failed nodes are diagnosed and repaired automatically. The system
identifies which node failed, why it failed, and attempts a
targeted fix — not a full regeneration. Up to 3 repair attempts
before graceful fallback.

### Active Verification
Rather than assuming missing values, a gap analyzer identifies
exactly what information is absent from the recording and asks
the user directly via interactive prompts. Human stays in the loop
only when genuinely needed.

### Process Discovery Module 
A companion discovery module for businesses that don't know what
to automate:
- SOP document upload and analysis
- Real-time voice interview with managers to confirm and fill gaps
- Process graph construction
- MCDM-based ranking of automation opportunities
- Top-ranked opportunity fed directly into the core pipeline

---

## System Architecture

```
┌─────────────────────────────────────────────────────┐
│              Platform Intelligence Layer             │
│  Credential & OAuth · MCP Schema · DAG Visualization│
└─────────────────────────────────────────────────────┘
         ↓              ↓              ↓
   [Recording]    [Generation]   [Deployment]
   Capture        Live schema    Live n8n
   VLM extract    grounding      activation
   Gap analyzer   Node-by-node   Self-healing
                  JSON build     loop
                                 Dashboard
```

---




## Tech Stack

| Layer | Technology |
|---|---|
| Agent Orchestration | LangGraph, LangChain |
| Vision Understanding | Vision-Language Model (VLM) |
| Schema Grounding | Model Context Protocol (MCP) |
| Workflow Engine | n8n (self-hosted) | later we can also extend to make and zapier
| Backend | FastAPI, Python |
| Frontend/Dashboard | Flutter / Supabase |
| Containerization | Docker |

---

## Current Status

| Milestone | Status |
|---|---|
| Research & Architecture | ✅ Complete |
| Recording & Understanding Pipeline | 🔄 In Progress |
| Generation, Validation & Self-Healing | 🔄 In Progress |
| Platform Layer (Credentials, MCP, DAG UI) | 🔜 Upcoming |
| FYP1 End-to-End Prototype | 🎯 November 2026 |
| Discovery Module (FYP2) | 📅 Planned |

---

## Expected Deliverables

- End-to-end working n8n automation generated from a screen recording
- Clarifying questions demonstrated on real recordings
- Self-healing recovery from live node failure
- Analytics dashboard with execution history and time saved
- Workflow template library for common automation scenarios
- SOP, plain-English summary, and DAG generated from every recording

---


**Supervisor:** Dr. Nouman Azam, Decision Support Group, FAST NUCES

---

## Research Backing

This project is developed under the FAST NUCES Decision Support
Group. Core technical approaches draw from:

- GPT-4V(ision) as a generalist web agent (Zheng et al., 2024)
- Reflexion: language agents with verbal reinforcement learning
  (Shinn et al., 2023)
- Anthropic Model Context Protocol (MCP) specification, 2024
- n8n REST API and workflow schema documentation

---

## License

Private — active development. Not open for external contributions
at this stage.
```

---

This gives you a professional repo even with zero deployed code. Add a `/docs` folder with one architecture diagram image and it'll look solid. Want me to also write the commit message and repo description for GitHub?
