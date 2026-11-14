# HSK Flashcards 闪卡

A mobile-friendly Mandarin flashcard app for HSK 1–3, built for use alongside the *HSK Standard Course* and *Short-term Spoken Chinese* textbooks.

## Features

- **606 words** across HSK 1, 2 and 3, each with pinyin, English and an example sentence
- **Spaced repetition**: rate each card Again / Hard / Good / Easy; tricky words come back sooner
- **Four study modes**: 汉字 → English, English → 汉字, listening, and handwriting
- **Character writing practice** with stroke-order animation, tracing and from-memory quizzes
- **Lesson decks**: match words to *HSK Standard Course 3* lessons (Lesson 1 pre-filled)
- **Your own cards**: add single words or paste a whole lesson (`汉字 | pinyin | English`, tone numbers OK)
- **Daily goal and streak**
- Audio via the device's built-in Mandarin voice, tone colours, light/dark mode

## Files

| Path | What it is |
|---|---|
| `index.html` | The whole app: markup, styles, vocabulary data and logic |
| `hanzi-writer.min.js` | [Hanzi Writer](https://hanziwriter.org) 3.7.3 (MIT licence) for stroke animation and quizzes |
| `strokes/s0.json` … `s127.json` | Stroke data for ~9,500 characters, split into 128 shards loaded on demand |
| `strokes/LICENSE.txt` | Licence for the stroke data (Arphic Public License, from Make Me a Hanzi via hanzi-writer-data) |

## Running it

It's a static site, with no build step. Serve the folder with any web server, e.g.:

```
python3 -m http.server
```

then open http://localhost:8000. (Opening `index.html` directly from disk works, except for writing practice, which needs the stroke files served over http.)

## Saving progress

- In the hosted Claude version, progress syncs to each person's account.
- Anywhere else (e.g. GitHub Pages or locally), progress is saved in the browser only, so use the same device and browser each time.

## Editing the word lists

Vocabulary lives in `index.html` in `HSK1_RAW`, `HSK2_RAW` and `HSK3_RAW`, one word per line:

```
汉字|pin yin (space between syllables)|English|example sentence|example pinyin|example English
```
