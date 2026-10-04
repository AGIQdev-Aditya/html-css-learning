# 🧪 Day 01 Test & Viva Checkpoint

Time limit: **8 Minutes**  
Rules: Try to answer in your head before clicking **Reveal Answer**.

---

### Question 1 (College Exam Classic)
**"Is `<!DOCTYPE html>` an HTML element? What happens if you forget to write it at the top of your document?"**

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
No, `<!DOCTYPE html>` is **not** an HTML tag/element. It is a document type declaration instruction to the web browser.  
If you omit it, modern browsers drop into **Quirks Mode** (emulating old 1990s Netscape/IE behavior), which breaks CSS box calculations and modern layouts. Writing `<!DOCTYPE html>` ensures the browser uses **HTML5 Standards Mode**.
</details>

---

### Question 2 (Viva Trap)
**"Your professor asks you: 'What is the semantic difference between `<strong>` and `<b>`, and why shouldn't you just use `<b>` for bold text?'"**

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
- `<b>` (Bold) is a **purely visual/presentational tag**. It only makes text visually thick without adding any meaning.
- `<strong>` is a **semantic tag**. It tells screen readers, accessibility tools, and search engines (SEO) that the content has **serious importance / urgency**. Screen readers pronounce `<strong>` with distinct acoustic emphasis.
- Modern web standards require separating *meaning* (HTML) from *visual appearance* (CSS).
</details>

---

### Question 3 (Code Analysis)
**Which of the following tags require closing tags?**
- A) `<br>`
- B) `<title>`
- C) `<hr>`
- D) `<meta>`

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
Only **B) `<title>`** requires a closing tag (`</title>`).  
`<br>`, `<hr>`, and `<meta>` are **Void (Empty) elements** in HTML5. They cannot hold child text or nested tags, so they do not have a closing tag.
</details>

---

### 🛠️ Practical Challenge (5 Minutes)
1. Open `Day_01/index.html` in your browser.
2. In Exercise 3, add a third paragraph containing an `<em>` phrase and a `<code>` inline tag.
3. Add a `<mark>` highlight tag around your college name ("NIAT ADYPU").
4. Save and refresh in Chromium to verify!

<details>
<summary>🔍 Reveal Practical Challenge Solution Code</summary>

```html
<p>
  Studying at <mark>NIAT — Ajeenkya DY Patil University</mark> in Pune. 
  Learning <em>first-principles web architecture</em> with Linux command <code>cat index.html</code>.
</p>
```
</details>
