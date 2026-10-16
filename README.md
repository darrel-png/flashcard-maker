# Flashcard Maker

A retro 80s neon-themed, self-contained HTML flashcard maker with intelligent distractor generation for multiple-choice tests.

## Features

- **Create** flashcards with term/definition pairs, organized by subject
- **Study** mode with flip cards, known/unknown tracking, and table view
- **Test** mode with multiple-choice questions and smart distractor generation
- **Import/Export** JSON, TXT, CSV, and PDF formats
- **Subject-based organization** — group, filter, and hide cards by subject
- **Edit** individual flashcards via modal dialog
- **Test history** — wrong answers are tracked and reused to enhance future distractors

## Intelligent Distractor Generation

The multiple-choice distractor generation uses two strategies:

1. **Reference knowledge base** — An embedded database of 545 flashcards across 6 library science subjects (Indexing, IKM, LMCYA, EdTech, MLIC, SADLIC) is used to generate distractors from the same domain. Distractors are scored by:
   - Word overlap with the correct answer
   - Question topic similarity
   - Type and category match
   - Length and structural similarity

2. **Type-based generation** — For subjects not in the reference base, distractors are generated based on the answer type:
   - Years → nearby years (±1, ±2, ±5, ±10)
   - Numbers → math variants (+1, −1, ×2, ÷2, squared, cubed)
   - Names → domain-relevant categories (authors, painters, composers, planets, etc.)
   - Chemical formulas → structural variants

## Test Settings

- 4 choices by default (25% guess probability)
- Subjects hidden during testing (no category elimination)
- Repeat wrong answers option
- Optional timer per question
- Random or fixed question direction

## Live Demo

**Try it online**: https://darrel-png.github.io/flashcard-maker/

Or run locally:
1. Open `flashcard-maker.html` in any modern browser

## Usage

1. Open `flashcard-maker.html` in any modern browser
2. Add flashcards manually or paste bulk data
3. Switch to the **Study** or **Test** tab
4. Import existing cards via the **Import/Export** tab

No server required — the app runs entirely client-side using localStorage.

## Development

To serve locally for testing:
```bash
python -m http.server 8103
```
Then open `http://localhost:8103/flashcard-maker.html`.

## License

MIT
