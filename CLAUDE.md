# Antigravity / Claude Code Developer Guidelines

## Graphify Integration Rules
- This workspace uses Graphify for codebase indexing, located in `graphify-out/`.
- **CRITICAL:** For any natural-language query about codebase structure, relationships, file content, or data flow, you MUST check `graphify-out/graph.json` first.
- Run queries using the Graphify CLI or the inline NetworkX script:
  `& (Get-Content graphify-out/.graphify_python) -m graphify query "<question>"`
- Avoid using native `view_file` or `grep_search` to explore relationships unless the graph does not contain the required information.

## Commands Reference
- Run a graph query: `& (Get-Content graphify-out/.graphify_python) -m graphify query "QUESTION"`
- Find shortest path: `& (Get-Content graphify-out/.graphify_python) -m graphify path "NODE_A" "NODE_B"`
- Explain concept: `& (Get-Content graphify-out/.graphify_python) -m graphify explain "NODE_NAME"`
- Update index: `& (Get-Content graphify-out/.graphify_python) -m graphify . --update`
