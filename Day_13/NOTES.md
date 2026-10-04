# 🎨 Capstone Day 13 — CSS3 Design System & Responsive Architecture

---

## 1. What Makes a "Senior-Grade" Stylesheet?
Amateur CSS relies on hardcoded hex codes scattered everywhere (`#fff`, `#222`, `#333`), random margin values (`margin: 17px`), and messy media queries.  
A production stylesheet uses:
1. **CSS Custom Properties (Variables):** Centralized design tokens for colors, spacing, and typography.
2. **Predictable Layout Scale:** Consistent grid tracks and flex gaps.
3. **Fluid Micro-Interactions:** Subtle GPU-accelerated elevation states.

---

## 2. CSS Custom Properties (Variables)
Variables allow you to change the entire color scheme or theme of a website from one central location:

```css
:root {
  /* Surface colors */
  --bg-dark: #0a0c10;
  --bg-surface: #12161f;
  --bg-card: #171b26;
  
  /* Accent colors */
  --accent-gold: #c9b59c;
  --accent-blue: #3b82f6;
  --accent-green: #10b981;
  
  /* Text tokens */
  --text-primary: #f0f3f6;
  --text-muted: #8b949e;
  
  /* Borders */
  --border-subtle: #1f2633;
  --border-highlight: #2f384a;
}

/* Usage in components */
.card {
  background-color: var(--bg-card);
  border: 1px solid var(--border-subtle);
  color: var(--text-primary);
}
```

---

## 3. Orchestrating Flexbox + Grid on the Same Page
A senior web developer does not choose between Flexbox and Grid — they orchestrate both:
- **Navigation Bar:** CSS Flexbox (`justify-content: space-between`).
- **Hero Actions:** CSS Flexbox (`gap: 16px; align-items: center`).
- **Project Catalog & Skills:** CSS Grid (`grid-template-columns: repeat(auto-fit, minmax(320px, 1fr))`).
- **Academic Table:** Pure CSS Table layout with styled `th`, `td`, and hover states.
- **Form Groups:** CSS Flexbox column flow.

---

## 4. Mobile Breakpoints Architecture
Instead of writing 10 different media queries, use a single clear standard breakpoint:
- **Desktop / Laptop (> 768px):** Multi-column grids, horizontal nav links.
- **Tablet / Mobile (≤ 768px):** Single-column stacks, full-width buttons, condensed padding.

---

## 🎓 College Exam & Viva Questions for Day 13
1. **"What is the difference between CSS Variables (`var(--name)`) and SASS variables?"**
   - CSS Variables are native, dynamic, and live in the browser DOM at runtime (can be changed live with JavaScript or media queries). SASS variables are compiled away into static values at build time and cannot react to DOM changes at runtime.
2. **"What is the `:root` pseudo-class in CSS?"**
   - `:root` represents the highest-level element in the document tree (identical to the `<html>` tag, but with higher specificity). It is the global standard location to define design tokens and CSS variables.
