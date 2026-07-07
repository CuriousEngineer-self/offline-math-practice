# Ganita Abhyasa — ಗಣಿತ ಅಭ್ಯಾಸ

**A standalone, offline-friendly, bilingual (English / ಕನ್ನಡ) math practice app for school students — one HTML file, zero installation.**

Built for classrooms with minimal infrastructure: all you need is a computer with a modern
web browser. No server, no internet connection (after the file is copied), no software to
install. Double-click `math_practice_v2.html` and start practising.

![Made for rural classrooms](https://img.shields.io/badge/made%20for-rural%20classrooms-green)
![Single file](https://img.shields.io/badge/deployment-single%20HTML%20file-blue)
![Languages](https://img.shields.io/badge/languages-English%20%7C%20%E0%B2%95%E0%B2%A8%E0%B3%8D%E0%B2%A8%E0%B2%A1-orange)

---

## Features

- **Eleven practice modules** across three groups:
  - **Arithmetic** — addition, subtraction, multiplication, division
  - **Fractions, Decimals & Percentages**
  - **Algebra & Geometry** — simple equations, simultaneous equations,
    quadratic equations, and area/volume problems
- **Adaptive difficulty** — five levels per module. Three correct answers in a row
  move the student up a level; two wrong answers in a row move them down.
  Levels are remembered **per student, per module** across sessions.
- **Bilingual interface and voice** — full UI and spoken feedback in English or
  Kannada, switchable on the start screen.
- **Audio feedback** — a celebratory chime and spoken praise
  (*"Ravi, this is correct! Well done!"* / *"ರವಿ, ಇದು ಸರಿಯಾಗಿದೆ! ಭೇಷ್!"*)
  for correct answers; a buzzer and the correct answer spoken aloud for wrong
  or timed-out answers. All sounds are synthesised in the browser
  (Web Audio API + Web Speech API) — no audio files needed.
- **Configurable timer** — seconds per question and questions per round are set
  on the start screen by the teacher.
- **Score recording** — every attempt is logged (timestamp, student, topic, level,
  problem, given answer, correct answer, result, time taken) and can be exported
  as a **CSV file** with one click.
- **Chalkboard UI** — large, friendly type on a classic blackboard, designed for
  children and for low-resolution screens.

## Quick start

1. Download `math_practice_v2.html` (or clone this repository).
2. Copy the file to the student's computer.
3. Double-click it — it opens in the default browser.
4. Choose the language, type the student's name, set the timer, and press **Start**.

That's it. Nothing else to install.

## Module details

| Module | Level 1 | … | Level 5 |
|---|---|---|---|
| Addition / Subtraction | 1-digit numbers | → | 5-digit numbers |
| Multiplication | 1-digit × 1-digit | → | 5-digit × 2-digit |
| Division | always exact (no remainders) | → | 5-digit quotients |
| Fractions | same-denominator ± | → | mixed ±×÷ with larger numbers |
| Decimals | 1-place addition | → | exact decimal division |
| Percentages | 10/25/50% of round numbers | → | reverse problems ("15% of a number is 45…") |
| Simple equations | x + 5 = 12 | → | 4(x + 3) = 36 |
| Simultaneous equations | small integer (x, y) | → | larger coefficients |
| Quadratic equations | positive integer roots | → | negative and larger roots |
| Geometry | rectangle/square area | → | cylinder, cone & sphere volumes |

Deliberate design choices, so young students are never blocked by mechanical issues:

- Subtraction results are never negative; division is always exact.
- Fraction answers are entered as numerator + denominator, and **any equivalent
  fraction is accepted** (checked exactly, by cross-multiplication).
- Decimal problems are constructed from scaled integers, so every answer is an
  exact 1- or 2-place decimal.
- Percentage problems are built backwards so answers are whole numbers.
- Circle/cylinder/cone/sphere problems say *"Use π = 22/7"* and use radii that are
  multiples of 7, so the answers are whole numbers.
- Quadratic equations are always factorable with integer roots, accepted in either order.

## Teacher configuration

Open the file in any text editor. Near the top of the `<script>` block:

```javascript
const CONFIG = {
  defaultTimerSeconds : 30,   // default time per question
  questionsPerRound   : 10,   // default questions per round
  levelUpStreak       : 3,    // correct-in-a-row needed to level up
  levelDownStreak     : 2,    // wrong-in-a-row that triggers level down
  maxLevel            : 5,
  minLevel            : 1,
  feedbackPauseMs     : 2800  // pause after each answer
};
```

All UI text lives in the `T` language pack and all spoken phrases in `SPEAK`,
both plain editable strings — corrections to the Kannada wording are very welcome
(see Contributing).

> **Tip:** 30 seconds suits arithmetic; for algebra, fractions and word problems,
> start a round with a longer timer (120–180 s).

## Scores and the CSV file

Browsers cannot silently write files to disk, so records are kept in the browser's
`localStorage` (they persist across sessions on that computer) and exported on
demand via **Download score sheet (CSV)**. The CSV opens directly in Excel /
LibreOffice / Google Sheets. Notes:

- Data is per browser, per computer. Students on different machines each keep
  their own records; collect the CSVs periodically.
- Clearing the browser's site data erases the stored records and levels.
- The CSV is UTF-8 with BOM, so Kannada text displays correctly in Excel.

## Text-to-speech notes

The app uses whatever voices the operating system / browser provides:

- **Windows + Edge** — recommended. English works out of the box, and Edge also
  exposes natural online Kannada voices to web pages.
- **Windows + Chrome** — English works; a Kannada voice is usually not available.
- **Linux** — most distros ship no speech engine; install one with
  `sudo apt install speech-dispatcher espeak-ng` and restart the browser.
- If no Kannada voice is found, the app **falls back to speaking English** rather
  than mangling Kannada text with an English voice. The chime/buzzer sounds work
  everywhere regardless.

## Privacy

Everything runs locally in the browser. No data is sent anywhere; the only
"database" is the browser's own local storage on the student's computer.

## Contributing

Issues and pull requests are welcome, especially:

- Corrections to Kannada phrasing (`T`, `SPEAK`, and `GEO_WORDS` blocks) —
  textbook wording from Kannada-medium teachers is especially valuable
- New problem generators or difficulty-curve tuning based on classroom experience
- Additional languages: add a new key alongside `en`/`kn` in the language packs

## Roadmap

- [ ] Per-topic timer defaults
- [ ] Optional central score collection over a local network (small Python server)
- [ ] More languages

## License

MIT — free to use, copy, and adapt for any classroom.
