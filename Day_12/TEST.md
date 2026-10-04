# 🧪 Day 12 Test & Viva Checkpoint

Time limit: **8 Minutes**  
Rules: Try to answer in your head before clicking **Reveal Answer**.

---

### Question 1 (College Exam Trap — Security & `target="_blank"`)
**When adding external links like `<a href="https://client-ruby-nine-87.vercel.app" target="_blank">`, why is it mandatory for security to include `rel="noopener noreferrer"`?**

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
Without `rel="noopener"`, the newly opened page gains access to your original page via the JavaScript `window.opener` object. A malicious site could execute `window.opener.location = "fake-phishing-login.com"` in the background without the user noticing (known as **Reverse Tabnabbing**). `rel="noopener"` severs this JavaScript connection completely.
</details>

---

### Question 2 (Accessibility & SEO Standards)
**Why should a web page strictly have only ONE `<h1>` tag in standard production markup?**

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
The `<h1>` tag communicates the single overarching theme and purpose of the entire document to both screen readers (for visually impaired users) and search engine web crawlers. Multiple `<h1>` tags create navigational ambiguity and dilute SEO ranking signals. All secondary sections must use `<h2>`, with subsections nesting under `<h3>`.
</details>

---

### Question 3 (HTML5 Semantic Landmarks)
**What is the functional difference between `<section>` and `<article>`?**

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
- **`<article>`:** Represents a completely self-contained, independent unit of content that could theoretically be lifted out and syndicated elsewhere on another website (e.g. a blog post, a project card, a product item).
- **`<section>`:** Represents a generic thematic grouping of content that belongs specifically to this page (e.g. an "About Me" section or "Contact Form" section).
</details>

---

### 🛠️ Practical Challenge (5 Minutes)
1. Open `Day_12/index.html` in your browser. Notice how cleanly readable and organized the page is even without CSS!
2. Open Chrome/Chromium DevTools (`F12`), switch to the **Lighthouse** tab, and run an **Accessibility & SEO Audit**.
3. Add a fourth course row to the academic table for Engineering Physics / Mathematics.

<details>
<summary>🔍 Reveal Practical Challenge Solution Code</summary>

```html
<!-- Inside <tbody> in Day_12/index.html: -->
<tr>
  <td><code>MA-101</code></td>
  <td>Engineering Mathematics I</td>
  <td>Calculus, linear algebra, and discrete matrix methods</td>
  <td>Active Core</td>
</tr>
```
</details>
