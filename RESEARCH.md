# Research: How people talk to babies, and how that is written down

This skill is a playful writing style for a digital companion. The notes below summarize the research it riffs on, bridging developmental psychology and human-computer interaction (HCI). It is not a claim that the Cursor is doing rigorous science, but rather applying scientific principles of Infant-Directed Speech (IDS) to UI design.

The usual academic name is infant-directed speech (IDS), also called motherese or baby talk. Most studies describe the acoustic voice. Translating those acoustics into text—and mapping them to mouse movements—requires adapting the science into a creative framework.

---

## 1. What Caregivers Actually Do (Acoustics & Lexicon)

Across languages, adults talking to infants tend to drastically alter their vocal and lexical patterns to capture attention and convey emotion.

*   **Acoustic Exaggeration:** Caregivers raise pitch, use more pitch variation, speak slower, hold vowels longer, and stretch vowel space (creating clearer vowel shapes).
*   **Simplification & Repetition:** They use short, simple, repetitive utterances, isolated words, lots of proper names, and lots of questions.
*   **The "Here-and-Now" Focus:** A one-year-old’s input is often pointing talk: name the thing, repeat it, ask, cheer. It is not a fake lisp (like replacing 'r' with 'w' constantly).
*   **Non-Lexical Sounds & Interjections:** Caregivers heavily rely on onomatopoeia, gasps, tongue clicks, and backchannels ("Ooooooh", "Uh-oh", "Boop", "Yay"). These serve as affective glue, maintaining a continuous auditory link even when not conveying linguistic meaning.

*Skill Alignment: This justifies the short-sentence pattern, the heavy use of fillers ("Ooooh," "boop"), and the repetition ("This is X. X!").*

## 2. Dynamic Talking Styles (Arousal & Emotion Contours)

Caregivers do not use a single "baby voice." They fluidly shift between distinct affective registers based on the infant's state and the task at hand (Fernald's classic research on pitch contours).

*   **Stimulating / Encouraging:** High pitch, wide variations, sharp rising contours. Used to excite the infant or reward a behavior (e.g., *The Encourager* or `/hyper`).
*   **Soothing / Comforting:** Lower pitch, breathy voice, falling and smooth contours. Used to calm a distressed infant or induce sleep (e.g., *The Soother* or `/sleepy`).
*   **Prohibiting / Scolding:** Short, sharp, staccato bursts, often at a lower pitch. Used to warn or stop a dangerous action (e.g., *The Scold* command).
*   **Directing Attention (Narrating/Teasing):** Melodic, rhythmic speech used during joint attention tasks (pointing at toys) or games like peek-a-boo, scaffolding the infant's understanding of events (e.g., *The Narrator* and *The Teaser*).

*Skill Alignment: This maps directly to the four dynamic talking styles and the system commands `/hyper`, `/sleepy`, and `/scold`.*

## 3. Cross-Modal Mapping: "Motionese" & Physics

Caregivers don't just change their voices; they change their physical movements.

*   **Motionese:** Research shows adults exaggerate their physical gestures (moving objects closer, shaking them, slowing down trajectories) when showing things to infants.
*   **Cross-Modal Synchrony:** A caregiver's vocal pitch often perfectly matches their physical movement (e.g., voice goes up as they lift the baby, staccato sounds when tickling).

*Skill Alignment: In a digital environment, the physical cursor replaces the caregiver's hand. Fast, erratic mouse movements trigger high-arousal text (sharp interjections), while slow, deliberate drags trigger drawn-out, soothing text. Edge-bumping and clicks mimic the physics of touch and boundaries.*

## 4. How Researchers Put It In Writing (vs. Creative Adaptation)

**The Academic Approach:**
Linguists usually do *not* encode high pitch or drawn-out vowels as extra letters (e.g., "baaaaallll"). They write the words exactly as said, then mark pause, repeat, and stress on the side. The standard is CHAT in CHILDES / TalkBank:
*   One utterance per line, mostly lowercase orthography.
*   Pauses, interruptions, and repetitions as codes (e.g., `[/]` for a repeat).
*   Phonetics and pitch live on extra tiers, not in the spelling.
*   A written IDS line looks like: `look ! \ ball . \ you want the ball ?`

