# Number Line Playground — ಸಂಖ್ಯಾ ರೇಖೆಯ ಮೈದಾನ

**An animated, bilingual (English / ಕನ್ನಡ) introduction to what +, − and × really *mean* —
told on a number line with a rabbit, a frog, and a rotating arrow. One standalone HTML
file, no installation, no internet.**

Four lessons carry a single idea further and further: numbers are **positions** → then
**movements** → then **arrows** → then arrows that **rotate**. By the end, students can
*see* why minus × minus equals plus — and the curious ones get an optional peek at
imaginary numbers.

Part of a family of classroom tools alongside the
[Ganita Abhyasa practice app](./math_practice_v2.html) (drills),
[First Steps in Algebra](./algebra_intro.html) (algebra concepts), and
[Grama Vidya Bank](./bank_passbook.html) (applied arithmetic).

![Made for rural classrooms](https://img.shields.io/badge/made%20for-rural%20classrooms-green)
![Single file](https://img.shields.io/badge/deployment-single%20HTML%20file-blue)
![Languages](https://img.shields.io/badge/languages-English%20%7C%20%E0%B2%95%E0%B2%A8%E0%B3%8D%E0%B2%A8%E0%B2%A1-orange)

---

## The four lessons

Teach **in order, one lesson per session**. Each has an animated interactive stage, a
"💡 Big idea" summary, and a collapsible "📖 For the teacher" note.

### 1. Walking: + and − · ನಡಿಗೆ 🐇
The number line is a road; zero is home. A rabbit hops one step at a time (with a tick
sound and a dashed arc per hop). **Adding walks right. Subtracting means turning around
first.** That phrasing makes every sign case natural — including `3 − (−2)`:
*turn around twice, walk right.* Enter any sum with either sign and watch it happen.

> **Big idea:** negative numbers are simply places to the left of home — nothing scary.

### 2. Jumps: × · ಜಿಗಿತಗಳು 🐸
Multiplication is repeated jumping: in `3 × 4` the first number counts the jumps, the
second sets each jump's size and direction. A frog takes labelled, arcing jumps from
zero. Negative size → leftward jumps; negative *count* → "do the opposite."
`(−3) × (−4)` works here, but the tool honestly says it feels like a verbal trick — and
promises the real secret in Lesson 3.

> **Big idea:** × means repeated jumps; the signs set the direction.

### 3. The Turn: (−) × (−) · ತಿರುವು 🔄
The heart of the tool. A number becomes an **arrow from zero**. Multiplying by −1 does
not move the arrow — it **turns it half way around (180°)**, animated as a sweep through
the space above the line. For `(−3) × (−2)`: the arrow grows to +6, one minus sign turns
it half way, the second minus sign turns it home again. **Two half-turns = one full
turn = plus.** The rule becomes a picture.

> **Big idea:** every minus sign is a half-turn — that is why (−) × (−) = (+).

### 4. Quarter Turn ⭐ (optional bonus) · ಕಾಲು ತಿರುವು
If ×(−1) is a half-turn… is there a number that turns you a **quarter** turn? Doing it
twice must equal ×(−1) — so its square is −1. Mathematicians call it **i**, and it lives
*above* the number line. The stage becomes a plane with a dashed imaginary axis; two
buttons (**× i** and **× (−1)**) rotate the arrow. Two presses of × i take 3 to −3,
revealing *i² = −1*; four presses trace the full circle 3 → 3i → −3 → −3i → 3.

Clearly marked as a **wonder lesson, not syllabus** — for curious or older students
after Lesson 3 has fully landed. The only takeaway needed: *"there exists a number whose
square is −1, and it lives off the line."*

> **Big idea:** numbers do not just live on a line — they fill a whole plane.

## Why the rotation model?

"Minus times minus is plus" is usually taught as a rule to memorise. The rotation model
is not a trick — it is the mathematically standard picture: multiplying by −1 genuinely
*is* a 180° rotation about zero, and the same picture extends seamlessly to complex
numbers (i as the 90° rotation). Children who meet multiplication this way get the sign
rules for free, and a head start on mathematics they will meet years later.

## Quick start

1. Download `number_line.html` (or clone this repository).
2. Copy it to the classroom computer.
3. Double-click — it opens in the default browser.
4. Pick the language (top-right) and start with Lesson 1.

Best used teacher-led on a shared or projected screen. A lovely warm-up: draw a chalk
line on the classroom floor and let a student *be* the rabbit — physical first, animated
second.

## Technical notes

- Single HTML file: vanilla JavaScript + SVG animations, no frameworks, no assets.
- Sounds (hop ticks, whoosh for rotations, celebratory chime) are synthesised with the
  Web Audio API — no audio files.
- Works fully offline once copied; nothing is sent anywhere. The only stored data is the
  language preference (shared with the companion tools, so all open in the same language).
- Inputs are range-limited with friendly bilingual warnings so results always stay on
  the visible line.

## Languages

The English/ಕನ್ನಡ selector switches every label, explanation, and message. All
translatable text lives in one `S` language pack near the top of the `<script>` block as
plain editable strings. **Corrections from Kannada-medium teachers are very welcome.**
Teacher notes are intentionally English-only.

## Contributing

Issues and pull requests welcome, especially:

- Kannada phrasing corrections (the `S` block)
- New lesson ideas in the same spirit — e.g. division as sharing jumps, or fractions as
  positions between the ticks
- Additional languages: add a new key alongside `en`/`kn` in the language pack

## License

MIT — free to use, copy, and adapt for any classroom.
