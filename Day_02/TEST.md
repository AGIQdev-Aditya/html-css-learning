# 🧪 Day 02 Test & Viva Checkpoint

Time limit: **8 Minutes**  
Rules: Try to answer in your head before clicking **Reveal Answer**.

---

### Question 1 (College Exam Classic — File Paths)
**You are inside `Day_02/index.html`. You have an image located at `assets/circuit_specimen.svg` inside your current `Day_02/` folder. What is the correct relative path to put in `<img src="...">`?**

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
`./assets/circuit_specimen.svg` (or `assets/circuit_specimen.svg`)  
- `./` indicates the CURRENT directory (`Day_02/`).
- `/assets/circuit_specimen.svg` enters the `assets` folder and points to `circuit_specimen.svg`.
- *Contrast with parent directory:* If the image were one level above in the parent folder, you would use `../assets/...`. Writing `/assets/...` (with a leading slash) points to your Linux root `/` filesystem!
</details>

---

### Question 2 (Viva & Security Question)
**"When opening an external link with `target="_blank"`, what security attribute should you always add, and why?"**

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
`rel="noopener noreferrer"`  
Without `noopener`, the target page can execute JavaScript through `window.opener.location` and redirect your original tab to a phishing or malicious website (reverse tab-nabbing). `noopener` severs this connection.
</details>

---

### Question 3 (Media Mechanics)
**"Why does `<video autoplay>` fail to start automatically on Google Chrome and Safari unless `muted` is also specified?"**

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
Modern browsers have strict **Autoplay Policies** to protect user experience. Audio playback without explicit user consent is blocked. Adding the `muted` attribute (`<video autoplay muted>`) informs the browser that no sound will play, allowing the video to start automatically.
</details>

---

### 🛠️ Practical Challenge (5 Minutes)
1. Open `Day_02/index.html` in your browser.
2. In Exercise 1, click the SVG circuit board image — ensure it navigates to `./specimen_report.html` locally without needing internet!
3. Inside `specimen_report.html`, click the back link to return to `Day_02/index.html`.
4. Now add an anchor link in `Day_02/index.html` that jumps directly to `Day_01/index.html` using a relative path.

<details>
<summary>🔍 Reveal Practical Challenge Solution Code</summary>

```html
<!-- Relative path to climb up from Day_02 and enter Day_01: -->
<p>
  <a href="../Day_01/index.html">&larr; Return to Day 01 Lesson</a>
</p>
```
</details>
