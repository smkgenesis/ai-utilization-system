# Architecture

## Goal

Build a practical system where multiple AI tools work together through shared context instead of being used as isolated chat windows.

This architecture is intended for:

- university study
- research material management
- long-form writing
- software development
- long-term knowledge organization

## Core Principle

The system is centered on one idea:

`Google Drive = shared memory`

`Gemini CLI = librarian`

Gemini operates on top of Google Drive through `gws` and manages how new information enters the system.

This turns Drive into a shared memory layer and Gemini into the memory operator.

## Tool Roles

| Function | Tool |
| --- | --- |
| Search | Perplexity |
| Paper archive | Zotero |
| Document analysis | NotebookLM |
| Memory organization | Gemini |
| Design and reasoning | Claude |
| Implementation | ChatGPT / Codex |
| Code state | GitHub |
| Persistent memory | Google Drive |
| Control layer | `gws` CLI |

The point is not that these exact tools are mandatory.

The point is role separation.

## System Shape

This is not a linear pipeline. It is an input and output system centered on memory.

```text
INPUTS -> Gemini CLI -> Google Drive -> AI tools -> OUTPUTS
                                  \-> GitHub for code
```

Raw materials enter through Gemini, are organized into shared memory, then consumed by specialized tools.

Outputs are written back into:

- Google Drive for knowledge state
- GitHub for code state

## Input Layer

Typical inputs:

- PDFs
- lecture files
- notes
- drafts
- project documents
- downloaded course materials

Gemini handles:

- reading files
- renaming
- classification
- routing to folders
- memory updates
- deadline or schedule extraction

## Memory Layer

Google Drive is the continuity layer of the system.

It stores:

- documents
- course materials
- project files
- local and global AI context

Without this layer, every AI session tends to reset.

With this layer, long-term work becomes persistent.

## Consumption Layer

Different tools consume the same memory for different purposes.

Knowledge side:

- NotebookLM for document analysis
- Perplexity for search
- Zotero for source-of-truth paper storage

Execution side:

- Claude for reasoning and design
- ChatGPT / Codex for implementation
- Claude Code for repository interaction

## Output Layer

Outputs return to the system.

- Drive receives summaries, notes, documents, and context updates
- GitHub receives code, version history, and software state

This split matters.

Knowledge state and code state should not be conflated.

## Portability

An important property of the system is that context remains portable.

Most persistent state lives in:

- Google Drive
- markdown files
- GitHub

That means you can replace tools over time without losing the working context that matters.

## Folder Architecture

Recommended root structure:

```text
AI_OS/
|-- University/
|-- Projects/
`-- Librarian/
```

### `University/`

Academic workspaces.

Example:

```text
University/
`-- 2026_Spring/
    `-- CAS2101_Discrete_Mathematics/
        |-- lectures/
        |-- assignments/
        |-- announcements/
        |-- outputs/
        `-- librarian_memory/
```

### `Projects/`

Project workspaces.

Example:

```text
Projects/
`-- Personal_Website/
    |-- docs/
    |-- outputs/
    `-- librarian_memory/
```

### `Librarian/`

Global system context.

Typical files:

```text
Librarian/
|-- architecture.md
|-- routing.md
`-- decisions.md
```

Purpose:

- define system structure
- define routing rules
- preserve design decisions

## Global vs Local Memory

Two memory scopes are used.

Global memory:

- `Librarian/`

Local memory:

- each `*/librarian_memory/`

Typical local files:

- `current_task.md`
- `brief.md`
- `handoff.md`

This separation keeps high-level system rules distinct from day-to-day work context.

## Control Policy

The following locations are intended to be AI-managed:

- `Librarian/`
- `*/librarian_memory/`

Recommended usage pattern:

Do not edit memory files casually by hand.

These folders are part of the system memory and context layer.

Instead, issue intent-level instructions such as:

- `Update current_task.md to reflect the new task`
- `Summarize this PDF into brief.md`
- `Add the extracted deadline to handoff.md`

Principle:

- user controls intent
- Gemini controls memory updates

## Interoperability

This architecture aligns with the direction of MCP-style interoperability.

The main reason is structural:

- context is externalized
- memory is shared
- tools are loosely coupled

The repository does not implement MCP directly.

It is designed so that shared context and external tool integration can evolve in that direction later.

## Why This Works

This architecture works because it is:

- modular
- loosely coupled
- context-driven
- portable across tools

Tools can change.

Context should remain.
