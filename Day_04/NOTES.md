# 🌐 HTML Day 04 — Forms & User Input

---

## 1. The Anatomy of an HTML Form
Forms collect user input and transmit it to a backend server.

```html
<form action="/api/inspect" method="POST" enctype="multipart/form-data">
  <!-- Inputs go here -->
</form>
```

### The #1 Exam Question: GET vs POST Method
* **`method="GET"`:**
  - Form data is appended directly into the URL query string: `mysite.com/search?query=wafer`.
  - Visible in browser history & address bar (❌ **Never use for passwords or private data!**).
  - Has URL length limitations (~2048 characters).
  - Used for searches and data retrieval.
* **`method="POST"`:**
  - Form data is packaged inside the HTTP request body.
  - Invisible in the URL (✅ **Always use for passwords, logins, and file uploads!**).
  - No length limit.
  - Used for database modifications, registrations, and uploads.

---

## 2. Labels & The `for` Attribute (Accessibility Rule)

Never write an input without a `<label>`.

```html
<!-- The 'for' attribute MUST match the input's 'id' -->
<label for="user-email">Operator Work Email:</label>
<input type="email" id="user-email" name="operator_email" required>
```
*Why this matters:* Clicking the label text automatically focuses the cursor inside the input box (essential for mobile screens and accessibility).

---

## 3. Essential `<input>` Types

| Input Type | Usage / Behavior |
| :--- | :--- |
| `type="text"` | Generic single-line text (names, titles). |
| `type="email"` | Validates standard email format (checks for `@` and domain). |
| `type="password"` | Masks characters with dots/asterisks (`••••`). |
| `type="number"` | Only allows numeric digits; supports `min="0"` and `max="100"` and `step="0.05"`. |
| `type="range"` | Slider control for thresholds (e.g. `min="10" max="100"`). |
| `type="date"` | Opens the operating system's native calendar picker. |
| `type="file"` | Opens file picker (`accept="image/*"` restricts to images). |
| `type="checkbox"` | Multiple-choice options (can check more than one). |
| `type="radio"` | Single-choice options (**All radio inputs must share the SAME `name` attribute!**). |

---

## 4. Dropdowns (`<select>`) & Multi-Line Text (`<textarea>`)

```html
<!-- Dropdown Selector -->
<label for="defect-type">Defect Classification:</label>
<select id="defect-type" name="defect_type">
  <option value="" disabled selected>Select anomaly category...</option>
  <option value="solder_bridge">Solder Bridging</option>
  <option value="micro_crack">Micro-Crack Fracture</option>
  <option value="surface_burr">Surface Burr</option>
</select>

<!-- Multi-Line Textarea (Does NOT use a value attribute; content sits between tags) -->
<label for="operator-notes">Inspector Rework Notes:</label>
<textarea id="operator-notes" name="notes" rows="4" cols="50" placeholder="Describe corrective measures..."></textarea>
```

---

## 5. Built-in HTML5 Validations (No JS Required!)
* `required`: Prevents submission if the field is empty.
* `placeholder="example@co.com"`: Faint hint text shown when input is blank.
* `minlength="8"` and `maxlength="20"`: Character boundary restrictions.
* `pattern="[A-Z]{3}-[0-9]{4}"`: Regex validation (e.g., format like `BAT-2026`).

---

## 🎓 College Exam & Viva Questions for Day 04
1. **"What happens if two radio buttons have different `name` attributes?"**
   - The user can select both simultaneously, which breaks the radio functionality. Radio buttons must share the exact same `name` attribute so the browser knows they belong to the same mutual-exclusion group.
2. **"What attribute is required on a `<form>` when uploading files with `<input type='file'>`?"**
   - `enctype="multipart/form-data"` is mandatory. Without it, the browser only sends the filename as text rather than the actual file binary bytes.
