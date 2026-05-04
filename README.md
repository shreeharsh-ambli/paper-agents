# paper-agents
A coordinated multi-agent system built on GitHub Copilot Chat that automates the end to end production of technical papers and documentation. Four specialised agents collaborate in a structured pipeline to deliver accurate, well-written, and publication ready content.

---

## Agents

| Agent | File | Role |
|---|---|---|
| **Publisher** | `.github/agents/publisher.agent.md` | Main entry point. Orchestrates the full pipeline. |
| **SME** | `.github/agents/sme.agent.md` | Validates technical accuracy and fills knowledge gaps. |
| **Writer** | `.github/agents/writer.agent.md` | Drafts structured, readable documentation from raw input. |
| **Editor** | `.github/agents/editor.agent.md` | Reviews for style, grammar, consistency, and publishing standards. |

---

## How It Works

The **Publisher** is the only agent you interact with directly. It drives the following pipeline automatically:

```
User Request
     │
     ▼
[Phase 1] Intake & Scoping       ← Publisher clarifies scope and audience
     │
     ▼
[Phase 2] SME Consultation       ← SME validates facts and provides technical content
     │
     ▼
[Phase 3] Drafting               ← Writer structures the content into a full draft
     │
     ▼
[Phase 4] Editorial Review       ← Editor checks style, grammar, and consistency
     │
     ▼
[Phase 5] Revision Loop          ← Writer revises; SME re-validates if needed
     │
     ▼
[Phase 6] Final Delivery         ← Publisher presents the completed document
```

---

## Getting Started

### Prerequisites

- Visual Studio Code with the **GitHub Copilot Chat** extension installed.
- Access to agent mode (`@agent` or agent file invocation) in Copilot Chat.

### Steps

1. Clone or open this repository in VS Code.
2. Open the **GitHub Copilot Chat** panel.
3. Switch to **Agent mode** and select the `publisher` agent.
4. Provide your request (see examples below).
5. Follow any clarifying prompts from the Publisher.
6. Receive the completed, publication-ready document.

---

## Example

**Input to the Publisher agent:**

```
I need a technical whitepaper on the use of retrieval-augmented generation (RAG)
for enterprise knowledge management. Target audience: engineering managers and
solution architects. Should cover: what RAG is, why it matters vs. fine-tuning,
a reference architecture, and known limitations. Approximately 2,000 words.
```

**What happens next:**

1. **Publisher** confirms the scope, audience, and format with you.
2. **SME** researches RAG architecture, validates technical claims, and flags any nuances (e.g., chunking strategies, vector store trade-offs).
3. **Writer** produces a structured draft: executive summary, concept overview, reference architecture, comparison table, limitations, and conclusion.
4. **Editor** reviews the draft for clarity, consistent terminology, and style compliance.
5. **Writer** incorporates editorial feedback; SME re-checks any new technical additions.
6. **Publisher** delivers the final whitepaper along with a session summary of decisions and open questions.

**Output:** A complete, reviewed, publication-ready 2,000-word whitepaper — ready to share or publish.

---

## Tips

- **Be specific in your brief.** The more context you give the Publisher (audience, format, length, style guide), the less back-and-forth is needed.
- **Provide raw material when you have it.** Paste in engineering notes, code snippets, or meeting transcripts — the Writer is designed to work from unstructured input.
- **Trust the SME phase.** Even for familiar topics, the SME validation step catches inaccuracies before they reach the final draft.
- **Iterate freely.** If the draft isn't right, tell the Publisher what to change. It will re-engage the appropriate agent rather than starting from scratch.

---

## Output Types

- Technical whitepapers and research papers
- README files and project documentation
- How-to guides and step-by-step tutorials
- API and SDK reference documentation
- Architecture and concept overviews
- Changelogs and release notes

---

## Repository Structure

```
.
├── .github/
│   └── agents/
│       ├── publisher.agent.md   # Main entry point — start here
│       ├── sme.agent.md
│       ├── writer.agent.md
│       └── editor.agent.md
├── README.md                    # This file
```
