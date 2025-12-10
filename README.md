# QuantumGuard-AI
# 🛡️ QuantumGuard AI

![Vertex AI](https://img.shields.io/badge/Built%20On-Google%20Vertex%20AI-4285F4?style=for-the-badge&logo=googlecloud&logoColor=white)
![Gemini 2.0](https://img.shields.io/badge/AI-Gemini%202.0%20Flash-8E44AD?style=for-the-badge&logo=googlebard&logoColor=white)
![Cloud Run](https://img.shields.io/badge/Compute-Cloud%20Run-22d3ee?style=for-the-badge&logo=googlecloud&logoColor=black)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

> **"Most tools tell you your code is vulnerable. QuantumGuard proves how to fix it without breaking production."**

## 🚨 The Problem: The Post-Quantum Crash
Shor's Algorithm is approaching. In the near future, quantum computers will break standard encryption primitives like **RSA-2048** and **ECDSA** in seconds.
* **The Risk:** Banking apps, Student projects, and SaaS platforms are currently vulnerable.
* **The Gap:** Developers do not know how to implement NIST-approved Post-Quantum Cryptography (PQC) like **Kyber** or **Dilithium**.
* **The Fear:** "If I migrate to PQC, will the massive key sizes crash my database or slow down my API?"

## 💡 The Solution
**QuantumGuard AI** is an agentic security auditor built on **Google Vertex AI**. It doesn't just flag "Red Code"; it autonomously refactors it and—crucially—**benchmarks the performance impact** in a real-time sandbox.

### ✨ Key Features
1.  **Agentic Audit (Scanner):** Uses **Gemini 2.0**'s massive context window to scan repositories and identify vulnerable cryptographic primitives (e.g., `rsa.newkeys(2048)`).
2.  **Auto-Migration (Architect):** Generates drop-in code patches using **NIST-standard libraries** (e.g., `liboqs`, `CRYSTALS-Kyber`).
3.  **Hallucination-Free RAG:** Grounded in official NIST PDF standards via **Vertex AI Vector Search**, ensuring the AI follows strict implementation guides.
4.  **The "Impact Sandbox" (Unique Feature):**
    * Spins up an isolated **Cloud Run Job**.
    * Executes the new "Quantum-Safe" code alongside the old code.
    * **Proves** the trade-off: *"Security: Critical → Safe. Latency: +4ms."*

---

## 🏗️ System Architecture (Pure Google Stack)

The project leverages a cloud-native, serverless architecture to ensure scalability from a single laptop to enterprise use.

| Component | Google Technology | Role |
| :--- | :--- | :--- |
| **Orchestrator** | **Vertex AI Agent Builder** | Manages the workflow between Scanner, Migrator, and Sandbox agents. |
| **Intelligence** | **Gemini 2.0 Flash** | fast reasoning for static analysis and code generation. |
| **Knowledge Base** | **Vertex AI Vector Search** | Stores RAG embeddings of NIST PQC documentation. |
| **Sandbox Engine** | **Cloud Run Jobs** | Runs the AI-generated benchmark scripts in a safe, isolated container. |
| **Frontend** | **Firebase Hosting** | React-based dashboard for developers to view audits. |
| **Storage** | **Google Cloud Storage** | Temporary storage for cloned repositories and scan artifacts. |

---

## 🚀 Getting Started

### Prerequisites
* Python 3.9+
* Google Cloud Platform Account (Active Project)
* `gcloud` CLI installed

