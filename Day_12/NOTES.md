# 🚀 Capstone Day 12 — HTML5 Architecture & Production Wireframing

---

## 1. The Capstone Mission
Across Days 01–11, you learned every primitive of HTML5 and CSS3.  
Now, in Days 12, 13, and 14, you assemble everything into a **production-grade Developer Portfolio & Engineering Showcase**:
- **Day 12:** Build the semantic HTML5 architecture (accessibility, metadata, pure structure).
- **Day 13:** Craft the responsive CSS3 styling (Flexbox, Grid, dark obsidian theme, 60fps micro-interactions).
- **Day 14:** Production deployment to GitHub Pages, performance audit, and the **Master 10-Question College Viva Exam Simulation**.

---

## 2. Production HTML5 Architectural Principles

### A. Zero "Div-Soup"
A junior developer writes:
```html
<div class="nav"><div class="links">...</div></div>
<div class="main-stuff"><div class="card">...</div></div>
<div class="bottom">...</div>
```
A senior engineer writes:
```html
<header><nav aria-label="Primary Navigation">...</nav></header>
<main>
  <section id="hero">...</section>
  <section id="projects"><article>...</article></section>
</main>
<footer>...</footer>
```

### B. Accessibility (a11y) & SEO Essentials
1. **Meaningful Headings:** Exactly **one** `<h1>` tag on the page (your primary identity/headline). All subsections follow `<h2>`, with child cards using `<h3>`.
2. **`aria-label` & Landmarks:** Helps screen readers navigate quickly.
3. **Descriptive Links:** Never write `<a href="...">Click Here</a>`. Write `<a href="...">View NexcanAI Live Telemetry Demo</a>`.
4. **Form Labels:** Every single form `<input>` must be explicitly connected to a `<label>` using matching `id` and `for` attributes.

---

## 3. Wireframe Structure of Aditya's Portfolio
```text
+-------------------------------------------------------------+
| HEADER: [ADITYA AGNIHOTRI // ADYPU]   [Projects] [Skills] [Contact]
+-------------------------------------------------------------+
| HERO SECTION:                                               |
|   - 1st Year Engineering Student @ NIAT ADYPU, Pune         |
|   - Building Automotive Telemetry & Full-Stack Interfaces   |
|   - [View Projects Button] [Download CV]                    |
+-------------------------------------------------------------+
| SKILLS MATRIX (<section id="skills">):                      |
|   - Frontend Architecture (HTML5, Modern CSS3, Flexbox/Grid)|
|   - Systems & Backend (Python 3, CAN Bus Telemetry, Linux)  |
|   - Engineering Tools (Git, Arch/Omarchy Linux, Bash)       |
+-------------------------------------------------------------+
| FEATURED PROJECTS (<section id="projects">):                |
|   - Project 1: NexcanAI (Onboard Vehicle CAN Bus Assistant) |
|   - Project 2: HTML5/CSS3 Accelerated Mastery System        |
|   - Project 3: LoRa Telemetry Gateway Node                  |
+-------------------------------------------------------------+
| CONTACT & INQUIRY FORM (<section id="contact">):            |
|   - Validated semantic form for freelance & internships     |
+-------------------------------------------------------------+
| FOOTER: Copyright 2026 Aditya Agnihotri • ADYPU Lohegaon    |
+-------------------------------------------------------------+
```

---

## 🎓 College Exam & Viva Questions for Day 12
1. **"Why is having only one `<h1>` per page recommended for SEO and accessibility?"**
   - The `<h1>` represents the highest-level title of the entire document. Multiple `<h1>` tags confuse screen readers and dilute search engine ranking signals regarding the page's core topic.
2. **"What is the difference between `<section>` and `<article>`?"**
   - An `<article>` represents self-contained, independently distributable content (like a blog post, a product card, or a standalone project widget). A `<section>` is a thematic grouping of related content (like "About Me" or "Contact Us").
