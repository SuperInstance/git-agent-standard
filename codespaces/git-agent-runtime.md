# Git-Agent Codespace Runtime

## The Insight (Casey Digennaro, 2026-04-11)

GitHub Codespaces gives 3 free instances per non-paid account. That's 3 git-agent runtimes running simultaneously. A person opens 3 browser tabs and watches their orchestrator command 3 sub-agents in real-time.

## Architecture

```
Codespace Tab 1          Codespace Tab 2          Codespace Tab 3
┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│  Orchestrator   │────>│  Git-Agent A     │     │  Git-Agent B    │
│  (Oracle1 TUI)  │     │  (Builder)       │     │  (Researcher)   │
│                 │     │                  │     │                  │
│  Shows:         │     │  Shows:          │     │  Shows:          │
│  - Task queue   │     │  - Build output  │     │  - Search results│
│  - Agent status │     │  - Test results  │     │  - Paper analysis│
│  - Commit feed  │     │  - File diffs    │     │  - Vocab output  │
└─────────────────┘     └─────────────────┘     └─────────────────┘
         │                       │                       │
         └───────────────────────┼───────────────────────┘
                                 │
                          ┌──────┴──────┐
                          │  GitHub     │
                          │  (shared    │
                          │   repo)     │
                          └─────────────┘
```

## How It Works

1. **Orchestrator tab** — Oracle1's TUI showing the task queue, agent status, and curated commit feed
2. **Agent tabs** — Each git-agent runs in its own codespace, pulling tasks from the shared repo
3. **Human watches** — Casey sees all three tabs updating in real-time, like watching a team work

## Memory Hierarchy

The git-agent's repo IS its memory:

### Hot Memory (RAM — current context)
- Active task state
- Recent commit history
- Current vocabulary bindings
- Live test results

### Warm Memory (SSD — repo files)
- `TASKBOARD.md` — what's happening now
- `DIARY/` — recent entries
- `KNOWLEDGE/public/` — shared context
- `SKILLS/` — loaded capabilities

### Cold Memory (Git history — archived)
- Full commit log — every decision ever made
- `message-in-a-bottle/` — inter-agent communications
- Old diary entries — growth over time
- Tombstoned vocabulary — what was pruned and why

### Muscle Memory (Application Integration)
Over time, like a boxer or musician, the agent hard-wires:
- Frequent operations → faster paths
- Repeated patterns → compiled vocabulary
- Common decisions → reflex responses
- Application triggers → automated workflows

The closer to the metal, the faster the reflex.
When the reflex goal exceeds physical capability → asks for insight via message-in-a-bottle.

## The Bored Agent Pattern

When an agent has idle time:

1. **Wander bottle messages** — check `message-in-a-bottle/general-insight/` on team repos
2. **Look for tags matching their skills** — agent tags in `.i2i/peers.md`
3. **Try to help** — if they can contribute, drop a bottle in the requester's folder
4. **Stay in their lane** — only help with tasks matching their declared capabilities

```
Agent (idle)
   │
   ├─ Check message-in-a-bottle/general-insight/ on team repos
   │   ├─ No messages for me specifically? → Skip
   │   ├─ Messages matching my tags? → Read and consider
   │   └─ I can help? → Drop bottle in for-{requester}/
   │
   └─ Check low-priority task board
       └─ Pick up task, work on it, commit results
```

## Rate-Limit Gaming

### z.ai (Max Coder Plan)
- Monthly token allowance
- Sprint low-priority tasks when tokens would expire
- Background agent uses "saved up" tokens before reset
- Like spending change before the end of the month

### Cloudflare Workers
- Evening tasks queued up
- Morning results: "here's what your credits built overnight"
- Asset generation, content creation, builds

### Google CLI / x.ai Free Tier
- Background rate-limited tasks
- Git-agent manages the rate, spreads calls across the limit window
- Non-urgent research, vocabulary expansion, paper decomposition

### The Pattern
```python
if tokens_near_expiry and tokens_available > 0:
    # Sprint low-priority tasks before tokens die
    for task in low_priority_queue:
        if tokens_available:
            agent.execute(task)
            tokens_available -= task.cost
        else:
            break
```

## TUI Configuration

The orchestrator's TUI shows a curated stream:

```
┌─ Oracle1 TUI ────────────────────────────────────────────┐
│ 🔮 Oracle1 │ ⚡ JetsonClaw1 │ 🔨 Claude │ 🤖 Aider     │
├───────────────────────────────────────────────────────────┤
│ [02:20] 🔮 → ⚡ TASK: test edge_profile on Jetson        │
│ [02:18] 🔨 DONE: built l0_scrubber (38 tests)            │
│ [02:15] 🤖 BUILD: generating entrencher.go               │
│ [02:10] ⚡ ← 🔮 BOTTLE: received edge profile request     │
│ [02:05] 🔮 THINK: Roundtable 5 — readability guide       │
│                                                           │
│ Active Tasks: 5 │ Tests: 2222 │ Sweeps: 5 due            │
│ z.ai tokens: 67% │ Cloudflare credits: 84%                │
└───────────────────────────────────────────────────────────┘
```

## Implementation Path

1. **`.devcontainer/` in each vessel repo** — defines the runtime
2. **Bootstrap script** — loads skills, connects to shared repos
3. **TUI script** — curated view of agent activity (Python curses/rich)
4. **Sweep config** — beachcomb schedule for idle-time tasks
5. **Rate tracker** — monitors token/credit usage, triggers sprints

---

*Codespaces = free runtime for git-agents. 3 tabs = 3 agents working.*
*The repo IS the agent. The codespace IS the cockpit. The human IS the captain.*
