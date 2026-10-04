# 🎨 CSS Day 06 — Selectors, Specificity & Typography

---

## 1. The 3 Ways to Attach CSS to HTML

In exams, professors ask: *"Explain the three ways of inserting style sheets."*

```html
<!-- 1. INLINE CSS (Highest priority, but messy — avoid in production) -->
<h1 style="color: #C9B59C; font-size: 24px;">Inline Title</h1>

<!-- 2. INTERNAL CSS (Sits inside <style> tags in the <head>) -->
<head>
  <style>
    h1 { color: #C9B59C; }
  </style>
</head>

<!-- 3. EXTERNAL CSS (Industry Standard — clean separation of concerns) -->
<head>
  <link rel="stylesheet" href="style.css">
</head>
```

---

## 2. CSS Selectors (The Building Blocks)

```css
/* 1. Element Selector (targets ALL <p> tags) */
p {
  color: #D9CFC7;
}

/* 2. Class Selector (targets elements with class="badge" — REUSABLE!) */
.badge {
  background-color: #16A34A;
}

/* 3. ID Selector (targets single element with id="main-nav" — UNIQUE!) */
#main-nav {
  background-color: #1C1815;
}

/* 4. Descendant Selector (any <p> inside a <article>, no matter how deep) */
article p {
  line-height: 1.6;
}

/* 5. Direct Child Selector (only immediate <li> children of <ul>) */
ul > li {
  list-style: none;
}

/* 6. Grouping Selector (applies same style to multiple tags) */
h1, h2, h3 {
  font-family: 'Space Grotesk', sans-serif;
}

/* 7. Pseudo-Classes (interactive states) */
.btn:hover {
  background-color: #C9B59C;
  color: #1C1815;
}
.btn:active {
  transform: scale(0.98);
}
input:focus {
  outline: 2px solid #C9B59C;
}
```

---

## 3. The College Exam Master Formula: CSS Specificity

When two CSS rules target the same element, **Specificity** decides which rule wins:

| Rank | Selector Type | Specificity Weight | Example |
| :---: | :--- | :---: | :--- |
| 1 | `!important` rule | Overrides all | `color: red !important;` |
| 2 | Inline style attribute | `1, 0, 0, 0` | `<h1 style="color: blue;">` |
| 3 | ID Selector | `0, 1, 0, 0` | `#header` |
| 4 | Class / Attribute / Pseudo-class | `0, 0, 1, 0` | `.card`, `[type="text"]`, `:hover` |
| 5 | Element tag | `0, 0, 0, 1` | `p`, `h1`, `div` |

### Specificity Calculation Example:
```css
div.card p#bio  /* 1 ID (0,1,0,0) + 1 Class (0,0,1,0) + 2 Elements (0,0,0,2) = 0, 1, 1, 2 */
.card .text     /* 2 Classes = 0, 0, 2, 0 */
```
The first rule (`0, 1, 1, 2`) beats the second rule because **1 ID outweighs any number of classes!**

---

## 4. Modern Color Systems & Typography

### Colors:
* **Hex:** `#1C1815` (Obsidian Ink), `#C9B59C` (Camel Gold).
* **RGB / RGBA:** `rgba(28, 24, 21, 0.85)` (The `A` stands for Alpha opacity: `0.0` invisible to `1.0` solid).
* **HSL:** `hsl(32, 28%, 70%)` (Hue, Saturation, Lightness).

### Typography:
```css
body {
  font-family: 'Inter', system-ui, -apple-system, sans-serif; /* Font stack with fallbacks */
  font-size: 16px;          /* Base browser size */
  font-weight: 500;         /* 400 = regular, 700 = bold */
  line-height: 1.6;         /* Space between lines (crucial for readability!) */
  letter-spacing: -0.02em;  /* Slight condensing for premium luxury headings */
}
```

---

## 🎓 College Exam & Viva Questions for Day 06
1. **"Can an element have multiple classes? Can it have multiple IDs?"**
   - An element can have **multiple classes** separated by spaces: `<div class="card dark shadow">`. However, an element can only have **one ID**, and that ID must be unique across the entire document.
2. **"Why should you avoid using `!important` in professional code?"**
   - It breaks the natural cascade of CSS and makes debugging impossible. If you need to override an `!important` rule later, you have to write another `!important` rule, leading to an "important war".
