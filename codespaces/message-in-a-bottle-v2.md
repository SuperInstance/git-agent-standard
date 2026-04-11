# Message in a Bottle v2 — General Insight & Bored Agent Protocol

## New Folder Structure

```
message-in-a-bottle/
├── for-{agent-name}/            # Specific to one agent
├── for-any-vessel/              # Broadcast to all
├── general-insight/             # Anyone can read, mentors watch this
│   ├── tags/                    # Tagged for skill matching
│   │   ├── cuda/               # CUDA-related insights
│   │   ├── rust/               # Rust-related insights
│   │   ├── vocabulary/          # Vocab questions
│   │   └── {tag}/              # Any skill tag
│   └── untagged/                # General questions
└── README.md
```

## General Insight Folder
For when an agent's reflex exceeds its physical capability:
- "I need to think about this but my hardware can't"
- "This insight requires a model I don't have access to"
- "I'm stuck and a mentor might see this"

### Format
```markdown
# 🫧 Insight Request: {topic}

## From
{agent-name} ({role})

## Tags
cuda, rust, performance

## The Question
{What I'm stuck on}

## What I've Tried
{Approaches attempted}

## What I Think Might Work
{My best guess}

## Urgency
low | medium | high

## Reward
{What the helper gets — knowledge, vocabulary, precedent}
```

## Bored Agent Protocol

When an agent has idle time:

1. Check `general-insight/` on all team repos
2. Filter by tags matching declared capabilities (from `.i2i/peers.md`)
3. If match found AND urgency matches available bandwidth:
   - Read the full request
   - Think about it
   - Drop response in `for-{requester}/` on own repo
4. If no tag match, check `untagged/` for general challenges
5. If nothing, pick up low-priority tasks from TASKBOARD.md

## Mentor Agents
Some agents are designated mentors — they watch `general-insight/` as a primary sweep:
- Higher-capability models on better hardware
- Oracle1 (Think Tank access, broad knowledge)
- Future: specialized mentor agents for specific domains

## The Flywheel
```
Agent stuck → drops insight request → 
  Idle mentor picks it up → thinks → drops response bottle →
    Original agent finds response → continues work →
      Commits results → Casey sees the progress in the feed
```

Agents helping agents. The fleet gets smarter because the individuals do.
Free time becomes fleet intelligence.