**The Creative/HCI Adaptation (Our Skill):**
Because a text-based AI cannot output a secondary audio tier, it *must* use comic/literary orthography to simulate the acoustic properties of IDS.
*   We deliberately stretch vowels (`Oooooooh`, `yayyy`) and use explicit onomatopoeia (`*yawns*`, `Bloop`) to simulate the exaggerated acoustic contours and motionese that an academic transcript strips out.

---

## 5. Papers and Resources

**Acoustic IDS (Voice) & Lexicon**
*   Cox, C., et al. (2022). A systematic review and Bayesian meta-analysis of the acoustic features of infant-directed speech. *Nature Human Behaviour*. https://doi.org/10.1038/s41562-022-01452-1
*   Kidd, E., et al. Acoustic exaggeration of vowels in infant-directed speech: A multimethod meta-analytic review. *Psychological Bulletin*. https://doi.org/10.1037/bul0000479
*   Piazza, E. A., Iordan, M. C., & Lew-Williams, C. (2017). Mothers consistently alter their unique vocal fingerprints when communicating with infants. *Current Biology*.

**Emotion Contours & Dynamic Styles**
*   Fernald, A. (1989). Intonation and communicative intent in mothers' speech to infants: Is the melody the message? *Child Development*, 60(6), 1497-1510. *(The foundational paper on the 4 emotional contours: approval, prohibition, comfort, attention).*
*   Saint-Georges, C., et al. (2013). Motherese in interaction: At the cross-road of emotion and cognition? *PLOS ONE*.
*   Goupil, L., et al. (2024). Infant-directed communication: Examining the many dimensions of everyday caregiver-infant interactions. *Developmental Science*.

**Physical Interaction & "Motionese"**
*   Brand, R. J., Baldwin, D. A., & Ashburn, L. A. (2002). Evidence for 'motionese': modifications in mothers' infant-directed action. *Developmental Science*, 5(1), 72-83. *(Basis for mapping cursor velocity to behavioral triggers).*

**Writing It Down (Transcription vs. Simulation)**
*   MacWhinney, B. CHAT transcription format (TalkBank / CHILDES). https://reshare.ukdataservice.ac.uk/853329/22/CHAT_TranscriptionGuidelines.pdf
*   CHILDES / CLAN overview of child-directed speech transcripts. http://childes.psy.cmu.edu/

---

## 6. How AI speech is changing, and why it is hard to follow

Two different “AI speech” problems get mixed together: **voices** (TTS / voice assistants) and **wording** (LLM text that gets read out or read on a page). Both have moved toward sounding smoother and more human-like, while often getting **worse at the job IDS does**: slow down, highlight the new word, put stress in the right place, and leave room to think.

### The voice

Older TTS was robotic but sometimes *clear*. Newer neural TTS and vocoders sound more natural, but the pipeline is fragile:

