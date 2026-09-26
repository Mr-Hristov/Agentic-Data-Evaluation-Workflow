# ⚙️ End-To-End Forensic Educational Content Evaluation & Extraction Agentic Workflow Optimized For Gemini Enterprise

## 📖 Overview
This repository contains the Standard Operating Procedures (SOPs) and system prompts for a 7-node, Agentic Workflow. Plus a standalone Forensic Quality Assurance (QA) Evaluator. The system is designed to ingest raw educational transcripts. Then it extracts, verifies, assembles, and formats the high-fidelity educational payload (strategies, frameworks, context, stories, etc.). 

It's designed to mitigate the natural LLM tendencies to summarize, truncate, paraphrase, and hallucinate. This workflow locks the agents into a rigid **Finite State Machine (FSM)** execution sequence. It guards against unauthorized data loss. It outputs vector-optimized data and structured Markdown formatting.

## 🏗️ System Architecture
* **Topological Pattern:** Hub-and-Spoke Orchestration.
* **State Management:** Decentralized & Stateless. Agents have no persistent memory; workflow state is strictly maintained via a Centralized Ledger (`Workflow_Ledger.md`) hosted in Google Drive.
* **Tooling Integration:** Semantic API Triggering (Google Drive: Upload, Download, Read, Search).
* **Execution Logic:** Deterministic, flat FSM integer paths with embedded Try/Catch Error Handling Protocols.

## 🤖 The Agent Roster (1 Orchestrator + 6 Subagents)

1. **MAIN AGENT (The Orchestrator):** Operates exclusively as a blind data courier and state router. It manages the Ledger, handles all Google Drive API initialization, and delegates execution parameters to Subagents based on the FSM state.
2. **SUBAGENT 1 (The Analyzer):** A read-only evaluation gate that scans the raw transcript to classify the exact conversational context (e.g., Marketing vs. Standard) to dictate downstream extraction paths.
3. **SUBAGENT 2 (The Extractor):** The core forensic engine. It executes a rigorous, taxonomy-driven extraction to isolate the initial educational payload.
4. **SUBAGENT 3 (The Verifier):** It acts as a Microscopic Dragnet. It runs up to 3 iterative "diff-check" passes, comparing the Original Transcript against the Extraction to catch and recover any micro-variables, stories, or context dropped by Subagent 2.
5. **SUBAGENT 4 (The Fuser):** A robotic copy-paste engine. It parses explicit mathematical coordinates (`***[▼ INTEGRATION ANCHOR...]***`) to surgically inject Subagent 3's recovered data into Subagent 2's base extraction. 
6. **SUBAGENT 5 (The Logic Auditor):** The structural logician. It cross-references the fused document against the source material to fix chronological/hierarchical fractures and purge any hallucinated text blocks.
7. **SUBAGENT 6 (The Unifier):** The grammatical polisher. It executes a strictly additive grammatical integration, reading only a 1-sentence radius around injection seams to add necessary conjunctions, ensuring a flawless, readable final master document.

## 🔬 The Forensic Evaluator (QA & System Refinement)
Included in this repository is the `EVAL_SOP.md`—a standalone Output Quality Assurance Auditor. While it can be manually operated or integrated as a final testing node, it serves as a ruthless verification engine for system testing, output debugging, and instruction refinement.
* **The Trigger Mechanism:** It ingests both the Raw `<TRANSCRIPT>` (Ground Truth) and the Final `<EXTRACTION>` (Agent Output), remaining dormant until triggered by a specified execution command.
* **The Delta Audit:** It mathematically cross-references the output against the strict *Six Pillars of Preservation* and *Excision List* to flag:
  * **False Negatives:** Unauthorized omissions of payload, context, constraints, or stories.
  * **False Positives:** Improper retention of conversational noise, banter, or logistics.
  * **Formatting Violations:** Unresolved floating pronouns, hallucinated markdown links, or rounded technical metrics.
* **Compound Grading & Dynamic Patching:** It calculates a strict 0-100 compound score across the three categories and generates a "System Refinement Protocol"—outputting copy-paste-ready, mathematically precise Prompt Engineering patches to continuously tighten upstream agent logic.

## 🛡️ Key Engineering Constraints
* **The Anti-Compression Lock:** Agents are restricted from summarizing, estimating metrics, or truncating illustrative stories. 
* **Strict Noun Resolution:** To ensure data is vector-database-ready, agents are banned from using floating pronouns (he/she/it). All references are dynamically resolved to explicit proper nouns.
* **Stateless Ledger Reliance:** Agents are forbidden from relying on context windows to determine where they are in the process. Every routing decision requires an explicit parsing of the `Workflow_Ledger.md`.
* **The Null State Bypass:** Agents are explicitly programmed to handle empty data returns (e.g., finding zero new data on a verification pass) without hallucinating filler content to appease the prompt.

## 🚀 Inputs & Outputs
* **Input:** Raw unformatted text, `.txt`, or `.md` transcript files.
* **Output:** A highly structured, meticulously tagged, logically sequential Master `.md` file containing the educational payload, delivered via a direct Google Drive link.
