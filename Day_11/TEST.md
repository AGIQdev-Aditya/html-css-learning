# 🧪 Day 11 Test & Viva Checkpoint

Time limit: **8 Minutes**  
Rules: Try to answer in your head before clicking **Reveal Answer**.

---

### Question 1 (College Viva Trap — The Hover Exit Snapping Bug)
**A student writes the following CSS to make a button expand smoothly:**
```css
.btn {
  background: blue;
}
.btn:hover {
  background: red;
  transition: background 0.3s ease;
}
```
**What visual bug occurs when the user moves their mouse away from the button?**

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
The button will transition smoothly to red upon hovering, **but will instantly snap back to blue without any transition when the mouse leaves!**  
*Why:* Because when the mouse leaves, the `:hover` pseudo-class no longer matches, so the `transition` property disappears.  
*Fix:* Always define `transition` on the **base selector** (`.btn`), so it animates smoothly both on entry AND exit.
</details>

---

### Question 2 (Browser Rendering Engine & Performance)
**Why does animating `transform: translateY(-5px)` achieve 60 frames per second, while animating `top: -5px` often causes browser lag and jank?**

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
- Changing `top` affects the document geometry, forcing the browser's CPU to recalculate positions of surrounding elements on the page (**Reflow/Relayout**), followed by repainting.
- `transform` does not change the physical space of the element; it is offloaded directly to the **GPU Compositor thread** as a GPU texture transformation, ensuring silky-smooth 60+ FPS animation.
</details>

---

### Question 3 (Modern CSS Glassmorphism)
**What two CSS properties must be paired together to achieve the frosted glass ("Glassmorphism") effect?**

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
1. A **semi-transparent background color** (e.g. `background: rgba(255, 255, 255, 0.05);`).
2. **`backdrop-filter: blur(12px);`** (which applies a gaussian blur to the content located behind the element).
</details>

---

### 🛠️ Practical Challenge (5 Minutes)
1. Open `Day_11/index.html` in your browser.
2. In `Day_11/style.css`, locate `.interactive-card:hover`.
3. Add a slight dynamic rotation alongside the translation:
   ```css
   transform: translateY(-8px) scale(1.02);
   ```
4. Hover over the cards and see how responsive and physical the UI feels!
