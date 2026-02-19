# Sentence-Builder
Sentence Building App For Learning English
# 🧩 Sentence Builder v5.1 – The Global Book Club

An interactive, browser-based English sentence-building game for ESL learners. Students tap words from a shuffled word bank to reconstruct correct English sentences, reinforced by instant audio playback, contextual grammar hints, streak rewards, and per-level progress tracking.

This app is part of **The Global Book Club** suite of English learning tools at [theglobalbookclub.com](https://www.theglobalbookclub.com/), and shares the same visual identity as the English Learning Hub.

---

## What's New in v5.1

| | v5.0 | v5.1 |
|---|---|---|
| **Total sentences** | 42 | **169** |
| 🌱 Basic | 15 | **51** |
| 🌿 Intermediate | 15 | **62** |
| 🌳 Advanced | 12 | **56** |
| Grammar structures covered | ~8 | **20+** |
| Unique hints | 42 | **169** |

With 169 sentences and smart no-repeat logic, a user completing 8–10 sentences per session will experience **over 16 sessions before any repetition** within a single level.

---

## Features

### Gameplay
- Tap words from the shuffled word bank to build a sentence in the drop zone
- Tap a placed word to remove it and try it in a different position
- The sentence is **checked automatically** the moment all words are placed
- **Multiple valid answers accepted** — sentences with flexible word order (e.g. fronted adverbs, inverted conditionals) accept all grammatically correct arrangements

### No-Repeat Logic
All sentences in a level are cycled through before any repeats occur. The used-index list resets only when the entire pool is exhausted, maximising freshness per session.

### Scoring
| Event | Points |
|---|---|
| Correct answer | +10 |
| Hint used | −2 per hint (minimum 5 awarded) |
| Streak of 3+ correct | +3 bonus |

Cumulative score persists between browser sessions via `localStorage`.

### Level Progress Bar
Stars fill as you accumulate points within each level:

| Threshold | Stars |
|---|---|
| 20 pts | ★☆☆ |
| 50 pts | ★★☆ |
| 100 pts | ★★★ |

### Hints
Each sentence has a unique contextual hint describing its grammar structure or meaning focus. The hint button disables after one use per sentence and costs 2 scoring points.

### Audio (Text-to-Speech)
- Correct sentences are spoken aloud automatically via the browser's `SpeechSynthesis` API
- Speech rate set to **0.82×** for clear, learner-friendly pacing
- **Listen Again** button replays the sentence on demand
- Supported in Chrome, Edge, Safari, and Firefox

### Game Modes
| Mode | Description |
|---|---|
| **Practice** | Untimed — move through sentences at your own pace |
| **Timer Mode** | 60-second countdown — score as many correct answers as possible |

---

## Difficulty Levels

### 🌱 Basic — 51 sentences

| Grammar Focus | Example |
|---|---|
| Simple present | *"She reads every day."* |
| To be / descriptions | *"The cat is small."* |
| Simple past | *"We watched a movie."* |
| Possession (have/has) | *"She has many books."* |
| Can / ability | *"He can swim well."* |
| Daily routines | *"He drinks coffee in the morning."* |
| Book & reading themed | *"I enjoy reading stories."* |

### 🌿 Intermediate — 62 sentences

| Grammar Focus | Example |
|---|---|
| Present perfect | *"I have finished my homework."* |
| Past continuous | *"She was reading when I called."* |
| Comparatives / superlatives | *"This book is better than the last one."* |
| Modal verbs | *"You should practice every day."* |
| Future (will / going to) | *"She is going to take an English course."* |
| Frequency adverbs | *"She rarely misses a class."* |
| Gerund phrases | *"She is interested in learning new things."* |
| Negatives | *"I do not understand this word."* |
| Book club & reading themed | *"Our book club meets every Wednesday."* |

### 🌳 Advanced — 56 sentences

| Grammar Focus | Example |
|---|---|
| 1st / 2nd / 3rd conditionals | *"If you practice daily you will improve quickly."* |
| Inverted conditionals | *"Were I to start again I would join a book club."* |
| Passive voice | *"The novel was written by a famous author."* |
| Relative clauses | *"The author whose work I admire most writes very simply."* |
| Participle phrases | *"Having read the chapter twice he felt more confident."* |
| Fronted inversion | *"Never before had I read such a moving story."* |
| Reported speech | *"She said that she had finished the whole novel."* |
| Cleft sentences | *"It was the story that made her fall in love with reading."* |
| Subjunctive mood | *"I suggest that she read at least one chapter a day."* |
| No sooner / so…that | *"No sooner had he opened the book than he was captivated."* |
| Philosophical / abstract | *"Language is not just a tool but a window into culture."* |

---

## Technical Notes

- **Pure HTML / CSS / JavaScript** — single self-contained file, zero dependencies, no server required
- **Works offline** — open directly in any modern browser by double-clicking the file
- **Mobile-responsive** — tested on phones and tablets; word chips wrap naturally on small screens
- **Score key** — `localStorage` key: `tgbc_score`
- **No-repeat key** — per-level arrays (`usedIndices`) reset automatically when the pool is exhausted

---

## Design System

Styled to match The Global Book Club's English Learning Hub:

| Element | Value |
|---|---|
| Background | Dark navy `#0f172a` |
| Cards | Slate `#1e293b` |
| Primary accent | Indigo `#6366f1` |
| Secondary accent | Violet `#8b5cf6` |
| Highlight accent | Pink `#ec4899` |
| Heading font | Quicksand (400 / 600 / 700) |
| Body font | Poppins (300 / 500 / 700) |
| Logo | Club logo embedded in header |
| Background animation | 3 floating translucent circles |

---

## Files

| File | Description |
|---|---|
| `TGBC_SentenceBuilder_v5.1.html` | Complete self-contained app — **current version** |
| `TGBC_SentenceBuilder_v5.html` | Previous version (42 sentences) |
| `README.md` | This file |

---

## How to Play

1. Open `TGBC_SentenceBuilder_v5.1.html` in any modern web browser
2. Choose a difficulty level from the dropdown
3. Click **Practice** or **Timer Mode** to begin
4. Tap words from the word bank to build your sentence
5. Tap a placed word to remove it and reposition it
6. The app checks your answer automatically when all words are placed
7. **Green border** = correct ✅ — **Red border** = try a different order ❌
8. Click **Next Sentence** to continue, or **Listen Again** to hear it spoken

---

## Adding More Sentences

Sentences are stored in the `SENTENCES` object in the `<script>` block. Each entry follows this structure:

```js
{ words: ["She", "reads", "every", "day"], answers: ["She reads every day."] }
```

For sentences with more than one valid word order, list all valid answers:

```js
{
  words: ["He", "usually", "cooks", "dinner"],
  answers: ["He usually cooks dinner.", "Usually he cooks dinner."]
}
```

Each sentence should have a matching hint string at the **same index** in the `HINTS` object:

```js
const HINTS = {
  easy: [
    "Describe a daily habit",   // ← index 0 matches SENTENCES.easy[0]
    "Talk about something you own",
    ...
  ]
}
```

> **Note:** If `HINTS[level]` is shorter than `SENTENCES[level]`, the app falls back to `"Think about the grammar!"` for any out-of-range index. Keep the arrays the same length for the best student experience.

---

## Session Freshness Reference

| Level | Sentences | At 8/session | At 12/session |
|---|---|---|---|
| 🌱 Basic | 51 | ~6 sessions before repeat | ~4 sessions |
| 🌿 Intermediate | 62 | ~7 sessions before repeat | ~5 sessions |
| 🌳 Advanced | 56 | ~7 sessions before repeat | ~4 sessions |

A student working across all three levels can enjoy **weeks of daily practice** without experiencing repetition fatigue.

---

## Part of The Global Book Club

This app is one of several learning tools at [theglobalbookclub.com](https://www.theglobalbookclub.com/):

- **Discussion Circles** — live group English conversation practice
- **Reading Workshops** — guided reading and comprehension sessions
- **Individual Lessons** *(coming soon)*
- **English Learning Hub** — vocabulary flashcards, quiz, and word library
- **Sentence Builder** — this app

---

*Built with ❤️ for Natalie and The Global Book Club.*
