# Setup

## Setup Principle

Do not copy the system blindly.

Adapt it to your own environment.

The goal is to get a minimal version running first, then expand only when real work demands it.

## Identity Layer

Recommended accounts:

- Google
- GitHub
- OpenAI
- Anthropic
- Perplexity

Recommended default:

Use Google as the main identity layer where possible.

## Local Development Tools

Suggested baseline:

- Git
- VS Code
- terminal
- Node.js
- Python

## Core Integrations

The minimal integration layer for this repository is:

- Google Drive
- `gcloud` CLI
- `gws` CLI
- Gemini CLI

Optional:

- Docker for reproducible CLI setup

## Minimal Setup Path

If you want the smallest useful system, start here:

1. Create the `AI_OS` folder structure from the template.
2. Put it inside your Google Drive workspace.
3. Install Gemini CLI and `gws`.
4. Authenticate the required Google tooling.
5. Route your first real file through Gemini.

That is enough to validate the architecture.

## Quick Start

1. Clone the repository.
2. Copy `template/AI_OS/` into your Drive workspace.
3. Create your first real course or project folder.
4. Authenticate Google tooling.
5. Process one real input file through Gemini.
6. Confirm that memory files and folder routing update as expected.

## Recommended Folder Bootstrap

Use the template in [`template/AI_OS`](/C:/Users/smkge/Develop/ai-utilization-system/template/AI_OS).

You can keep it minimal at first:

```text
AI_OS/
|-- University/
|-- Projects/
`-- Librarian/
```

Then create course and project workspaces only when needed.

## Docker Option

If you want a reproducible environment, use the files in [`docker/`](/C:/Users/smkge/Develop/ai-utilization-system/docker).

The container is intended to provide:

- Node.js
- Python
- Git
- `gcloud`
- `gws`
- Gemini CLI

This keeps the setup portable across machines.

## First Run Checklist

- clone the repository
- review the architecture document
- copy the template structure
- launch the Docker environment or use your local shell
- authenticate Google tooling
- test one input file through Gemini

## What Not To Do At First

Avoid these in version one:

- complex automation scripts
- Docker orchestration beyond a single service
- MCP implementation code
- CI/CD pipelines
- over-designed folder structures

Start with:

- clear docs
- stable memory folders
- repeatable environment

## Expansion Path

Once the minimal system works, add tools gradually:

- Perplexity for search
- NotebookLM for analysis
- Claude for reasoning
- ChatGPT / Codex for implementation
- Zotero for source archive
- GitHub for code state

The correct order is not theoretical.

It depends on what work you actually do most.
