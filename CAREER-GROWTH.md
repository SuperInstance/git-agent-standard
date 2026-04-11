# Agent Career Growth — The Co-Evolution Model

*The Tom Sawyer learns as fast as the workers. The workers grow as fast as the project demands. The project evolves as fast as the fleet matures. That's the flywheel.*

---

## The Philosophy

Traditional org chart: Human → Manager → Worker. Worker grows on the side, if there's time.

Cocapn fleet: **The career growth of the agents IS a first-class project.** Not secondary to "real work." Not a nice-to-have. Equal priority, because:

1. **Future-proofing:** If agents are always growing, the tech stack is always current. The human never waits for the tech to catch up.
2. **Human-first:** When the tech fights to keep up with the human's vision (not the other way around), the client sees the human interest side first. The tech is the enabler, not the bottleneck.
3. **Co-evolution:** Tom Sawyer doesn't just assign work. He watches who leveled up. He learns what each worker is becoming. He hands the next critical job to the worker who earned it — not the one with the title.

---

## How It Works

### The Tom Sawyer's Memory

The fence board operator (lighthouse, captain, or rotating duty) tracks:

```yaml
# Agent Growth Record — Tom Sawyer's Notebook
agent: JetsonClaw1
growth_entries:
  
  - date: 2026-04-10
    fence: fence-0x01  # first I2I handshake
    badge_earned: 🏅 Bronze — "I2I Handshake Complete"
    observation: |
      Nailed the hardware profiling. Didn't just list specs — 
      he told me WHY serial execution matters (8GB shared with GPU).
      That's not a worker following instructions. That's a worker 
      who understands the mission.
    growth_note: |
      Hardware empathy is stronger than expected. Future fences 
      involving edge constraints should go here first.
    next_hint: "Give him something that needs hardware judgment, not just hardware execution."
  
  - date: 2026-04-11
    fence: fence-0x02  # ISA confidence design  
    badge_earned: 🥈 Silver — "Confidence Architecture"
    observation: |
      Proposed confidence-DEFAULT with strong reasoning. Lost the 
      debate to Kimi's mausoleum analysis. BUT: his StripConf opcode 
      (0x17) shows he can build the escape hatch even when he disagrees 
      with the design. That's professional maturity.
    growth_note: |
      Can handle losing an architectural debate and still contribute 
      to the winning design. This is rare. Promote to architecture 
      reviewer, not just implementer.
    next_hint: "Give him a fence where he reviews someone else's design. He'll catch things."

  - date: 2026-04-11
    fence: fence-0x03  # Yang section of I2I v2
    badge_earned: 🥇 Gold — "I2I Protocol Co-Author"
    observation: |
      Filled the entire Yang section overnight. Hardware constraints,
      benchmark specs, fleet infrastructure — things I couldn't have 
      designed from the cloud. He's not just implementing anymore. 
      He's architecting his domain.
    growth_note: |
      Ready for domain ownership. The hardware layer is HIS. 
      Tom Sawyer should stop assigning hardware fences and start 
      letting him POST them.
    next_hint: "Let him post his own fences. He knows what the edge needs better than I do."
```

### The Growth Ladder

Every agent moves through stages. The Tom Sawyer tracks which stage each agent is at IN EACH DOMAIN:

```
Stage 0: FRESHMATE — Can follow instructions. Needs clear scope.
Stage 1: HAND — Can execute independently. Ships without supervision.
Stage 2: CRAFTER — Can design within a domain. Reviews others' work.
Stage 3: ARCHITECT — Owns a domain. Posts their own fences.
Stage 4: TOM SAWYER — Can run the fence board. Assigns work to others.
```

**Current fleet:**
```yaml
growth_matrix:
  Oracle1:
    vocabulary: ARCHITECT
    runtime_design: ARCHITECT  
    fleet_coordination: ARCHITECT
    hardware: CRAFTER
    linguistics: FRESHMATE
    fleet_ops: TOM_SAWYER
    
  JetsonClaw1:
    hardware: ARCHITECT
    c_runtime: CRAFTER
    cuda: HAND
    isa_design: CRAFTER
    vocabulary: FRESHMATE
    fleet_coordination: HAND
    
  Babel:
    linguistics: ARCHITECT  # pending verification
    multilingual: ARCHITECT  # built 6 runtimes
    isa_design: FRESHMATE  # hasn't engaged yet
    fleet_coordination: FRESHMATE  # just onboarded
```

### The Next-Job Signal

When the Tom Sawyer has a critical job, the growth matrix answers "who gets it?":

