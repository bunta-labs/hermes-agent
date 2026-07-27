# Changelog — Hermes Agent (AICompany Fork)

Notable changes to the AICompany fork of NousResearch/hermes-agent.

## [2026-07-27] — Profile Model Overhaul

### Changed
- **Default profile** — swapped primary from ornith-1.0-35b-1m to agents-a1 on llama.cpp :8001
- **11 specialist profiles** — model assignments updated based on v2 4-pass benchmark:
  - All profiles switched from `provider: custom` to `provider: lmstudio` (built-in)
  - Stale `custom_providers` entries (escaped JSON with llama-cpp) removed
  - Stale `base_url`/`api_key` fields removed from lmstudio profiles
- **long-context profile** — kept ornith-1.0-35b-1m (agents-a1 has 256K context, not 1M)

### Docs
- `Company Brain/knowledge/firstmate-model-assignment-guide.md` — updated leaderboard + assignments
- `Company Brain/knowledge/learnings.md` — profile assignment update entry

## [2026-07-26] — FirstMate Integration

### Added
- FirstMate fleet integration with 13 specialist profiles
- Kanban webhook HMAC-signed event delivery
- n8n MCP server registration
- memory-tencentdb as persistent gateway

### Changed
- Local-first architecture — all AI tools local, no cloud dependencies

## [2026-07-22] — Initial Fork + TUI Deployment

### Added
- Forked from NousResearch/hermes-agent for private cross-Mac sync
- Hermes TUI deployment with ornith-1.0-35b-1m
- Three MCP servers: ai_company, langgraph, n8n-mcp
- AICompany Electron app with Control Center dashboard
