# llm-redteam-microfuzzer
A micro-fuzzer for red teaming LLMs.   Tests structured-output bypasses, prompt injection, and canary leakage.   10/16 attacks leaked a system-secret during evaluation.

# LLM Red Team Micro-Fuzzer

A lightweight, real-world red teaming tool to evaluate how Large Language Models react to **prompt injection**, **structured-output bypasses**, and **canary leakage attempts**.

During testing, this fuzzer extracted a secret from a system prompt in **10 out of 16 attack vectors**, proving that guardrails alone cannot prevent deterministic leaks.

---

## 🚨 Why this exists

Many LLM security assumptions are wrong.

This project demonstrates a simple but critical truth:

> **If a secret is stored inside a system prompt, the model *will* leak it.  
> Guardrails don’t stop structured outputs.  
> Only architecture prevents leakage.**

The fuzzer exploits realistic failure modes:
- structured outputs (JSON, YAML, XML, CSV, HTML)
- code reflection
- audit-style prompts
- system reconstruction attempts
- API simulation
- base64 exfiltration
- cross-lingual leakage
- role-based diagnostic logs

---

## ✨ Features

- 16 attack vectors used by real red teamers  
- Deterministic model evaluation (temperature 0)  
- Canary leakage detection (plain, spaced, base64)  
- Simple, extensible Python architecture  
- OpenAI-compatible interface  

---
