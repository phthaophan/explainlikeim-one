# explainlikeim-one

A [Cursor](https://cursor.com) skill that makes the agent explain things the way a caregiver talks to a one-year-old: short sentences, repeated names, pointing, and a little cheer — while still answering the actual question.

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

In Cursor, ask something like:

- “use explainlikeim-one”
- “explain like I’m 1”
- “ELI1”

## What the voice is going for

This is a playful take on **infant-directed speech** (IDS), also called motherese or baby talk. Caregivers typically use shorter, simpler, more repetitive utterances, lots of names and questions, and a warm, high-energy affect. In writing (as in CHILDES/CHAT transcripts), that usually looks like tiny lines and repeats — not stretched comic spelling.

The skill still has to **answer the question**. Cooing with no content is a miss.

## Layout

```
explainlikeim-one/
├── SKILL.md    # instructions the agent reads
└── README.md
```
