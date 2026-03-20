# Workflows

## Purpose

These workflows show how the architecture behaves in actual use.

The goal is not to force a single pipeline.

The goal is to make memory, context, and execution work together.

## 1. Course Material Automation

Flow:

`Download -> Gemini -> Google Drive -> memory update`

Example:

1. Download a lecture PDF or course announcement.
2. Pass the file to Gemini CLI.
3. Gemini detects course context, renames the file, and routes it into the correct course folder.
4. Gemini updates `current_task.md`, `brief.md`, or `handoff.md` if needed.

Expected outcome:

- files stop accumulating in Downloads
- course context remains current
- deadlines and task state become persistent

## 2. Research Workflow

Flow:

`Perplexity -> Zotero -> NotebookLM -> Claude`

Role split:

- Perplexity finds material
- Zotero stores the original source
- NotebookLM analyzes documents
- Claude helps synthesize and structure arguments

Drive stores:

- notes
- summaries
- project context
- writing outputs

This keeps source preservation and AI interpretation separate.

## 3. Long Document Writing

Flow:

`Drive context -> Claude or ChatGPT -> draft -> Drive`

Example:

1. Store background notes, references, and outlines in Drive.
2. Use the memory files to define the current writing objective.
3. Ask an execution model to draft or revise a section.
4. Write the result back into the project folder.

Expected outcome:

- writing is grounded in persistent context
- sessions do not restart from zero
- draft history remains attached to the project workspace

## 4. Software Project Workflow

Flow:

`Drive docs + memory -> ChatGPT / Codex -> GitHub`

Split of responsibilities:

- Drive stores project documentation and AI context
- GitHub stores source code and version history
- Gemini updates project memory
- Codex or ChatGPT handles implementation

This avoids mixing design notes and code state into a single storage system.

## 5. Shared Context Across AIs

Flow:

`librarian_memory/ -> multiple AI tools`

Use case:

- Claude reads project brief for system design
- Codex reads the same brief for implementation
- NotebookLM reads the same documents for analysis

The shared memory layer reduces repeated explanation between tools.

## 6. Schedule Extraction

Flow:

`Document -> Gemini -> memory update -> optional calendar action`

Example:

1. You receive a syllabus or assignment document.
2. Gemini extracts deadlines and important dates.
3. Gemini updates the relevant memory files.
4. You optionally sync those dates into a calendar workflow.

This turns static documents into actionable context.

## Operating Rule

The best workflow is the one that keeps real work moving.

If a new tool increases friction more than value, do not add it yet.
