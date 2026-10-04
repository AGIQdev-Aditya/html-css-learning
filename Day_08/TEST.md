# 🧪 Day 08 Test & Viva Checkpoint

Time limit: **8 Minutes**  
Rules: Try to answer in your head before clicking **Reveal Answer**.

---

### Question 1 (College Exam Trap — Absolute Positioning Context)
**If a child `<span class="badge">` is given `position: absolute; top: 10px; right: 10px;`, but its parent `<div class="card">` has `position: static` (or no position defined), what does the badge align itself against?**

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
It travels up the DOM tree looking for the nearest ancestor with a non-static position (`relative`, `absolute`, or `fixed`). If none exists, it positions itself relative to the **initial containing block (the whole document/body)**!  
This is why the **Golden Pairing Pattern** is mandatory: Always set `position: relative` on the parent container if you want child elements positioned inside it.
</details>

---

### Question 2 (Viva Trap — `z-index` Failure)
**A developer writes `.overlay { z-index: 999999; }`, but the overlay stubbornly refuses to appear on top of other elements. What is the fundamental CSS reason for this failure?**

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
By default, HTML elements have `position: static`. In CSS specification, **`z-index` is completely ignored on static elements**.  
To fix this, the developer must set `position: relative;` (or `absolute`/`fixed`) alongside `z-index`.
</details>

---

### Question 3 (Viva Question — Fixed vs Sticky)
**What is the functional difference between `position: fixed` and `position: sticky` during page scroll?**

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
- **`position: fixed`:** Pulled entirely out of the document flow. Anchored directly to the browser viewport window; remains permanently visible in the exact same spot regardless of scrolling or parent containers.
- **`position: sticky`:** Starts in normal document flow like `relative`. When the user scrolls past its threshold (e.g., `top: 0`), it behaves like fixed, **BUT only within its parent container**. Once the parent container scrolls out of view, the sticky element scrolls away with it.
</details>

---

### 🛠️ Practical Challenge (5 Minutes)
1. Open `Day_08/index.html` in your browser.
2. In `Day_08/style.css`, locate `.box-1` (the blue box).
3. Change its `z-index` from `1` to `20`.
4. Refresh the page: Observe how the blue box instantly leaps to the very top layer, covering both the orange and green boxes!
5. In `.card`, temporarily comment out `position: relative;`. Refresh and observe where the red sale badge flies — it shoots straight to the top right corner of your whole browser window!
