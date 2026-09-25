# ⚙️ End-To-End Forensic Educational Content Evaluation & Extraction Workflow

## 📖 Overview
This repository contains the Standard Operating Procedures (SOPs) and system prompts for a 7-node, deterministic Agentic Workflow. The system is designed to ingest raw educational transcripts and mathematically evaluate, extract, verify, assemble, and format 100% of the high-fidelity educational payload (strategies, frameworks, context, and stories). 

Built to combat the natural LLM tendencies of summarization, truncation, and hallucination, this workflow forces fluid AI models into a rigid **Finite State Machine (FSM)**. It guarantees lossless data preservation, vector-ready context resolution, and modular Markdown formatting.

## 🏗️ System Architecture
* **Topological Pattern:** Hub-and-Spoke Orchestration.
* **State Management:** Decentralized & Stateless. Agents have no persistent memory; workflow state is strictly maintained via an immutable Centralized Database (`Workflow_Ledger.md`) hosted in Google Drive.
* **Tooling Integration:** Semantic API Triggering (Google Drive: Upload, Download, Search).
* **Execution Logic:** Deterministic, flat FSM integer paths with embedded Try/Catch Error Handling Protocols.

## 🤖 The Agent Roster (1 Orchestrator + 6 Subagents)

1. **MAIN AGENT (The Orchestrator):** Operates exclusively as a blind data courier and state router. It manages the Ledger, handles all Google Drive API initialization, and delegates execution parameters to Subagents based on the FSM state.
2. **SUBAGENT 1 (The Analyzer):** A read-only evaluation gate that scans the raw transcript to classify the exact conversational context (e.g., Marketing vs. Standard) to dictate downstream extraction paths.
3. **SUBAGENT 2 (The Extractor):** The core forensic engine. It executes a rigorous, taxonomy-driven extraction to isolate the initial educational payload without summarizing or compressing multi-step frameworks.
4. **SUBAGENT 3 (The Verifier):** The Microscopic Dragnet. It runs up to 3 iterative "diff-check" passes, comparing the Original Transcript against the Extraction to catch and recover any micro-variables, stories, or context dropped by Subagent 2.
5. **SUBAGENT 4 (The Fuser):** A robotic copy-paste engine. It parses explicit mathematical coordinates (`***[▼ INTEGRATION ANCHOR...]***`) to surgically inject Subagent 3's recovered data into Subagent 2's base extraction. 
6. **SUBAGENT 5 (The Logic Auditor):** The structural logician. It cross-references the fused document against the original source to fix chronological/hierarchical fractures and permanently purge any hallucinated text blocks.
7. **SUBAGENT 6 (The Unifier):** The grammatical polisher. It executes a strictly additive grammatical integration, reading only a 1-sentence radius around injection seams to add necessary conjunctions, ensuring a flawless, readable final master document.

## 🛡️ Key Engineering Constraints
* **The Anti-Compression Lock:** Agents are mathematically restricted from summarizing, estimating metrics, or truncating illustrative stories. 
* **Strict Noun Resolution:** To ensure data is vector-database-ready, agents are banned from using floating pronouns (he/she/it). All references are dynamically resolved to explicit proper nouns.
* **Stateless Ledger Reliance:** Agents are forbidden from relying on context windows to know where they are in the process. Every routing decision requires an explicit download and parse of the `Workflow_Ledger.md`.
* **The Null State Bypass:** Agents are explicitly programmed to handle empty data returns (e.g., finding zero new data on a verification pass) without hallucinating filler content to appease the prompt.

## 🚀 Inputs & Outputs
* **Input:** Raw unformatted text, `.txt`, or `.md` transcript files.
* **Output:** A highly structured, meticulously tagged, logically sequential Master `.md` file containing 100% of the educational payload, delivered via a direct Google Drive link.
