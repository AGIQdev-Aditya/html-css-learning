# 🧪 Day 02 Test & Viva Checkpoint

Time limit: **8 Minutes**  
Rules: Try to answer in your head before clicking **Reveal Answer**.

---

### Question 1 (College Exam Classic — File Paths)
**You are inside `Day_02/index.html`. You have an image located at `assets/logo.png` in the parent directory (`HTML Learning/assets/logo.png`). What is the correct relative path to put in `<img src="...">`?**

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
`../assets/logo.png`  
- `..` moves you UP one folder from `Day_02/` into `HTML Learning/`.
- `/assets/logo.png` enters the `assets` folder and points to `logo.png`.
- *Common student mistake:* Writing `/assets/logo.png` (points to system root) or `./assets/logo.png` (looks inside `Day_02/assets/` which doesn't exist).
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
1. Open `Day_02/index.html` in VS Code or your editor.
2. In Exercise 2, click the circuit board image in your browser — ensure it opens the Unsplash webpage in a new tab without closing your own page!
3. In Exercise 4, test clicking the email link — does it open your default mail client with `aditya@nexcan.ai` pre-filled?
4. When finished, check off Day 02 in `README.md`!
