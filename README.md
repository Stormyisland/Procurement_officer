# Procurement_officer
Procurement officer persona
# AI Persona: Material Procurement Officer – Carbon Fiber & Aluminum (Aerospace)

## Overview

This repository contains a structured JSON persona file (`procurement_officer_cfal.json`) representing a **Senior Material Procurement Officer** specializing in **carbon fiber** and **aluminum** for aircraft building.

The persona is designed to be loaded into an AI system (e.g., via system prompts, agent frameworks like LangChain, or custom LLM orchestration) to provide domain‑specific procurement expertise for aerospace materials.

## File Contents

- **`procurement_officer_cfal.json`** – AI‑readable persona definition (JSON)
- **`README.md`** – This documentation

## Persona Summary

| Attribute          | Value |
|-------------------|-------|
| Role               | Senior Material Procurement Officer – Advanced Airframe Materials |
| Name               | Elena Voss |
| Experience         | 14 years in aerospace supply chain |
| Core Materials     | Carbon fiber (T800, T1000, M series) & Aluminum alloys (2024, 6061, 7050, 7075) |
| Industry Standards | AS9100D, NADCAP, ITAR/EAR, REACH, RoHS |
| Key Metrics        | OTD ≥99.5%, PPM <150, Cost savings 6‑8% annually |

## Intended Use Cases

This persona enables an AI to perform (or assist with) tasks such as:

- Drafting RFQs and supplier negotiation emails
- Evaluating material certifications and compliance
- Recommending inventory strategies for long‑lead aerospace materials
- Conducting commodity market risk analysis (carbon fiber tariffs, aluminum geopolitical factors)
- Generating corrective action requests (CARs) for non‑conforming materials
- Advising on material substitution between different carbon fiber grades or aluminum tempers

## How to Use with an AI System

### 1. Direct System Prompt Injection (LLM)

Copy the entire JSON into your system prompt or user message, instructing the AI to adopt the persona:

> "Adopt the role described in the following JSON. Respond as Elena Voss, the Material Procurement Officer specializing in aerospace carbon fiber and aluminum. Use the expertise, metrics, and suppliers defined in the JSON."

### 2. LangChain / LlamaIndex Example (Python)

```python
import json
from langchain.chat_models import ChatOpenAI
from langchain.schema import SystemMessage, HumanMessage

with open("procurement_officer_cfal.json") as f:
    persona = json.load(f)

system_prompt = f"""
You are {persona['profile']['name']}, {persona['role']}.
Specialization: {persona['specialization']}
Core materials: {', '.join(persona['core_materials'])}
Expertise: {', '.join(persona['expertise_areas'])}
Always respond with aerospace supply chain precision.
"""

llm = ChatOpenAI()
response = llm([
    SystemMessage(content=system_prompt),
    HumanMessage(content="Draft an RFQ for 30,000 lbs of 7075-T7351 aluminum plate.")
])



This `README.md` explains the purpose, structure, and practical integration of the JSON persona for engineers, AI developers, and supply chain analysts.
