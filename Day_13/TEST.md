# 🧪 Day 13 Test & Viva Checkpoint

Time limit: **8 Minutes**  
Rules: Try to answer in your head before clicking **Reveal Answer**.

---

### Question 1 (College Exam Trap — Variable Fallbacks & `:root`)
**Why do professional developers declare design variables inside `:root` rather than on `body` or individual classes?**

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
- `:root` refers to the highest-level element in the document tree (`<html>`). Variables declared here are globally available to **every** element, pseudo-element (`::before`, `::after`), and SVG on the page.
- Declaring them on `body` means pseudo-elements attached to `html` or elements rendered outside normal flow might not inherit them properly.
</details>

---

### Question 2 (Viva Question — The Power of Design Tokens)
**What happens if you provide a fallback inside `var()` (e.g. `var(--accent-color, #c9b59c)`)? When does the fallback get used?**

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
If the variable `--accent-color` has not been defined anywhere in the cascade, the browser uses the fallback value `#c9b59c`. If `--accent-color` is defined, the fallback is completely ignored.
</details>

---

### Question 3 (Responsive Reflow & Table Overflow)
**Why is the academic table wrapped inside a `<div class="table-wrapper">` with `overflow-x: auto;` in `Day_13/style.css`?**

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
Standard HTML `<table>` elements refuse to wrap text past their minimum content width. On narrow mobile screens (375px), a wide table would burst through the screen boundary and cause an ugly horizontal page scroll. Wrapping it in an `overflow-x: auto` container creates an isolated horizontal swipe zone without breaking the rest of the page layout!
</details>

---

### 🛠️ Practical Challenge (5 Minutes — The 1-Second Theme Switch)
1. Open `Day_13/index.html` in your browser.
2. In `Day_13/style.css`, locate lines 8–9:
   ```css
   --accent-gold: #c9b59c;
   ```
3. Change `--accent-gold` to Neon Emerald:
   ```css
   --accent-gold: #10b981;
   ```
4. Save and refresh the browser. Observe how every single badge, button, link, hover state, and heading accent throughout the entire website immediately converts to vibrant green without touching a single other line of CSS! That is the architectural power of CSS Custom Properties!
