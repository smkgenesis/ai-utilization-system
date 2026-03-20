# AI Utilization System

Reference repository for the AI utilization system.

If you already read the blog post, treat this repository as the implementation-facing companion: documentation, folder templates, examples, and a minimal reproducible environment.

For Korean readers, see [`README.ko.md`](/C:/Users/smkge/Develop/ai-utilization-system/README.ko.md).

## What This Repo Contains

- architecture docs for the system structure
- setup guidance for the baseline environment
- workflow references for common operating patterns
- an `AI_OS` folder template you can copy into Drive
- example `librarian_memory` files
- a minimal Docker environment for CLI-based setup

This repo is not an app and not a full automation framework.

It is a system template.

## Reader Assumption

This README assumes you already understand the high-level idea:

- shared memory lives outside any single AI tool
- tools have clear roles
- context should persist across sessions

If you need the concept and motivation first, start from the blog post, then return here.

## Start Here

1. Read [`docs/architecture.md`](/C:/Users/smkge/Develop/ai-utilization-system/docs/architecture.md).
2. Review [`docs/setup.md`](/C:/Users/smkge/Develop/ai-utilization-system/docs/setup.md).
3. Copy [`template/AI_OS`](/C:/Users/smkge/Develop/ai-utilization-system/template/AI_OS) into your Drive workspace.
4. Use [`examples/`](/C:/Users/smkge/Develop/ai-utilization-system/examples) to shape your first `librarian_memory` files.
5. If you want a reproducible environment, use [`docker/README.md`](/C:/Users/smkge/Develop/ai-utilization-system/docker/README.md).

## Repository Map

### [`docs/`](/C:/Users/smkge/Develop/ai-utilization-system/docs)

Core reference documents.

- [`docs/architecture.md`](/C:/Users/smkge/Develop/ai-utilization-system/docs/architecture.md): system structure, memory model, and control policy
- [`docs/setup.md`](/C:/Users/smkge/Develop/ai-utilization-system/docs/setup.md): baseline environment and recommended setup order
- [`docs/workflows.md`](/C:/Users/smkge/Develop/ai-utilization-system/docs/workflows.md): example workflows for study, research, writing, and software projects
- [`docs/philosophy.md`](/C:/Users/smkge/Develop/ai-utilization-system/docs/philosophy.md): design constraints and operating principles

### [`template/AI_OS/`](/C:/Users/smkge/Develop/ai-utilization-system/template/AI_OS)

Starting folder structure for the shared memory layer.

Includes:

- `University/`
- `Projects/`
- `Librarian/`
- example `librarian_memory/` files for course and project workspaces

Use this as a bootstrap, not as a rigid schema.

### [`examples/`](/C:/Users/smkge/Develop/ai-utilization-system/examples)

Small sample files for:

- `current_task.md`
- `brief.md`
- `handoff.md`

These are intended to show the expected shape of local working context.

### [`docker/`](/C:/Users/smkge/Develop/ai-utilization-system/docker)

Minimal reproducible CLI environment for working with:

- `gcloud`
- `gws`
- Gemini CLI
- Node.js
- Python

Use this if you want a clean starting point instead of configuring everything directly on the host.

## Recommended Use

Use this repository in three layers.

1. Read the docs to understand the operating model.
2. Copy the template into your own workspace.
3. Adapt the structure and tooling to your environment.

The important artifact is not the repo itself.

The important artifact is your own working system derived from it.

## Minimal Adoption Path

If you want the smallest possible starting point:

1. Create `AI_OS/`
2. Add `University/`, `Projects/`, and `Librarian/`
3. Add one real `librarian_memory/` folder
4. Install Gemini CLI and `gws`
5. Route one real file through the system

That is enough to validate the architecture.

## Operating Rule

Treat these locations as AI-managed memory by default:

- `Librarian/`
- `*/librarian_memory/`

User intent should drive updates.

The memory operator should maintain the files.

## Scope

This repository intentionally does not try to provide:

- a universal standard
- a finished product UI
- full workflow automation
- one fixed tool stack for everyone

It provides a clear starting structure that you can adapt.

## Related

- Repository: [smkgenesis/ai-utilization-system](https://github.com/smkgenesis/ai-utilization-system)
