# 📘 Offline Master Reference & Viva Survival Manual
> **Student:** Aditya Agnihotri  
> **Institution:** 1st Year, NIAT — Ajeenkya DY Patil University (ADYPU), Pune  
> **Purpose:** 100% Offline Reference Manual — Zero Internet Required. Keep this open in VS Code while studying!

---

## 📑 TABLE OF CONTENTS
1. [HTML5 Tag & Attribute Cheat Sheet](#1-html5-tag--attribute-cheat-sheet)
2. [Void (Self-Closing) Elements](#2-void-self-closing-elements)
3. [CSS Selectors & Specificity Calculator](#3-css-selectors--specificity-calculator)
4. [The CSS Box Model Formula](#4-the-css-box-model-formula)
5. [Display Modes Comparison](#5-display-modes-comparison)
6. [CSS Positioning Mechanics](#6-css-positioning-mechanics)
7. [Flexbox Mental Model & Properties](#7-flexbox-mental-model--properties)
8. [CSS Grid Cheat Sheet](#8-css-grid-cheat-sheet)
9. [Responsive Breakpoints & Viewport Meta](#9-responsive-breakpoints--viewport-meta)
10. [Top 20 College Viva & Exam Definitions](#10-top-20-college-viva--exam-definitions)

---

## 1. HTML5 Tag & Attribute Cheat Sheet

### Essential Document Skeleton
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="Brief SEO summary of document">
  <title>Descriptive Window Title</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <!-- All user-visible elements live here -->
</body>
</html>
```

### Semantic Landmarks (Document Structure)
| Tag | Purpose & Semantic Meaning |
|---|---|
| `<header>` | Introductory container: holds logo, site headings, primary navigation. |
| `<nav>` | Navigation block containing primary link lists (`<ul><li><a>`). |
| `<main>` | The primary unique content of the page (**Only 1 per document**). |
| `<section>` | Thematic chapter/grouping of content, usually with a heading (`<h2>`). |
| `<article>` | Independent, self-contained syndicatable unit (blog post, card, product). |
| `<aside>` | Tangential/indirectly related content (sidebar, related links, quotes). |
| `<footer>` | Document or section footer: copyright, disclaimers, contact links. |

### Text & Formatting Elements
| Tag | Visual Appearance | Semantic Meaning (Exam Focus) |
|---|---|---|
| `<h1>`–`<h6>` | Heading scale (Largest to Smallest) | Document outline hierarchy. Only 1 `<h1>` per page. |
| `<p>` | Paragraph block | Block of continuous prose with default vertical margins. |
| `<strong>` | Bold | **High importance, seriousness, or urgency**. Screen readers inflect. |
| `<b>` | Bold | Pure visual bolding with zero semantic weight. |
| `<em>` | Italics | **Stressed emphasis**. Screen readers change vocal pitch. |
| `<i>` | Italics | Alternate voice, technical term, or foreign phrase without emphasis. |
| `<del>` | Strikethrough | Text that has been deleted or replaced. |
| `<ins>` | Underline | Text that has been newly inserted. |
| `<mark>` | Yellow highlight | Text highlighted for relevance or search hits. |
| `<code>` | Monospace | Inline computer code fragment. |
| `<pre>` | Monospace block | Preformatted text preserving literal spaces and line breaks. |

### Hyperlinks & Media
```html
<!-- Internal relative jump link -->
<a href="#section-id">Jump to Section</a>

<!-- Relative path to local file -->
<a href="./about.html">About Page</a>
<a href="../parent_page.html">Parent Folder Page</a>

<!-- External link with MANDATORY security attributes -->
<a href="https://example.com" target="_blank" rel="noopener noreferrer">Visit External</a>

<!-- Accessible Image -->
<img src="./assets/photo.jpg" alt="Thorough description for screen readers" width="400" loading="lazy">

<!-- Audio Player -->
<audio controls>
  <source src="./audio.mp3" type="audio/mpeg">
  Your browser does not support audio.
</audio>

<!-- Video Player -->
<video controls width="640" poster="./thumbnail.jpg">
  <source src="./video.mp4" type="video/mp4">
  Your browser does not support video.
</video>
```

### Forms & Validation Controls
```html
<form action="/submit" method="POST">
  <!-- Matching label for and input id is MANDATORY for accessibility! -->
  <label for="username">Username:</label>
  <input type="text" id="username" name="user" required minlength="3" placeholder="Enter username">

  <label for="user-email">Email:</label>
  <input type="email" id="user-email" name="email" required>

  <label for="user-password">Password:</label>
  <input type="password" id="user-password" name="pass" required minlength="8">

  <!-- Radio Group (Same 'name' attribute ensures single selection) -->
  <label><input type="radio" name="plan" value="free" checked> Free</label>
  <label><input type="radio" name="plan" value="pro"> Pro</label>

  <!-- Checkboxes (Multiple selection) -->
  <label><input type="checkbox" name="terms" required> Accept Terms</label>

  <!-- Dropdown -->
  <label for="country">Country:</label>
  <select id="country" name="country" required>
    <option value="" disabled selected>Choose...</option>
    <option value="in">India</option>
  </select>

  <!-- Multiline Text -->
  <label for="msg">Message:</label>
  <textarea id="msg" name="message" rows="4"></textarea>

  <!-- Buttons -->
  <button type="submit">Submit Form</button>
  <button type="reset">Reset Fields</button>
</form>
```

---

## 2. Void (Self-Closing) Elements
In HTML5, **void elements cannot have any content and cannot have closing tags**:
- `<br>` : Line break
- `<hr>` : Horizontal thematic divider line
- `<img>` : Image embed
- `<input>` : Form input control
- `<meta>` : Document metadata in `<head>`
- `<link>` : External resource link (e.g. stylesheet)
- `<source>` : Media source inside `<audio>` or `<video>`

---

## 3. CSS Selectors & Specificity Calculator

Specificity is calculated as a 4-part tuple: `(Inline, ID, Class, Element)`:

| Selector Type | Example | Specificity Value |
|---|---|---|
| **Inline Styles** | `<h1 style="color: red;">` | `1, 0, 0, 0` |
| **ID Selector** | `#header`, `#nav-btn` | `0, 1, 0, 0` |
| **Class, Attribute, Pseudo-class** | `.card`, `[type="text"]`, `:hover`, `:active` | `0, 0, 1, 0` |
| **Element Tag, Pseudo-element** | `div`, `p`, `h1`, `::before`, `::after` | `0, 0, 0, 1` |
| **Universal / Combinators** | `*`, `>`, `+`, `~` | `0, 0, 0, 0` |

### Combinator Relationships:
- `div p` : **Descendant selector** (any `<p>` inside `<div>`, no matter how deeply nested).
- `div > p` : **Direct child selector** (only `<p>` directly one level below `<div>`).
- `h1 + p` : **Adjacent sibling selector** (the `<p>` immediately following `<h1>`).
- `h1 ~ p` : **General sibling selector** (any `<p>` that shares the parent with `<h1>`).

---

## 4. The CSS Box Model Formula

### The Golden Reset (Place at the top of every CSS project):
```css
*, *::before, *::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
```

### Calculation Comparison:
Given: `width: 300px`, `padding: 20px`, `border: 5px`, `margin: 10px`:
- **Default `content-box`:**
  $$\text{Visible Box Width} = 300 + 20(\text{L}) + 20(\text{R}) + 5(\text{L}) + 5(\text{R}) = \mathbf{350\text{px}}$$
  $$\text{Total Footprint on Page} = 350 + 10(\text{L}) + 10(\text{R}) = \mathbf{370\text{px}}$$
- **Modern `border-box`:**
  $$\text{Visible Box Width} = \mathbf{300\text{px}} \quad (\text{Padding and border absorbed inside!})$$

### Vertical Margin Collapsing:
When vertical margins touch:
- `margin-bottom: 30px` on Box A + `margin-top: 20px` on Box B = **30px gap** (largest wins).
- **Horizontal margins NEVER collapse!**

---

## 5. Display Modes Comparison

| Value | Starts on New Line? | Respects `width` & `height`? | Respects Vertical Padding & Margins? |
|---|---|---|---|
| **`block`** | Yes (100% width) | Yes | Yes |
| **`inline`** | No (flows in text) | **NO (Ignored)** | **NO (Horizontal only)** |
| **`inline-block`** | No (sits side-by-side) | **Yes** | **Yes** |
| **`none`** | Removed from DOM flow (0px) | N/A | N/A |

---

## 6. CSS Positioning Mechanics

| Position | Participates in Flow? | Offsets Relative To... | Stays on Screen During Scroll? |
|---|---|---|---|
| **`static`** (default) | Yes | N/A (`top/left/z-index` ignored) | No |
| **`relative`** | Yes (holds spot) | Its own original position | No |
| **`absolute`** | **No (Pulled out)** | Nearest positioned ancestor | No |
| **`fixed`** | **No (Pulled out)** | Browser Viewport window | **YES (Always locked)** |
| **`sticky`** | Yes until threshold | Parent container boundary | **YES until parent scrolls out** |

### The Golden Anchor Pattern:
```css
.card-parent {
  position: relative; /* Anchor container */
}
.badge-child {
  position: absolute; /* Pinned corner element */
  top: 10px;
  right: 10px;
}
```

---

## 7. Flexbox Mental Model & Properties

Flexbox is **1-Dimensional** (Row OR Column).

```text
flex-direction: row (Default)
  Main Axis:  --------------------> (Controlled by justify-content)
  Cross Axis: |                     (Controlled by align-items)
              v
```

### Container Properties:
- `display: flex;` : Activates flex context.
- `flex-direction: row | column | row-reverse | column-reverse`
- `justify-content` (Aligns along **MAIN AXIS**):
  - `flex-start` | `center` | `flex-end` | `space-between` | `space-around` | `space-evenly`
- `align-items` (Aligns along **CROSS AXIS**):
  - `stretch` | `center` | `flex-start` | `flex-end` | `baseline`
- `gap: 16px;` : Clean gutter between items (replaces hacky margins).
- `flex-wrap: nowrap | wrap;`

### Perfect Centering in 3 Lines:
```css
.center-box {
  display: flex;
  justify-content: center;
  align-items: center;
}
```

### Flex Item Shorthand:
- `flex: 1;` -> Expands to `flex-grow: 1; flex-shrink: 1; flex-basis: 0%;`

---

## 8. CSS Grid Cheat Sheet

CSS Grid is **2-Dimensional** (Rows AND Columns simultaneously).

```css
.grid-container {
  display: grid;
  /* 3 Equal columns: */
  grid-template-columns: 1fr 1fr 1fr;
  /* Or with repeat: */
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
}

/* Magic Responsive Grid with ZERO Media Queries: */
.responsive-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 24px;
}

/* Span across multiple columns */
.featured-card {
  grid-column: span 2;
}
```

---

## 9. Responsive Breakpoints & Viewport Meta

### The Mandatory Viewport Tag:
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

### Standard Mobile-First Media Queries:
```css
/* Mobile styles are default (outside media queries) */
.col { width: 100%; }

/* Tablet & Desktop (Screen width 768px and up) */
@media (min-width: 768px) {
  .col { width: 50%; }
}

/* Wide Desktop (Screen width 1024px and up) */
@media (min-width: 1024px) {
  .col { width: 33.33%; }
}
```

---

## 10. Top 20 College Viva & Exam Definitions

1. **What is HTML?**  
   HyperText Markup Language — the standard declarative markup language used to structure web documents and content for web browsers.
2. **What is Quirks Mode?**  
   A backwards-compatibility emulation mode triggered when `<!DOCTYPE html>` is omitted, causing browsers to emulate 1990s Netscape/IE bugs.
3. **What is the DOM?**  
   Document Object Model — an in-memory, tree-structured programmatic representation of an HTML document created by the browser.
4. **Difference between `<div>` and `<span>`?**  
   `<div>` is a generic block-level container with no semantic meaning; `<span>` is a generic inline container used to style or target text fragments.
5. **What is CSS Specificity?**  
   A scoring algorithm browsers use to determine which CSS rule applies when multiple conflicting rules target the same element.
6. **Why use `box-sizing: border-box`?**  
   It includes padding and border within the declared width and height, preventing layout breakage and unwanted expansion.
7. **What is Vertical Margin Collapsing?**  
   When adjacent vertical margins meet, they merge into a single margin equal to the largest of the two margins rather than adding together.
8. **Explain `position: fixed` vs `sticky`?**  
   `fixed` locks an element to the viewport permanently; `sticky` acts relatively until a scroll threshold is hit, then locks to the viewport *only within its parent container*.
9. **Why does `z-index` fail on static elements?**  
   `z-index` specification only applies to positioned elements (`relative`, `absolute`, `fixed`, `sticky`). On `static`, it is ignored.
10. **Difference between `display: none` and `visibility: hidden`?**  
    `display: none` completely removes the element from document layout (takes 0px space); `visibility: hidden` hides content visually while preserving its empty physical footprint.
11. **Main Axis vs Cross Axis in Flexbox?**  
    The Main Axis is determined by `flex-direction` (row = horizontal, column = vertical). The Cross Axis is perpendicular (at 90 degrees) to the Main Axis.
12. **What does `justify-content` align?**  
    It aligns flex items along the **Main Axis** (whether horizontal or vertical).
13. **When to use Flexbox vs Grid?**  
    Flexbox for 1D content components (navbars, toolbars, buttons); Grid for 2D page layouts (dashboards, multi-column card matrices).
14. **What is an `fr` unit in CSS Grid?**  
    A fractional unit representing a fraction of the leftover free space in the grid container.
15. **Why animate `transform` instead of `top` or `margin`?**  
    `transform` is offloaded to the GPU Compositor thread (60fps smooth) without triggering browser CPU reflow/repaint; modifying `top` triggers layout reflow across the DOM.
16. **Why place `transition` on the base class instead of `:hover`?**  
    Defining transition on the base class ensures smooth animation both on hover entry AND on mouse leave.
17. **What does `rel="noopener noreferrer"` do?**  
    Prevents the newly opened tab from accessing `window.opener` on the parent window, defending against Reverse Tabnabbing attacks.
18. **Why should a page have only one `<h1>`?**  
    To provide a single unambiguous document title for search engine crawlers and screen readers.
19. **What is the difference between GET and POST?**  
    `GET` appends parameters to the URL query string (insecure for passwords, limited size); `POST` sends data inside the HTTP message body (secure, unlimited size).
20. **What is CSS `:root`?**  
    The pseudo-class matching the root element of the document tree (`<html>`), universally used to store global CSS custom properties (variables).
