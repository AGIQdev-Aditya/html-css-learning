# 🌐 HTML Day 05 — Modern Semantic Architecture & Block vs. Inline

---

## 1. The Core Architectural Division: Block vs. Inline

In college vivas and technical interviews, professors ask: *"What is the difference between block-level and inline elements?"*

### Block-Level Elements
* Always **starts on a new line** (creates a line break before and after).
* Expands horizontally to take the **full available width** of its parent container (100% width).
* **Respects all dimensional styling:** Width, height, margin (top, right, bottom, left), and padding work properly.
* *Examples:* `<div>`, `<p>`, `<h1>`–`<h6>`, `<ul>`, `<ol>`, `<li>`, `<form>`, `<header>`, `<main>`, `<section>`, `<article>`.

### Inline Elements
* **Does NOT start on a new line;** sits inline with surrounding text.
* Takes up only as much width as its **inner text/content** requires.
* **Dimensional limitations in CSS:** Setting `width` or `height` has NO effect! Vertical `margin-top` and `margin-bottom` are ignored by browsers!
* *Examples:* `<span>`, `<a>`, `<strong>`, `<em>`, `<img>`, `<label>`, `<button>`, `<input>`.

---

## 2. Generic Containers: `<div>` vs `<span>`

When no semantic tag fits, we use generic division containers:
* **`<div>` (Division):** The generic **block-level** container. Used for layout grouping.
* **`<span>`:** The generic **inline** container. Used for styling a specific word or phrase inside a paragraph.

```html
<!-- Example: -->
<div class="stat-card"> <!-- BLOCK container -->
  <p>Defect rate: <span class="highlight-stat">0.05%</span></p> <!-- INLINE target -->
</div>
```

---

## 3. HTML5 Semantic Layout Landmarks (Death to "Div Soup")

In the early 2000s, websites were composed of hundreds of meaningless `<div id="header">`, `<div class="nav">`, `<div class="content">`. This is known as **"Div Soup"**.

HTML5 introduced meaningful **semantic landmarks**:

```
+-----------------------------------------------------------+
|                        <header>                           |
|       [Logo]                 <nav> [Home] [About]         |
+-----------------------------------------------------------+
|                                                           |
|                       <main>                              |
|   +-----------------------------------+   +-----------+   |
|   |            <section>              |   |  <aside>  |   |
|   |  +-----------------------------+  |   | (Sidebar) |   |
|   |  |         <article>           |  |   |           |   |
|   |  +-----------------------------+  |   | [Related] |   |
|   |  |         <article>           |  |   | [Links]   |   |
|   |  +-----------------------------+  |   |           |   |
|   +-----------------------------------+   +-----------+   |
|                                                           |
+-----------------------------------------------------------+
|                        <footer>                           |
|           [Copyright 2026] [Terms] [Privacy]              |
+-----------------------------------------------------------+
```

### The Landmark Roles:
1. **`<header>`:** Introductory banner, branding, top-level headings.
2. **`<nav>`:** Major navigation links (`<ul><li><a href="...">`).
3. **`<main>`:** The dominant, unique content of the page. *(Rule: A document must have only **one** `<main>` element).*
4. **`<section>`:** A thematic grouping of content (e.g., Features section, Testimonials section), typically introduced by a heading (`<h2>`).
5. **`<article>`:** A self-contained, independent composition that could be syndicated or shared on its own (e.g., a blog post, a defect report card, a product review).
6. **`<aside>`:** Content tangentially related to the main content (e.g., sidebars, callout boxes, related metrics).
7. **`<footer>`:** Trailing footer with copyright, privacy policies, author attribution.

---

## 🎓 College Exam & Viva Questions for Day 05
1. **"Can an `<article>` contain a `<section>`, or can a `<section>` contain an `<article>`?"**
   - Both are completely valid! A blog post (`<article>`) can have chapters (`<section>`). Similarly, a news section (`<section>`) can contain multiple news stories (`<article>`).
2. **"Can you place an `<h1>` inside an inline element like `<span>`?"**
   - Strictly invalid. Block elements cannot be nested inside inline elements (with the single exception of `<a>`, which HTML5 allows to wrap around block cards).
