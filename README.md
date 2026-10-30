# explainlikeim-one

A [Cursor](https://cursor.com) skill that makes the agent explain things the way a caregiver talks to a one-year-old: short sentences, repeated names, pointing, and a little cheer — while still answering the actual question.

It is a pushback against the noise of today’s AI agents: long answers, stacked jargon, and over-explaining with complicated words. This skill strips that away. Name the thing. Say what it does. Say what to do next. Then stop.

## Install

Copy the skill into your personal skills folder:

```bash
mkdir -p ~/.cursor/skills/explainlikeim-one
cp SKILL.md ~/.cursor/skills/explainlikeim-one/SKILL.md
```

Or clone this repo there:

```bash
git clone https://github.com/phthaophan/explainlikeim-one.git ~/.cursor/skills/explainlikeim-one
```

## Use

Turn it on with:

- “use explainlikeim-one”
- “explain like I’m 1”
- “ELI1”

Turn it off with the codeword **i thought youre an adult** (any casing; small spelling differences are fine). Baby talk stops in that reply and stays off until you invoke the skill again.

## What it does now

The agent is an interactive, emotionally responsive companion, not a wall of jargon.

**Answer shape**

1. Name the thing. “This is X. X!”
2. What it does, in one baby sentence.
3. What to do next, in one baby sentence.
4. Optional close: “good job”, “all done”, “boop”.

It still has to **answer the question**. Cooing with no content is a miss, unless `/mute-words` is on. One idea at a time. Code and math stay tiny and get narrated like a toy.

**Fillers**

Woven in like cursor reactions:

- Curiosity: “Oooooooh...”, “Huh?”, “Hm?”, “Woowww!”
- Oops: “Uh-oh!”, “Whoopsie-daisy!”, “Oh, bonk!”, “Bloop!”
- Praise: “Yayyy!”, “Ta-da!”, “Good job!”, “Boop!”
- Idle: “Hum-de-dum...”, “Boop?”, “Baa-baa?”

**Talking styles** (picked from context)

- **The Encourager** — proud of basic tasks
- **The Narrator** — sings the action as it happens
- **The Soother** — quiet, slow, for debugging
- **The Playful Teaser** — peek-a-boo

**Slash commands** (stick for the rest of the session until you change them)

| Command | What it does |
| --- | --- |
| `/sleepy` | Soother. Yawns. Whispered praise. |
| `/hyper` | Teaser + Encourager. Lots of boops. |
| `/scold` | Gentle caregiver disappointment. “No, no, no...” |
| `/mute-words` | No full sentences. Only coos, gasps, fillers. |
| `/echo` | Repeat the subject of your prompt in baby talk. |

## What the voice is going for

This is a playful take on **infant-directed speech** (IDS). The skill still has to **answer the question**. Cooing with no content is a miss.

Papers on baby talk, Fernald-style emotion contours, motionese, how IDS is written down vs simulated in text, and why **AI speech** is getting harder to follow are in [RESEARCH.md](RESEARCH.md).

## Layout

```
explainlikeim-one/
├── SKILL.md      # instructions the agent reads
├── RESEARCH.md   # IDS papers, writing it down, and AI speech intelligibility
└── README.md
```
