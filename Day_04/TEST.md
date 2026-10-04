# 🧪 Day 04 Test & Viva Checkpoint

Time limit: **8 Minutes**  
Rules: Try to answer in your head before clicking **Reveal Answer**.

---

### Question 1 (College Exam Classic — GET vs POST)
**"A college professor asks: 'Why is `method="GET"` dangerous for a login form, and what are 2 technical differences between GET and POST?'"**

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
1. **Security Vulnerability:** `GET` exposes submitted username and password directly in the browser address bar as plain text (`?user=aditya&pass=secret123`), saving credentials into browser history, proxy server logs, and shoulder-surfing view.
2. **Technical Differences:**
   - **Data Transmission:** `GET` sends data in the URL query string; `POST` transmits data in the hidden HTTP request body.
   - **Size Limits:** `GET` is limited to ~2048 characters (URL length restriction); `POST` has virtually no length limit (required for uploading files and images).
</details>

---

### Question 2 (Viva Trap)
**"What does the `<label for="abc">` attribute do, and what other attribute on the `<input>` must it match?"**

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
The `for` attribute binds the text label to an input. It MUST match the input's `id` attribute (`<input id="abc">`).  
When a user clicks on the label text, the browser automatically activates/focuses the corresponding input field, enlarging the clickable touch target for mobile devices and allowing screen readers to announce what the input field is for.
</details>

---

### Question 3 (Code Analysis)
**What happens if you omit the `type` attribute on a `<button>` inside a `<form>`?**
- A) It defaults to `type="button"` and does nothing.
- B) It defaults to `type="submit"` and submits the form.
- C) It throws an HTML validation error.

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
**B) It defaults to `type="submit"` and submits the form.**  
Inside a form, any `<button>` without an explicit `type` behaves as a submit trigger by default. To make a button that does NOT submit the form (e.g., toggling a password visibility eye icon), you must explicitly write `type="button"`.
</details>

---

### 🛠️ Practical Challenge (5 Minutes)
1. Open `Day_04/index.html` in your browser.
2. Try submitting the form with an empty name or invalid email — watch the browser's native validation popup stop you!
3. Add a new checkbox under section 2: `RoHS Environmental Compliance`.
4. Refresh and verify it toggles properly.

<details>
<summary>🔍 Reveal Practical Challenge Solution Code</summary>

```html
<!-- Inside fieldset 2: -->
<label>
  <input type="checkbox" name="certs" value="RoHS-Compliant"> RoHS 2011/65/EU Heavy Metal Directive
</label><br>
```
</details>
