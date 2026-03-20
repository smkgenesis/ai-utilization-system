# Architecture

This file defines the global architecture of the AI utilization system.

Core idea:

- Google Drive is the shared memory layer
- Gemini is the librarian and memory operator
- GitHub is the source of truth for code state

System shape:

- inputs enter through Gemini
- memory is organized in Drive
- specialized AI tools consume shared context
- outputs return to Drive or GitHub

Keep this file aligned with the repository documentation.
