# 🧪 Day 09 Test & Viva Checkpoint

Time limit: **8 Minutes**  
Rules: Try to answer in your head before clicking **Reveal Answer**.

---

### Question 1 (College Viva Trick Question — Axis Inversion)
**You set `flex-direction: column` on a flex container. Which property do you now use to center items horizontally across the screen: `justify-content` or `align-items`?**

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
**`align-items: center;`**  
- In column mode, the **Main Axis runs vertically** (top to bottom). Therefore, `justify-content` controls vertical alignment.
- The **Cross Axis runs horizontally** (left to right). Therefore, `align-items` controls horizontal alignment!
</details>

---

### Question 2 (Viva Trap — The `gap` Property)
**Why is the modern CSS `gap: 16px` property vastly superior to using `margin-right: 16px` on flex children?**

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
Using `margin-right: 16px` creates an unwanted ghost margin on the last item in the row, requiring messy cleanup code like `.item:last-child { margin-right: 0; }` or causing line breaks in responsive layouts.  
`gap` places spacing **strictly between adjacent items**, automatically ignoring outer container edges and handling wrapped lines cleanly.
</details>

---

### Question 3 (Frontend Engineering Formula)
**What does the shorthand CSS property `flex: 1;` actually configure behind the scenes?**

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
It expands to:
- `flex-grow: 1;` (Allow this item to grow and absorb leftover free space proportionally)
- `flex-shrink: 1;` (Allow this item to shrink if the container compresses)
- `flex-basis: 0%;` (Start measuring growth from 0 size instead of intrinsic text width)
</details>

---

### 🛠️ Practical Challenge (5 Minutes)
1. Open `Day_09/index.html` in your browser.
2. In `Day_09/style.css`, locate `.flex-navbar`.
3. Temporarily change `justify-content: space-between;` to `justify-content: space-around;` and refresh. Notice how brand and CTA now have margins on the extreme edges. Change it to `justify-content: space-evenly;` to see perfectly balanced mathematical spacing.
4. Add 2 more `<div class="flex-card">` items in `Day_09/index.html` under Section 3. Resize your browser window and watch how cleanly Flexbox reorganizes them into neat rows!

<details>
<summary>🔍 Reveal Practical Challenge Solution Code</summary>

```css
/* In Day_09/style.css line 17: */
.flex-navbar {
  display: flex;
  justify-content: space-evenly; /* Try space-between, space-around, and space-evenly */
  align-items: center;
}
```
```html
<!-- Additional cards in Day_09/index.html under .flex-cards-container: -->
<div class="flex-card">
  <h4>Module E: Thermal Dissipation</h4>
  <p>Inverter heat-sink thermocouple telemetry.</p>
  <span class="chip">Online</span>
</div>
<div class="flex-card">
  <h4>Module F: Throttle Position</h4>
  <p>Dual Hall-effect sensor angular voltage check.</p>
  <span class="chip">Online</span>
</div>
```
</details>
