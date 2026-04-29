# 🇳🇱 Dutch Vocab Builder

A single-file, offline-capable Dutch flashcard app using the SM-2 spaced repetition algorithm. Open `index.html` in any browser — no build step, no server required.

## How it works

Cards move through two phases:

| Phase | Mode | Mechanic |
|---|---|---|
| **Recognise** | Multiple choice | Pick the correct English meaning. Two consecutive correct answers promote the card to Produce phase. |
| **Produce** | Type the Dutch word | Type the Dutch word from the English prompt. SM-2 schedules the next review based on performance. |

Wrong answers are re-queued a few cards later in the same session. Progress is saved automatically to `localStorage` after every answer.

## SM-2 scheduling

- **Correct** → easiness factor grows; next review interval increases (1 → 4 → 6 → n × EF days)
- **Wrong** → interval resets to 1 day; lapse counter increments
- Cards with interval ≥ 21 days are counted as **mastered**

## Session structure

- Up to 15 new cards introduced per session
- New cards are interleaved with due reviews (2 reviews : 1 new)
- Sessions show accuracy % and a live progress bar (green = mastered, yellow = learning)

## Word list

~700 high-frequency Dutch words across verbs, nouns, adjectives, adverbs, colours, numbers, body parts, and family terms. Distractors in multiple-choice mode are drawn from the same semantic category where possible.

## Usage

1. Download or clone the repo
2. Open `index.html` in a browser
3. Study daily — the app tells you how many cards are due tomorrow

To reset all progress: scroll to the bottom and click **Reset all progress**.
