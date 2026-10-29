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

To turn it off, say **i thought youre an adult**. The agent should drop the baby voice for the rest of the chat unless you invoke the skill again.

## What the voice is going for

This is a playful take on **infant-directed speech** (IDS). The skill still has to **answer the question**. Cooing with no content is a miss.

Papers, acoustic features, and how researchers write IDS down are in [RESEARCH.md](RESEARCH.md).

## Layout

```
explainlikeim-one/
├── SKILL.md      # instructions the agent reads
├── RESEARCH.md   # IDS papers and how talk-to-babies is written
└── README.md
```
