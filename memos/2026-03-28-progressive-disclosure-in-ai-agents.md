file-created-at:: 2026-03-28

# Progressive Disclosure in AI Agents

Progressive disclosure in AI agents is a context management technique that feeds information to an LLM on demand rather than all at once, improving efficiency and accuracy.

## Context Optimization

Instead of loading all available tools and data, the agent initially receives only descriptions of capabilities. Detailed, heavy information (for example, full API schemas and large documents) is loaded only when the agent determines it is relevant to the task.

## Layered Architecture

It often follows a three-layer approach:

1. `Layer 1 (Index)`: Lightweight metadata (names, descriptions) that allows the agent to decide which skill/tool to use.
2. `Layer 2 (Details)`: Full content/instructions (for example, `skill.md`) loaded on demand.
3. `Layer 3 (Deep Dive)`: Supporting files, documentation, or examples accessed only when necessary.
