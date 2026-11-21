# Calculator labs

Practise what you learned in the video by extending the calculator. Do the labs in order: each one builds on the last.

Before you start, make a copy of the project (or a new git branch) so you can always compare with the original.

---

## Lab 1: Keyboard support

**Goal:** type numbers and operators on your keyboard instead of clicking.

**Hints**
- Listen for `keydown` on `document`.
- Map keys to buttons: `0`–`9` and `.` are digits, `+ - * /` are operators, `Enter` or `=` is equals, `Escape` is clear.
- Reuse the functions you already have: `inputDigit()`, `chooseOp()` and `actions.equals()`.

**Done when** you can type `12*7` then press Enter and see `84`.

---

## Lab 2: A backspace key

**Goal:** delete the last digit you typed.

**Hints**
- Add `actions.back()`, and a button with `data-action="back"` (or bind it to the Backspace key from Lab 1).
- Use `current.slice(0, -1)`. If nothing is left, set `current` back to `'0'`.

**Done when** typing `123`, then backspace twice, shows `1`.

---

## Lab 3: Start fresh after equals

**The bug:** do `60 × 5 =` to get `300`, then type `2`. The display shows `3002`. A real calculator starts a new number.

**Hints**
- Add a flag such as `let justSolved = false;`.
- Set it to `true` at the end of `compute()`, when it was called from equals.
- In `inputDigit()`, if `justSolved` is true, replace `current` instead of appending, then reset the flag.
- Typing an operator after a result should still continue from that result.

**Done when** `60 × 5 =` then `2` shows `2`, and `60 × 5 =` then `+ 1 =` shows `301`.

---

## Lab 4: Show the chosen operator

**Goal:** highlight the operator key that is waiting for the next number.

**Hints**
- In `chooseOp()`, add a class such as `active` to the pressed key, and remove it from the others.
- Remove it in `compute()` and in `actions.clear()`.
- Style `.active` in CSS, for example with a white outline.

**Done when** pressing `×` keeps `×` highlighted until you press `=` or `C`.

---

## Lab 5: A light theme

**Goal:** switch the whole calculator to a light look by changing only CSS variables.

**Hints**
- Move every hard-coded color (`#1a2338`, `#e6eaf2`, `#0f1420`) into `:root` variables first.
- Add a `.light` class on `<body>` that overrides those variables.
- Add a toggle button that runs `document.body.classList.toggle('light')`.
- Bonus: follow the system setting with `@media (prefers-color-scheme: light)`.

**Done when** one click swaps every color, and you didn't touch any rule except the variables.

---

## Lab 6: Long numbers

**The bug:** type a long number, or do `99999999 × 99999999 =`. The result runs out of the display.

**Hints**
- Limit input to about 12 digits in `inputDigit()`.
- For results, shrink the font when the text is long: set `display.style.fontSize` based on `value.length` inside `show()`.
- Or show very big and very small results with `Number(result).toExponential(6)`.

**Done when** no number ever spills outside the display.

---

## Challenge lab: History tape

**Goal:** show the last five calculations under the display, like `12 × 7 = 84`.

**Hints**
- Keep an array of strings and push one in `compute()`.
- Keep only the last five with `history.slice(-5)`.
- Render it into a `<ul>` below the display.
- Clicking a history line could load its result back into `current`.

---

## Stretch: Operator precedence

Right now `2 + 3 × 4` gives `20`, because the calculator works left to right, like most pocket calculators. Scientific calculators give `14`. Can you make it follow the order of operations? (Hint: keep a list of numbers and operators, and do `×` and `÷` before `+` and `−` when you press `=`.)

---

Stuck? Ask in the comments under the video on **@CorePulseOffical**.
