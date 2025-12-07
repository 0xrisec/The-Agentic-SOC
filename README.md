# Agentic SOC 

## End-to-End Proof of Concept

A autonomous AI agents for Security Operations Center (SOC) alert triage and incident response, replacing repetitive Level 1 SOC tasks.

---

## Problem Statement

### Challenges in Modern SOC Operations

**Enterprise SOC teams face critical challenges:**

1. **Alert Fatigue**: High volume of SIEM alerts (1000+ per day)
2. **Repetitive Work**: 60-70% of alerts are routine false positives
3. **Slow Response Times**: Average MTTR (Mean Time To Respond) of 4-6 hours
4. **High Operational Cost**: $150K+ annual cost per L1 analyst
5. **Inconsistent Decision Making**: Human variability in triage quality
6. **Analyst Burnout**: High turnover due to monotonous work

### Typical L1 SOC Tasks

- Alert monitoring and ingestion
- Initial noise filtering
- Basic investigation and context gathering
- Severity assessment and prioritization
- Ticket creation and notification
- Documentation and handoff

---

## Solution Overview

### Objective

Validate whether autonomous AI agents can replace repetitive Level 1 SOC triage and initial investigation tasks, reducing MTTR and analyst workload while maintaining decision accuracy.

### Agent Replacement Architecture

| Traditional L1 Task | Agentic SOC Replacement |
|-------------------|------------------------|
| Alert Monitoring | **Alert Ingestion Agent** (FastAPI) |
| Noise Filtering | **Triage Agent** (LLM) |
| Basic Investigation | **Investigation Agent** (LLM) |
| Severity Decision | **Decision Agent** (LLM) |
| Ticket Creation | **Response Agent** (LLM) |

### Key Benefits

- **95% faster triage** - Seconds vs. minutes
- **Consistent accuracy** - No human variability
- **Cost reduction** - 70% reduction in L1 workload
- **Complete audit trail** - Every decision documented
- **24/7 operation** - No shift handoffs
- **Scalable** - Handle 10x volume without additional resources

---

## Architecture

### System Architecture

### Agent Workflow (LangGraph)

<img width="1292" height="359" alt="image" src="https://github.com/user-attachments/assets/fbb988c0-12d7-49ca-8d13-d342aa963e1f" />

### Agent Capabilities

#### 1. Triage Agent
- Rapid alert assessment (< 5 seconds)
- Noise filtering (false positive detection)
- Confidence scoring
- Key indicator extraction

#### 2. Investigation Agent
- Threat intelligence correlation
- Attack chain mapping (MITRE ATT&CK)
- Risk scoring (0-10 scale)
- Related alert identification

#### 3. Decision Agent
- Final verdict determination
- Priority assignment (P1-P5)
- Escalation decision
- Impact assessment

#### 4. Response Agent
- Incident ticket creation
- Stakeholder notifications
- Automated containment actions
- Response documentation

---

## Tech Stack

### Backend
- **FastAPI** - High-performance async REST API
- **LangGraph** - Agent workflow orchestration
- **LangChain** - LLM integration framework
- **OpenAI GPT-4** - Large language model
- **Pydantic** - Data validation and serialization
- **Python 3.11+** - Core language

### Frontend
- **HTML5/CSS3** - Modern responsive UI
- **Vanilla JavaScript** - No framework dependencies
- **Fetch API** - Async HTTP requests

### Data & Storage
- **JSON** - Alert data, threat intel, ground truth

---

## Installation

### Local Installation

```bash
brew install python@3.12
python3.12 -m venv env312
source env312/bin/activate
pip install -r requirements.txt
python run.py
```

### Docker Container

```bash
docker pull vikas9012/agentic-soc:latest
docker-compose up -d
docker-compose ps
```
---
