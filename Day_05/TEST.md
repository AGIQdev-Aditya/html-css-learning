# 🧪 Day 05 Test & Viva Checkpoint

Time limit: **8 Minutes**  
Rules: Try to answer in your head before clicking **Reveal Answer**.

---

### Question 1 (College Exam Classic — Block vs Inline)
**"Name 3 differences between block-level elements and inline elements."**

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
1. **Line Breaking:** Block elements always start on a new line; inline elements sit directly within the same line.
2. **Width Expansion:** Block elements expand horizontally to occupy 100% of their parent container's width; inline elements only take up the width of their inner content.
3. **Box Dimensions:** Block elements respect CSS `width`, `height`, and 4-sided `margin`/`padding`. Inline elements ignore `width`/`height` and ignore vertical `margin-top` and `margin-bottom`.
</details>

---

### Question 2 (Viva Question)
**"What is the difference between `<section>` and `<article>`?"**

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
- An **`<article>`** is a self-contained, independent composition that could theoretically be pulled out of the page and republished on RSS, a newsletter, or a different website and still make complete sense (e.g., a blog post, a tweet, a product card).
- A **`<section>`** is a generic thematic chapter or grouping of related content within a page, typically introduced with a heading (`<h2>`–`<h6>`).
</details>

---

### Question 3 (Document Architecture Rule)
**How many `<main>` tags are permitted in an HTML5 document?**
- A) As many as needed for each section.
- B) Exactly one.
- C) None; it is deprecated.

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
**B) Exactly one.**  
HTML5 specifications strictly state that a document must have only one visible `<main>` element, representing the primary content unique to that document.
</details>

---

### 🛠️ Practical Challenge (5 Minutes)
1. Open `Day_05/index.html` in your browser.
2. Open Chrome Developer Tools (`Ctrl + Shift + I` or Right Click → *Inspect*).
3. Hover over the `<header>`, `<main>`, `<section>`, and `<article>` tags in the Elements tree. Notice how each block element highlights across the entire screen width!
4. Notice how `<span>Gemini 3.8 Flash</span>` only highlights around those exact words because it is inline!
5. Celebrate: **Phase 1 (HTML5 Mastery) is officially COMPLETE!** 🎉
