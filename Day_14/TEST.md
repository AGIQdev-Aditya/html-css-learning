# 🎓 Master 10-Question College Viva Exam Simulation

> **Subject:** Web Technologies / Internet Programming Laboratory  
> **Target:** 1st Year Engineering Exam & External Viva (NIAT — ADYPU Pune)  
> **Instructions:** Try to answer each question out loud *before* clicking **Reveal Answer**.

---

### Question 1: The DOCTYPE & Quirks Mode
**Examiner:** *"What is `<!DOCTYPE html>`, is it an HTML tag, and what happens if you completely omit it from an HTML file?"*

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
- `<!DOCTYPE html>` is an **instruction / declaration to the web browser**, **NOT an HTML tag**.
- It tells the browser rendering engine that the document is written in modern **HTML5 standards mode**.
- If omitted, modern browsers revert to **"Quirks Mode"** (an emulation mode intended for backwards compatibility with 1990s Netscape Navigator and Internet Explorer 5). In Quirks Mode, CSS Box Model calculations break, modern layout rules misbehave, and rendering becomes unpredictable.
</details>

---

### Question 2: Semantic Markup vs Pure Formatting
**Examiner:** *"Why should modern web developers use `<strong>` and `<em>` instead of `<b>` and `<i>`?"*

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
- `<b>` and `<i>` are **purely visual formatting tags**; they make text bold or italic without conferring any semantic meaning.
- `<strong>` and `<em>` are **semantic tags**. `<strong>` signifies strong importance or seriousness, and `<em>` represents verbal emphasis.
- Crucially, **Screen Readers for visually impaired users alter their tone and inflection** when reading `<strong>` and `<em>`, whereas they treat `<b>` and `<i>` as plain uninflected text. Additionally, search engine web crawlers weigh semantic tags higher for SEO indexing.
</details>

---

### Question 3: The CSS Box Model Calculation
**Examiner:** *"An element has `width: 300px`, `padding: 20px`, `border: 5px solid black`, and `margin: 15px`. What is its visible rendered width on the screen under default `content-box` versus `border-box`?"*

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
- **Under default `content-box`:**  
  $$\text{Visible Width} = 300 + 20(\text{left pad}) + 20(\text{right pad}) + 5(\text{left border}) + 5(\text{right border}) = \mathbf{350\text{px}}.$$  
  *(Note: Margin is outside the visible box; total footprint including margin is $350 + 15 + 15 = 380\text{px}$).*
- **Under `box-sizing: border-box`:**  
  $$\text{Visible Width} = \mathbf{300\text{px}}.$$  
  The browser automatically shrinks the inner content area to $250\text{px}$ to accommodate the padding and border within the declared $300\text{px}$ width.
</details>

---

### Question 4: Vertical Margin Collapsing
**Examiner:** *"Two vertically adjacent block `<div>` elements have `margin-bottom: 30px` and `margin-top: 20px` respectively. What is the rendered vertical distance between them? Does this collapsing also happen horizontally?"*

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
- The rendered vertical distance is **30px** (the larger of the two margins), **not 50px**. This is known as **Vertical Margin Collapsing**.
- **No, horizontal margins NEVER collapse.** If two inline-block or floating elements have horizontal margins of $30\text{px}$ and $20\text{px}$, the rendered horizontal gap is strictly $50\text{px}$.
</details>

---

### Question 5: Relative vs Absolute Positioning
**Examiner:** *"How does `position: relative` differ from `position: absolute`, and what is the 'Golden Pairing Pattern'?"*

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
- **`position: relative`:** Retains its place in normal document flow. Offsets (`top`, `left`, etc.) shift it visually from where it normally would sit, without collapsing its original physical space.
- **`position: absolute`:** Removed completely from document flow (surrounding elements collapse into its former space). It positions itself relative to its **nearest positioned ancestor** (`relative`, `absolute`, or `fixed`).
- **The Golden Pairing Pattern:** Setting `position: relative` on a parent card and `position: absolute` on a child (such as a corner notification badge) anchors the child securely inside the parent container.
</details>

---

### Question 6: CSS Specificity Hierarchy
**Examiner:** *"Given the selector `#navbar ul.nav-menu li.active a`, how is CSS specificity calculated, and can 100 classes override 1 ID selector?"*

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
Specificity is calculated as a 4-part tuple `(Inline, ID, Class/Attribute/Pseudo-class, Element/Pseudo-element)`:
- In `#navbar ul.nav-menu li.active a`:
  - Inline styles = `0`
  - ID selectors (`#navbar`) = `1`
  - Class selectors (`.nav-menu`, `.active`) = `2`
  - Element tags (`ul`, `li`, `a`) = `3`
  - Total Specificity Score = `0, 1, 2, 3`.
- **No, 100 classes can NEVER override a single ID selector.** Specificity columns do not carry over or roll into higher ranks; an ID selector (`0, 1, 0, 0`) will always beat any number of classes (`0, 0, 100, 0`).
</details>

---

### Question 7: Flexbox Main Axis vs Cross Axis
**Examiner:** *"If a flex container is set to `flex-direction: column`, does `justify-content` align items horizontally or vertically?"*

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
**Vertically.**  
- `justify-content` ALWAYS aligns along the **Main Axis**.  
- When `flex-direction` is set to `column`, the Main Axis runs vertically from top to bottom.  
- To align items horizontally in column mode, you must use **`align-items`** (which aligns along the Cross Axis).
</details>

---

### Question 8: CSS Flexbox vs CSS Grid
**Examiner:** *"When should you choose Flexbox, and when should you choose CSS Grid?"*

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
- **Flexbox is 1-Dimensional** (Row *OR* Column) and **Content-First**. Use it for interface components where items align in a single direction — such as navigation bars, form button rows, search input groups, and tag lists.
- **CSS Grid is 2-Dimensional** (Rows *AND* Columns simultaneously) and **Layout-First**. Use it for page-level layouts, multi-column dashboard card matrices, photo galleries, and structured table-like alignments.
</details>

---

### Question 9: Mobile Viewport Meta Tag
**Examiner:** *"What is the exact purpose of `<meta name="viewport" content="width=device-width, initial-scale=1.0">`, and what happens if you forget it?"*

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
- It tells mobile browsers to set the width of the virtual viewport equal to the physical screen width of the device in CSS pixels (`width=device-width`), with an initial zoom level of 100% (`initial-scale=1.0`).
- If omitted, mobile browsers default to simulating a 1990s 980px desktop monitor. The entire page appears tiny and unreadable, and **all `@media` queries will fail to trigger properly**!
</details>

---

### Question 10: Anchor Security (`rel="noopener noreferrer"`)
**Examiner:** *"Why is it a critical security requirement to add `rel="noopener noreferrer"` whenever you use `target="_blank"` on external links?"*

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
- Without `rel="noopener"`, the newly opened page gains a JavaScript reference to the originating page via `window.opener`.
- A malicious target website can execute `window.opener.location = "https://phishing-login-page.com"`. While the user is looking at the new tab, their original tab is redirected to a fake login page in the background (known as **Reverse Tabnabbing**).
- `rel="noopener"` severs this reference completely, isolating the new tab.
</details>

---

### 🏆 Final Grade Criteria
- **10 / 10:** External Examiner Distinction (Top 1% of batch).
- **8 – 9 / 10:** Solid A+ (Exceeds university engineering standards).
- **< 8 / 10:** Review the respective daily notes in `Day_01` through `Day_13`.
