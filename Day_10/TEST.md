# 🧪 Day 10 Test & Viva Checkpoint

Time limit: **8 Minutes**  
Rules: Try to answer in your head before clicking **Reveal Answer**.

---

### Question 1 (College Exam Calculation — `fr` Units)
**You have a grid container of width `900px` with `gap: 0;`. You set `grid-template-columns: 1fr 2fr;`. What is the exact calculated width of each column?**

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
- Total fractions = $1\text{fr} + 2\text{fr} = 3\text{fr}$.  
- Value of $1\text{fr} = 900\text{px} / 3 = \mathbf{300\text{px}}$.  
- **Column 1:** $1\text{fr} = \mathbf{300\text{px}}$.  
- **Column 2:** $2\text{fr} = \mathbf{600\text{px}}$.
</details>

---

### Question 2 (Viva Trap — Breakpoint Failure)
**You wrote a media query `@media (max-width: 600px) { ... }`, but when testing on a physical iPhone or Android smartphone, the media query never triggers, and the site looks zoomed-out. What critical line of code did you forget?**

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
You forgot the **Viewport Meta Tag** in the `<head>`:  
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```  
Without this tag, mobile browsers assume a desktop viewport of 980px, zoom out, and fail to report actual device CSS pixel widths!
</details>

---

### Question 3 (Advanced Grid Trivia)
**How does `grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));` make a page responsive with ZERO media queries?**

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
- `minmax(280px, 1fr)` tells the browser: each column must be at least `280px` wide, but can stretch up to `1fr` to fill extra room.
- `auto-fit` tells the browser: calculate how many `280px` cards can fit in the container. If the screen has `900px` space, it fits 3 columns. If the screen shrinks to `500px`, it automatically wraps into 1 column!
</details>

---

### 🛠️ Practical Challenge (5 Minutes)
1. Open `Day_10/index.html` in your browser.
2. In `Day_10/style.css`, locate `.metrics-grid` on line 60.
3. Replace `grid-template-columns: repeat(3, 1fr);` with:
   ```css
   grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
   ```
4. Resize your window slowly and observe how each card dynamically reorganizes itself smoothly at any screen width!

<details>
<summary>🔍 Reveal Practical Challenge Explanation</summary>

```css
/* In Day_10/style.css: */
.metrics-grid {
  display: grid;
  /* Auto-fits as many 240px columns as fit on screen, zero media queries needed! */
  grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
  gap: 20px;
  margin-bottom: 32px;
}
```
</details>
