# Build a Calculator with HTML, CSS & JavaScript

The source code and lab practice for the CorePulse video **"Build a Calculator with HTML, CSS & JavaScript"**.

▶️ Watch the video: `https://youtube.com/@CorePulseOffical` *(replace with the video link once it's live)*

No frameworks, no libraries: three small files you can read in one sitting.

![A dark calculator with round keys and amber operator keys](preview.png)

## What's in this repo

| File | What it does |
| --- | --- |
| `index.html` | The structure: a display and 19 buttons. Each button says what it does with `data-op` or `data-action`. |
| `styles.css` | The look: CSS variables for colors, Grid for the keypad, round keys and a pressed effect. |
| `script.js` | The logic: one click listener, digit input, operators, equals, clear, ± and %. |
| `LABS.md` | Hands-on exercises to practise after watching. |

## Run it

1. Click **Code → Download ZIP** (or `git clone` this repo).
2. Open `index.html` in your browser. That's it.

Tip: in VS Code, the **Live Server** extension reloads the page every time you save, just like in the video.

## How it works, in four ideas

1. **Structure first.** The HTML is written before any styling. An `<output>` element holds the result.
2. **Data attributes describe behaviour.** `data-op="*"` tells the script what a key does, so the label can be `×` without breaking anything.
3. **Event delegation.** One listener on `.keys` handles every button through `e.target.closest('button')`.
4. **No `eval`.** A small lookup object does the math, divide by zero shows `Error`, and `toFixed(10)` cleans up floating-point noise, so `0.1 + 0.2` shows `0.3`.

## Practise

Open [LABS.md](LABS.md) and work through the labs in order. Each lab says what to build, gives hints, and tells you how to check that it works.

Built something cool? Share it in the video's comments.

## Follow CorePulse

Trading tech skills and updates. Subscribe on YouTube: **@CorePulseOffical**

## License

MIT. Use this code however you like, in your own projects too.
