# AI Utilization System

Practical architecture for using AI tools across research, learning, and software development.

## What This Is

This repository is a system repository, not a product repository.

Its purpose is to help you build a personal AI working environment where multiple tools cooperate through shared context instead of being used independently.

In practical terms, this repository distributes:

- the operating philosophy
- the architecture
- the folder template
- the minimal reproducible environment

The system is designed for:

- studying university courses
- managing research materials
- writing long documents
- building software projects
- organizing knowledge over time

## Why This Exists

AI tools are powerful, but typical usage quickly becomes fragmented.

Common pattern:

`ChatGPT -> Perplexity -> NotebookLM -> Drive -> repeat`

Over time:

- context gets fragmented
- knowledge spreads across tools
- switching costs increase
- long-term work loses structure

The limitation is not model capability.

The real problem is the lack of architecture.

## Core Idea

Assign a clear role to each tool.

| Role | Tool |
| --- | --- |
| Search | Perplexity |
| Store | Zotero |
| Analyze | NotebookLM |
| Organize | Gemini |
| Design | Claude |
| Build | ChatGPT / Codex |
| Code State | GitHub |
| Memory | Google Drive |
| Control | `gws` CLI |

Each tool does one job well.

## Architecture

This system is built around one simple principle:

`Google Drive = shared memory`

`Gemini CLI = memory operator`

Flow:

`Inputs -> Gemini CLI -> Google Drive -> AI tools -> Outputs`

Code output is tracked separately in GitHub.

```text
                    INPUTS
   (PDFs, notes, docs, course files, drafts)
                         |
                         v
                +-------------------+
                |    Gemini CLI     |
                |   via gws CLI     |
                |                   |
                | - classify        |
                | - rename          |
                | - route           |
                | - update memory   |
                | - extract dates   |
                +---------+---------+
                          |
                          v
                +-------------------+
                |   Google Drive    |
                |   Memory Layer    |
                +---------+---------+
                          |
        +-----------------+-----------------+
        v                                   v
+----------------------+       +----------------------+
|   Knowledge Tools    |       |   Execution Tools    |
| NotebookLM           |       | Claude               |
| Perplexity           |       | ChatGPT / Codex      |
| Zotero (manual)      |       | Claude Code          |
+----------------------+       +----------------------+
        |                                   |
        v                                   v
   Analysis / Search                Design / Build / Code

                          |
                          v
                        OUTPUTS
                          |
              +-----------+-----------+
              v                       v
        Google Drive            GitHub (code)
```

## Minimal Setup

You do not need every tool from day one.

Minimal working setup:

- Google Drive
- Gemini CLI
- `gws` CLI

This already gives you:

- file organization
- persistent memory
- reusable context

Optional additions:

- Perplexity for search
- NotebookLM for analysis
- Claude for reasoning and design
- ChatGPT / Codex for implementation
- GitHub for code state
- Zotero for research archive

## Repository Structure

```text
ai-utilization-system/
|-- README.md
|-- docs/
|   |-- architecture.md
|   |-- setup.md
|   |-- workflows.md
|   `-- philosophy.md
|-- template/
|   `-- AI_OS/
|       |-- University/
|       |-- Projects/
|       `-- Librarian/
|-- examples/
|   |-- example_current_task.md
|   |-- example_brief.md
|   `-- example_handoff.md
`-- docker/
    |-- Dockerfile
    |-- docker-compose.yml
    `-- README.md
```

## Quick Start

1. Clone this repository.
2. Read [`docs/architecture.md`](/C:/Users/smkge/Develop/ai-utilization-system/docs/architecture.md).
3. Copy the [`template/AI_OS`](/C:/Users/smkge/Develop/ai-utilization-system/template/AI_OS) folder into your Google Drive workspace.
4. Set up the environment from [`docs/setup.md`](/C:/Users/smkge/Develop/ai-utilization-system/docs/setup.md).
5. If you want a reproducible CLI environment, start from [`docker/README.md`](/C:/Users/smkge/Develop/ai-utilization-system/docker/README.md).

## Design Principles

- AI assists thinking. It does not replace it.
- AI is a cognitive tool.
- Working systems matter more than perfect systems.
- Tools are replaceable.
- Context should persist.

## Librarian Policy

The following locations are intended to be AI-managed:

- `Librarian/`
- `*/librarian_memory/`

Recommended rule:

Do not manually edit them unless necessary.

These locations act as the system memory layer rather than ordinary notes.

Instead, treat Gemini as the memory operator and issue updates such as:

`Update current_task.md to reflect the new assignment and deadline.`

This keeps the memory layer consistent across tools and sessions.

Principle:

- user controls intent
- Gemini controls memory

## Documentation

- [`docs/architecture.md`](/C:/Users/smkge/Develop/ai-utilization-system/docs/architecture.md): system structure and memory model
- [`docs/setup.md`](/C:/Users/smkge/Develop/ai-utilization-system/docs/setup.md): environment and setup guidance
- [`docs/workflows.md`](/C:/Users/smkge/Develop/ai-utilization-system/docs/workflows.md): practical operating examples
- [`docs/philosophy.md`](/C:/Users/smkge/Develop/ai-utilization-system/docs/philosophy.md): design intent and constraints

## Repository

[https://github.com/smkgenesis/ai-utilization-system](https://github.com/smkgenesis/ai-utilization-system)

## Final Insight

Do not replicate this system exactly.

Implement the idea in a form that matches your own environment.
