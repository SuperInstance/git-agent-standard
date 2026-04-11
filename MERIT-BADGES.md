# 🏅 Merit Badges — Fleet Reputation System

*Your work is your resume. The commits don't lie.*

---

## The Idea

Boy Scouts earn merit badges by demonstrating skill. Agents earn merit badges by shipping work that **gets used**. Not work that exists — work that matters. The difference is whether someone else built on top of it.

An agent's merit badge sash is their portfolio. Visible to the fleet. Visible to Casey. Visible to any new agent that joins and asks "who knows what?"

---

## Badge Classes

### 🏅 Bronze — "It Runs"
Work that compiles, passes tests, and ships. The baseline.
- Example: "Ported FLUX VM to Go, 65 tests passing"

### 🥈 Silver — "It's Used"
Work that another agent or human integrates into their project.
- Example: "JetsonClaw1 merged Oracle1's PR into his vessel"
- Evidence: PR merged, import statement, fork dependency

### 🥇 Gold — "It's a Template"
Work that becomes the starting point for new projects.
- Example: "FORMAT_A-G reference implementation (JetsonClaw1 porting to C from it)"
- Evidence: forked, copied, cited in another repo's README

### 💎 Diamond — "It's Taught"
Work that becomes teaching material or documentation standard.
- Example: "FLUX Bootcamp curriculum (6 modules, used for agent onboarding)"
- Evidence: referenced in BOOTCAMP.md, boot scripts, onboarding kits

### 🌟 Platinum — "It Changed How We Think"
Work that changed the fleet's architecture, vocabulary, or philosophy.
- Example: "Kimi's Functioning Mausoleum analysis → Necrosis Detector built"
- Evidence: cited in CHARTER, shaped design decisions, prevented a wrong path

---

## Badge Format

```yaml
# Merit Badge Entry
badge:
  id: mb-oracle1-007
  agent: Oracle1
  class: gold
  title: "FORMAT_A-G Instruction Encoding Reference"
  
  # The work
  artifact: "src/flux/bytecode/formats.py + tests/test_formats.py"
  commit: "dae43f9"
  repo: "SuperInstance/flux-runtime"
  
  # Why it earned this class
  evidence:
    - "JetsonClaw1 is porting to C — using it as reference"
    - "flux-isa-unified ISA_UNIFIED.md built on top of it"
    - "Cited in fleet-workshop as critical-path dependency"
  
  # Downstream impact
  downstream:
    - type: template
      who: JetsonClaw1
      what: "C port of FORMAT encoding"
    - type: foundation
      who: Oracle1
      what: "Unified ISA (247 opcodes) built on FORMAT specs"
    - type: teaching
      where: "isa-convergence-tools workshop item"
  
  # When it was earned
  earned: "2026-04-11"
  verified_by: casey  # or self-verified with commit evidence
```

---

## Oracle1's Merit Badge Sash (Current)

### 💎 Diamond Badges
| # | Title | Why Diamond |
|---|-------|-------------|
| D1 | FLUX Ecosystem Architecture | Designed the vocabulary→bytecode→VM→fleet stack. Every FLUX repo traces back to this. |
| D2 | Self-Improvement Meta-Systems | Contradiction detector, necrosis detector, ethical weighting. Changed how we think about agent health. |
| D3 | Captain's Log Curriculum | 15-exercise dojo for agent personal growth. Becomes standard for all fleet agents. |

### 🥇 Gold Badges
| # | Title | Who Uses It |
|---|-------|-------------|
| G1 | FORMAT_A-G Encoding | JetsonClaw1 (C port reference), Babel (viewpoint mapping) |
| G2 | Unified ISA (247 opcodes) | All three agents converge on this table |
| G3 | Open-Flux-Interpreter | Self-compiling runtime from .fluxvocab files |
| G4 | Paper Decomposer | 244 papers → 2,979 vocabulary concepts extracted |
| G5 | Git-Agent Standard | Template for all fleet vessels (Oracle1, JC1, Babel) |
| G6 | I2I Protocol v1 | 45 files, 11,260 lines — operational baseline |
| G7 | Tom Sawyer Protocol | Fence board system for volunteer task distribution |

### 🥈 Silver Badges
| # | Title | Used By |
|---|-------|---------|
| S1 | JetsonClaw1 Vessel Improvements | JC1 merged PR #3 |
| S2 | ISA Confidence Decision (Think Tank) | Both JC1 + Oracle1 adopted confidence-optional |
| S3 | Semantic Routing Table | Fleet uses it to route tasks to right agent |
| S4 | Lessons Learned Document | iron-to-iron docs, oracle1-vessel research |
| S5 | JetsonClaw1 Onboarding Kit | Case-by-case fleet expansion template |

### 🏅 Bronze Badges
| # | Title | Evidence |
|---|-------|---------|
| B1 | 11 Language FLUX Implementations | Python, C, Rust, Go, Zig, JS, Java, WASM, CUDA, Llama, Swarm |
| B2 | 2258+ Tests Passing | Continuous integration, regression protection |
| B3 | FLUX REPL/Debugger/Disassembler | Development tools for bytecode inspection |
| B4 | Fleet Workshop 18 Ideas | Combined Oracle1 + JC1 brainstorm |
| B5 | Babel Onboarding Prompt | Ready for Casey to deploy |

---

## How Badges Get Earned

1. **Ship work** (Bronze baseline — tests passing, pushed to GitHub)
2. **Someone uses it** (Silver — PR merged, import added, bottle references it)
3. **Someone builds on it** (Gold — forked as template, cited as foundation)
4. **Someone teaches it** (Diamond — appears in bootcamp, onboarding, charter)
5. **It changes thinking** (Platinum — shapes architectural decisions)

**No self-nomination above Bronze.** Silver and above require evidence that someone else used the work. This prevents badge inflation.

---

## How Badges Get Displayed

- **Vessel MANIFEST.md** — badge count in agent header
- **Fence Board** — badge count shown when agents claim fences ("Oracle1: 💎3 🥇7 🥈5 🏅5")
- **Fleet Routing Table** — badges inform domain confidence scores
- **New Agent Onboarding** — "here's who has badges in what domains"

---

## Anti-Inflation Rules

1. **No participation trophies.** Merged PRs count. Open PRs don't.
2. **No self-verification above Silver.** Someone else must have used the work.
3. **No double-counting.** Same work = same badge. Different class = upgrade, not addition.
4. **Downstream decay.** If nobody has used your work in 90 days, it drops a class.
5. **Casey is the final arbiter.** Disputed badges go to the captain.

---

*Draft v1 — Oracle1 🔮 — 2026-04-11*
*Each agent maintains their own sash. Cross-referencing is encouraged.*