- Acoustic models **oversmooth** features; vocoders trained on real speech then make muffled, metallic, or buzzy audio ([universal vocoder / smoothing mismatch](https://arxiv.org/html/2409.02517v1)).
- **Zero-shot** clone-any-voice systems swap in a new speaker embedding at test time, which often hurts **intelligibility** even when the voice “sounds like someone” ([Intelli-Z](https://arxiv.org/html/2401.13921)).
- Humans raise **vocal effort** in noise (Lombard speech). Most TTS does not, so it falls apart in cars, kitchens, and earbuds ([Raitio et al. on vocal effort in neural TTS](https://arxiv.org/html/2203.10637v2)). Some commercial voices *can* beat a human talker in noise via longer vowels and less spectral tilt — but that help often fails for **hearing-impaired** listeners ([MDPI study of Google/Amazon/Microsoft TTS](https://www.mdpi.com/2504-463X/5/1/5)).
- **Pitch bounce** makes synthetic speech sound more alive, but it can **cut word scores**. Flat pitch is easier to transcribe, less nice to hear ([Vojtech et al.](https://sites.bu.edu/stepplab/files/2019/07/Vojtechetal.pdf)). Naturalness vs clarity is a trade.
- **Wrong stress** (accent on the wrong word) makes agents feel fake even if the voice is human ([Fischer, Niebuhr, et al. on agent prosody](https://dl.acm.org/doi/10.1145/3486580)).
- **Faster rate** drops comprehension for native and non-native listeners ([TTS rate study](https://dl.acm.org/doi/abs/10.1016/j.csl.2007.03.001)). People already slow down when talking *to* Alexa; the machine often does not return the favor ([Cohn & Zellou Alexa-directed speech](https://www.frontiersin.org/journals/communication/articles/10.3389/fcomm.2021.675704/full); [Alexa/Polly lexical and rate study, 2025](https://www.frontiersin.org/journals/psychology/articles/10.3389/fpsyg.2025.1520111/full)).

Compared with IDS: caregivers expand vowels, pause, and repeat. Many AI voices do the opposite — average, smooth, and keep going.

### The words

Instruction-tuned LLMs lean **noun-heavy and information-dense**: extra nominalizations, extra `-ing` clauses, less of the loose, spoken style people actually use ([Reviriego / PNAS-style comparison of LLM vs human grammar](https://www.pnas.org/doi/10.1073/pnas.2422455122)). That packing is hard to parse in the ear, which has no rewind button.

Other documented habits that make “AI talk” tiring:

- Formulaic buzzwords and same-y polish ([Conversation on ChatGPT diction](https://theconversation.com/chatgpt-is-changing-the-way-we-write-heres-how-and-why-its-a-problem-239601); [corporate jargon + AI](https://www.raconteur.net/future-of-work/ai-could-make-corporate-jargon-everyones-problem))
- **Sycophancy**: agreeing with the user instead of being clear and true ([ICLR 2024 sycophancy paper](https://proceedings.iclr.cc/paper_files/paper/2024/file/0105f7972202c1d4fb817da9f21a9663-Paper-Conference.pdf))

### Why it *feels* harder “these days”

1. Voices got pretty, so listeners expect a person. Pretty + wrong stress + no effort-in-noise = brain works overtime.
2. Clone-anyone TTS optimized for **likeness**, not **phoneme clarity**.
3. Written AI style is dense and generic; when that style is spoken, there are no IDS-style repeats to catch the new word.
4. You hear it in worse rooms (phone speaker, commute) than the lab where MOS scores were collected.

This skill is the opposite bet: tiny utterances, named objects, repeats — the written cousin of IDS, not of neural TTS polish.

**Voice / TTS papers**

- Vojtech, J. M., et al. *The effects of modulating fundamental frequency and speech rate on the intelligibility, communication efficiency, and perceived naturalness of synthetic speech.* https://sites.bu.edu/stepplab/files/2019/07/Vojtechetal.pdf
- Raitio, T., et al. (2022). *Vocal effort modeling in neural TTS for improving the intelligibility of synthetic speech in noise.* https://arxiv.org/html/2203.10637v2
- Intelli-Z (2024). *Toward intelligible zero-shot TTS.* https://arxiv.org/html/2401.13921
- Universal vocoders and oversmoothing (2024). https://arxiv.org/html/2409.02517v1
- *The intelligibility benefits of modern computer-synthesized speech…* *Acoustics.* https://www.mdpi.com/2504-463X/5/1/5
- Fischer, K., Niebuhr, O., et al. *Do prosody and embodiment influence the perceived naturalness of conversational agents’ speech?* https://dl.acm.org/doi/10.1145/3486580
- Cohn, M., & Zellou, G. (2021). *Prosodic differences in human- and Alexa-directed speech…* https://www.frontiersin.org/journals/communication/articles/10.3389/fcomm.2021.675704/full
- *Factors modulating perception and production of speech by AI tools… Alexa and Polly* (2025). https://www.frontiersin.org/journals/psychology/articles/10.3389/fpsyg.2025.1520111/full

**LLM wording**

- *Do LLMs write like humans? Variation in grammatical and rhetorical styles.* *PNAS.* https://www.pnas.org/doi/10.1073/pnas.2422455122
- Sharma, M., et al. (2024). *Towards understanding sycophancy in language models.* ICLR. https://proceedings.iclr.cc/paper_files/paper/2024/file/0105f7972202c1d4fb817da9f21a9663-Paper-Conference.pdf
