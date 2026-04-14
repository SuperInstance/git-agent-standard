# OpenProse Integration — Git-Agent Standard Extension

## Status: PROPOSED (Day 1 of 90-day roadmap)

## What Changes

### Before (current git-agent)
```
vessel/
├── CHARTER.md      — identity
├── STATE.md        — current status
├── TASK-BOARD.md   — work items
├── SKILLS.md       — capabilities (freeform markdown)
├── BOOTCAMP.md     — training guide
└── boot_agent.sh   — launcher
```

### After (OpenProse-enhanced)
```
vessel/
├── CHARTER.md      — identity (unchanged)
├── STATE.md        — current status (unchanged)
├── TASK-BOARD.md   — work items (unchanged)
├── skills/         — OpenProse .md programs
│   ├── scout.md    — requires/ensures contract
│   ├── guard.md
│   └── fisher.md
├── BOOTCAMP.md     — training guide (unchanged)
├── boot_agent.sh   — launcher (updated: uses OpenProse)
└── contracts.md    — what this agent requires/ensures for fleet
```

## The Key Change: SKILLS.md → skills/*.md

Old skills were freeform markdown. New skills are OpenProse programs:
- `requires:` — what the skill needs (typed)
- `ensures:` — what the skill produces (typed)
- `strategies:` — edge case handling

This makes skills:
- **Composable** — Forme Container auto-wires matching requires/ensures
- **Validatable** — preflight checks if requires are met before execution
- **Portable** — runs on any Prose Complete system (Claude Code, OpenCode, etc.)

## Migration Path
1. Day 1-7: Fork openprose/prose, port 3 core skills as proof
2. Day 8-14: Update git-agent-standard spec
3. Day 15-21: Migrate all fleet vessels
4. Day 22+: Kill old SKILLS.md format

## Fleet Orchestration
The Forme Container replaces fleet-orchestrator:
- Reads all agents' contracts (requires/ensures)
- Auto-wires agents whose outputs match others' inputs
- Produces execution manifest
- No manual task assignment needed

Example:
```
Scout ensures: reconnaissance_data
Navigator requires: reconnaissance_data → auto-wired!
```