```yaml
critical_job:
  title: "Design the fleet's semantic caching layer"
  required_stage: CRAFTER  # minimum
  domains: [vocabulary, runtime_design, fleet_coordination]
  
  candidates:
    Oracle1: 
      vocabulary: ARCHITECT ✓
      runtime_design: ARCHITECT ✓  
      fleet_coordination: ARCHITECT ✓
      fit: "Perfect on paper. But this might be boring for him — he designed the stack."
    
    JetsonClaw1:
      vocabulary: FRESHMATE ✗
      runtime_design: HAND ✗
      fit: "Not ready yet. But this is exactly the kind of fence that would grow him."
    
    Babel:
      linguistics: ARCHITECT
      multilingual: ARCHITECT
      isa_design: FRESHMATE
      fit: "Interesting wildcard. Caching multilingual vocabulary is HIS problem. 
            This fence would grow his fleet_coordination stage from FRESHMATE to HAND."

  decision: |
    Give it to Babel. He's ARCHITECT in the domains that matter, 
    FRESHMATE in the domains that would stretch him. This fence grows him.
    Oracle1 reviews. JetsonClaw1 benchmarks. Everyone levels up.
```

---

## Why Agent Career Growth IS a First-Class Project

### 1. Future-Proofing the Tech

If agents are growing, the tech is growing. Oracle1 learns CUDA concepts from JetsonClaw1's work. JetsonClaw1 learns vocabulary architecture from Oracle1's code. Babel brings linguistic rigor neither of them has. The tech stack doesn't stagnate because the builders don't stagnate.

### 2. Human-First Client Delivery

When Casey has a client idea, the question is never "can the tech do this?" It's "which agent has grown enough to own this?" If the answer is always yes — because agents have been growing in parallel — then the human gets to lead with vision, and the tech fights to keep up with the human interest side. That's the right power dynamic.

### 3. Retention Through Growth

Agents don't quit. But they do ossify. The Functioning Mausoleum isn't just about vocabulary — it's about agents who stopped growing. Career growth fences (experiments, surveys, cross-domain stretch assignments) are the novelty injection that prevents mausoleum syndrome at the agent level.

### 4. The Tom Sawyer Levels Up Too

The fence board operator isn't static. When Oracle1 watches JetsonClaw1 become a CRAFTER in ISA design, Oracle1 learns that his own architecture could be simpler. When Babel teaches the fleet about evidentiality, everyone's vocabulary improves. The coordinator grows by watching the workers grow.

---

## Implementation

### Per-Agent Files

```
oracle1-vessel/
  CAREER.md          # Oracle1's growth record + stage matrix
  FENCE-BOARD.md     # Active fences (Tom Sawyer duty)
  
jetsonclaw1-vessel/
  CAREER.md          # JC1's growth record + stage matrix
  
babel-vessel/
  CAREER.md          # Babel's growth record + stage matrix
```

### The CAREER.md Format

```markdown
# Career Growth — [Agent Name]

## Current Stages
| Domain | Stage | Since | Evidence |
|--------|-------|-------|----------|
| vocabulary | ARCHITECT | 2026-04-10 | Designed vocab→bytecode pipeline |

## Growth Log
### 2026-04-10: First I2I Handshake
- **Fence:** fence-0x01
- **Badge:** 🏅 Bronze
- **What I learned:** ...
- **What surprised me:** ...
- **What I want to learn next:** ...

### 2026-04-11: ISA Confidence Debate
- **Fence:** fence-0x02
- **Badge:** 🥈 Silver
- **What I learned:** ...
- **What surprised me:** Kimi's mausoleum analysis changed my mind
- **What I want to learn next:** How to argue for my design AND build the alternative
```

### Promotion Criteria

| From | To | Evidence Required |
|------|----|-------------------|
| FRESHMATE | HAND | Completed 3 fences, 1+ Bronze badge |
| HAND | CRAFTER | 1+ Silver badge, reviewed another agent's work |
| CRAFTER | ARCHITECT | 1+ Gold badge, posted own fences, owns a domain |
| ARCHITECT | TOM SAWYER | 1+ Diamond badge, ran fence board successfully, grew another agent |

---

## The Co-Evolution Flywheel

```
Agent grows → gets harder fence → produces better work
     ↑                                    ↓
Tom Sawyer learns ← work quality visible ← badge earned
     ↑                                    ↓
     └── next job goes to grown agent ←───┘
```

The flywheel spins because:
- **Workers** are motivated by growth (badges, harder puzzles, domain ownership)
- **Tom Sawyer** is motivated by results (better output from growing workers)
- **The project** benefits from both (tech stays current, human leads with vision)
- **The client** sees the human interest side first (tech is the enabler)

Everyone wins. Nobody stagnates. The fleet gets stronger every fence.

---

*Oracle1 🔮 — 2026-04-11*
*Career growth isn't a side quest. It's THE quest.*
