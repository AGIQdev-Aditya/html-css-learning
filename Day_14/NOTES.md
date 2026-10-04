# 🎓 Day 14 — Production Deployment & College Viva Defense Guide

---

## 1. Hosting Your Work Live (Zero Cost)

Having a live public URL separates students who just talk about coding from engineers who ship real software.

### Method A: Deploying via GitHub Pages
1. Push your code to GitHub:
   ```bash
   git init
   git add .
   git commit -m "feat: complete 14-day HTML & CSS curriculum"
   git remote add origin https://github.com/your-username/aditya-portfolio.git
   git branch -M main
   git push -u origin main
   ```
2. In your GitHub repository:
   - Go to **Settings** → **Pages** (under Code and automation).
   - Under **Build and deployment** → Branch: select `main` → Folder: select `/ (root)` or your capstone folder.
   - Click **Save**.
   - Your site will be live at `https://your-username.github.io/aditya-portfolio/` in under 60 seconds!

### Method B: Deploying via Vercel (Instant CLI)
1. In your terminal:
   ```bash
   npx vercel
   ```
2. Follow the 3 prompts: Confirm directory, confirm project name, and hit Enter. Vercel automatically deploys with high-speed CDN edge caching.

---

## 2. The 100/100 Lighthouse Performance Audit
Before submitting your assignment to college professors or clients, run Google Lighthouse:
1. Open Chromium or Google Chrome.
2. Open DevTools (`Ctrl + Shift + I` or `F12`) → Click the **Lighthouse** tab.
3. Select **Desktop** or **Mobile** → Click **Analyze page load**.
4. Key metrics to check:
   - **Performance:** 95–100 (instant load, no uncompressed huge images).
   - **Accessibility:** 100 (proper contrast ratios, `aria-label` attributes, `<label for>` connected to `<input id>`).
   - **Best Practices:** 100 (HTTPS, modern doctype, `rel="noopener"` on external links).
   - **SEO:** 100 (`<meta name="description">`, `<title>`, `<h1>` hierarchy).

---

## 3. How College Professors Conduct Viva Examinations
In Indian university practical exams (ADYPU, SPPU, etc.), external examiners follow a predictable psychological pattern:
1. **The Warmup (Basics):** They check if you actually know what `<!DOCTYPE html>` does, or if you just memorized it.
2. **The Calculation Trap:** They give you numbers (e.g. `width: 200px, padding: 20px, border: 5px`) and ask you for the total width to see if you understand `box-sizing`.
3. **The Layout Battle:** They ask why someone would use CSS Grid instead of Flexbox, or how to center a div.
4. **The Security/Attributes Check:** They ask what happens when you use `target="_blank"` without `rel="noopener"`.

Mastering the 10 questions in `Day_14/TEST.md` guarantees you an `A+` in any practical lab viva!
