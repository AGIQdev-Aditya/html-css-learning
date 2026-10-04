# 🧪 Day 07 Test & Viva Checkpoint

Time limit: **8 Minutes**  
Rules: Try to answer in your head before clicking **Reveal Answer**.

---

### Question 1 (College Exam Calculation — Box Model Width)
**Given the following CSS snippet:**
```css
.card {
  box-sizing: content-box;
  width: 250px;
  padding: 15px 25px; /* top/bottom: 15px, left/right: 25px */
  border: 4px solid black;
  margin: 20px;
}
```
**What is the exact visible rendered width of the card on the screen (excluding margins), and what is the total horizontal footprint occupied (including margins)?**

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
- **Visible Rendered Width:**  
  $$250\text{px (content)} + 25\text{px (left padding)} + 25\text{px (right padding)} + 4\text{px (left border)} + 4\text{px (right border)} = \mathbf{308\text{px}}.$$
- **Total Horizontal Footprint:**  
  $$308\text{px} + 20\text{px (left margin)} + 20\text{px (right margin)} = \mathbf{348\text{px}}.$$
- *Note:* If `box-sizing: border-box` were applied, the visible width would remain exactly **250px**.
</details>

---

### Question 2 (Viva Trap — Margin Collapsing)
**You have two vertically stacked `<div>` elements. Div A has `margin-bottom: 40px`, and Div B has `margin-top: 25px`. What is the actual rendered vertical gap between Div A and Div B? Does this same collapsing behavior occur between horizontal elements?**

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
- The rendered gap is **40px** (the larger of the two margins), **not 65px**. This phenomenon is called **vertical margin collapsing**.
- **No**, horizontal margins **never** collapse. If Box 1 has `margin-right: 40px` and Box 2 has `margin-left: 25px`, the horizontal distance will be strictly $$40 + 25 = 65\text{px}$$.
</details>

---

### Question 3 (Industry Best Practice)
**Why do modern web developers apply `*, *::before, *::after { box-sizing: border-box; }` at the very beginning of every CSS project?**

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
Because under the default `content-box`, adding padding or borders expands the physical footprint of elements, frequently breaking grid layouts, causing unexpected horizontal scrollbars, and requiring tedious mental math. `border-box` forces the browser to absorb padding and border inside the declared `width` and `height`, making all layout dimensions predictable.
</details>

---

### 🛠️ Practical Challenge (5 Minutes)
1. Open `Day_07/index.html` in your browser.
2. In `Day_07/style.css`, locate the `.box-content` class.
3. Change its padding from `24px` to `48px`. Notice how the box visibly balloons in size and shifts other content.
4. Now locate `.box-border` and increase its padding to `48px`. Notice how the box **remains exactly 320px wide**, simply compressing the inner text. That is the power of `border-box`!
