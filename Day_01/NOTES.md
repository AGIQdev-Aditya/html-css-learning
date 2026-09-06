# 🌐 HTML Day 01 — Skeleton, Text Hierarchy & Semantics

## 1. The Anatomy of an HTML5 Document

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Day 01 — My First Web Page</title>
  </head>
  <body>
    <h1>Welcome to Web Engineering</h1>
    <p>This is the visible content of the page.</p>
  </body>
</html>
```

### Key Questions Professors Ask in Exams:
1. **What is `<!DOCTYPE html>`?**
   - It is a **document type declaration**, NOT an HTML tag.
   - It instructs the browser to render the page in modern **HTML5 standard mode** rather than legacy quirks mode.
2. **`<head>` vs `<body>`**:
   - `<head>`: Metadata, page title, character sets, stylesheet links (invisible to the user).
   - `<body>`: Everything rendered directly on screen (visible to the user).
3. **What is `<meta charset="UTF-8">`?**
   - Specifies character encoding. UTF-8 supports virtually all human languages, symbols, and emojis.
4. **What are Void / Empty elements?**
   - Tags that do not have closing tags and cannot contain content:
     - `<br>`: Line break.
     - `<hr>`: Horizontal thematic rule/divider line.

---

## 2. Headings & Paragraphs

### Headings (`<h1>` to `<h6>`)
- `<h1>`: Top-level heading. (Rule: Only **one** `<h1>` per page for clean SEO & document structure).
- `<h2>` to `<h6>`: Subheadings in decreasing hierarchical order.

### Paragraphs (`<p>`)
- Represents a block of text.
- Browsers automatically inject vertical margin (spacing) above and below `<p>`.

---

## 3. Formatting & Semantic Meaning (Exam Favorite)

| Visual Tag | Semantic Tag | Difference (Why It Matters) |
| :---: | :---: | :--- |
| `<b>` | `<strong>` | `<b>` only changes visual font-weight. `<strong>` indicates **high importance** to screen readers and search engines. |
| `<i>` | `<em>` | `<i>` only slants text (italics). `<em>` adds **emphasis / altered verbal stress**. |
| `<s>` | `<del>` | `<s>` is just strikethrough. `<del>` marks **deleted / retracted text**. |
| `<u>` | `<ins>` | `<u>` is underline. `<ins>` marks **inserted / newly added text**. |

---

## 4. Void / Self-Closing Tags
- `<br>`: Line break (moves text to the next line without creating paragraph spacing).
- `<hr>`: Horizontal rule (draws a separator line across the width of the container).
