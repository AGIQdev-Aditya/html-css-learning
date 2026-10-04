# 🌐 HTML Day 02 — Hyperlinks, File Paths & Media

---

## 1. Hyperlinks (`<a>` Anchor Tag)
The link is the foundation of the entire World Wide Web (the "Hyper" in HTML).

```html
<a href="https://google.com" target="_blank" rel="noopener noreferrer">Visit Google</a>
```

### Key Attributes:
* **`href` (Hypertext Reference):** The destination URL.
* **`target="_blank"`:** Opens the link in a fresh browser tab.
* **`rel="noopener noreferrer"` (Security Best Practice):** 
  - Prevents the newly opened tab from accessing your original page through `window.opener` (blocks tab-nabbing phishing attacks).
* **Internal Anchor Jump:** Links to an ID on the same page:
  ```html
  <a href="#contact-section">Jump to Contact</a>
  <!-- jumps down to: -->
  <section id="contact-section">...</section>
  ```
* **Utility Links:**
  - Phone call: `<a href="tel:+919876543210">Call Support</a>`
  - Email: `<a href="mailto:aditya@example.com?subject=Inquiry">Send Email</a>`

---

## 2. The #1 Student Trap: Relative vs. Absolute File Paths

In college lab exams, 70% of students lose marks because their images or links break when moved to the professor's computer.

### Absolute Path
Points to a fixed external internet address or fixed root:
- `https://images.unsplash.com/photo-1` (Web URL)
- `/home/luca/Downloads/photo.jpg` ❌ **NEVER USE LOCAL OS PATHS IN HTML!** (Breaks on any other computer).

### Relative Path (Always use this!)
Points to files relative to the current file's directory:
* `./image.jpg` or `image.jpg`: File is in the **same folder**.
* `images/photo.jpg` or `./images/photo.jpg`: Go inside the `images` **subfolder**.
* `../index.html`: Go **UP one directory** (parent folder).
* `../../assets/logo.png`: Go **UP two directories**, then into `assets`.

---

## 3. Images (`<img>` Tag)

`<img>` is a **Void (self-closing) element** — it does not have an `</img>` closing tag.

```html
<img src="./assets/wafer.jpg" alt="Silicon wafer on calibrated cutting mat" width="600" height="400" loading="lazy">
```

### Attributes:
1. **`src` (Source):** The file path to the image.
2. **`alt` (Alternative Text) — CRITICAL FOR EXAMS & SEO:**
   - Text displayed if the image fails to load.
   - Read aloud by screen readers for visually impaired users.
   - Indexed by Google search crawlers.
3. **`width` & `height`:** Setting intrinsic dimensions prevents **Cumulative Layout Shift (CLS)** (prevents the page from awkwardly jumping while loading).
4. **`loading="lazy"`:** Browser only downloads the image when the user scrolls near it (improves page speed).

---

## 4. Modern Audio & Video (`<video>` & `<audio>`)

Gone are the days of Adobe Flash plugins. HTML5 has native media players.

```html
<!-- Native Video Player -->
<video controls width="640" poster="./thumbnail.jpg">
  <source src="./inspection_feed.mp4" type="video/mp4">
  <source src="./inspection_feed.webm" type="video/webm">
  Your browser does not support the video tag.
</video>
```

### Video Attributes:
* **`controls`:** Displays the play/pause, volume, and fullscreen bar.
* **`autoplay muted`:** Autoplays the video. *(Note: Browsers block autoplay unless `muted` is present!)*
* **`loop`:** Automatically restarts when finished.
* **`poster`:** An image thumbnail displayed before the video plays.

```html
<!-- Native Audio Player -->
<audio controls>
  <source src="./alert_chime.mp3" type="audio/mpeg">
  Your browser does not support the audio element.
</audio>
```

---

## 🎓 College Exam & Viva Questions for Day 02
1. **"What happens if you leave the `alt` attribute empty (`alt=""`) vs missing entirely?"**
   - *Missing:* Screen readers announce the ugly raw filename (e.g. `IMG_20261004_WA0023.jpg`), failing accessibility audits.
   - *Empty (`alt=""`):* Screen readers deliberately skip the image, treating it as purely decorative (valid for background icons).
2. **"Why do browsers require `muted` for `autoplay` to work?"**
   - To prevent annoying users with unexpected loud audio when loading a page.
