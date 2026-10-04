# 🌐 HTML Day 03 — Lists & Complex Tables

---

## 1. HTML Lists (3 Types)

Lists organize related data. In college vivas, professors love asking about all 3 types (most students only know 2).

### 1. Unordered List (`<ul>`)
Used when sequence does NOT matter (bullet points by default):
```html
<ul>
  <li>Silicon Wafer</li>
  <li>Printed Circuit Board</li>
  <li>Turbine Blade</li>
</ul>
```

### 2. Ordered List (`<ol>`)
Used when sequence matters (numbered 1, 2, 3 by default):
```html
<!-- start="1" type="1" (can be 'A', 'a', 'I', 'i') -->
<ol type="1" start="1">
  <li>Power on optical sensor</li>
  <li>Calibrate telecentric lens</li>
  <li>Trigger camera capture</li>
</ol>
```

### 3. Description / Definition List (`<dl>`) — ⭐ Viva Favorite
Used for glossaries, key-value pairs, and metadata:
- `<dl>`: Description List container
- `<dt>`: Description Term (the key/word)
- `<dd>`: Description Details (the value/definition)

```html
<dl>
  <dt>AOI</dt>
  <dd>Automated Optical Inspection using machine vision.</dd>

  <dt>Tolerance</dt>
  <dd>The permissible limit of variation in physical dimensions.</dd>
</dl>
```

---

## 2. HTML Tables (The #1 College Lab Exam Topic)

Tables represent tabular (row and column) data. **Never use tables for page layouts** (use CSS Flexbox/Grid instead). Use tables only for data!

### Basic Table Anatomy
```html
<table border="1">
  <caption>Weekly Inspection Telemetry</caption>
  <thead>
    <tr>
      <th>Batch ID</th>
      <th>Component</th>
      <th>Verdict</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>BATCH-001</td>
      <td>QFP-48 SMT</td>
      <td>PASS</td>
    </tr>
    <tr>
      <td>BATCH-002</td>
      <td>Wafer 300mm</td>
      <td>SCRAP</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td colspan="2">Total Inspected</td>
      <td>2 Units</td>
    </tr>
  </tfoot>
</table>
```

### The Key Tags:
* `<table>`: Root table wrapper.
* `<caption>`: Official title / caption of the table (placed right after `<table>`).
* `<thead>`: Table header row group.
* `<tbody>`: Table body data group.
* `<tfoot>`: Table summary / totals footer group.
* `<tr>`: Table Row.
* `<th>`: Table Header cell (bold and centered by default, semantic header).
* `<td>`: Table Data cell (regular text, left-aligned by default).

---

## 3. The Exam Master Trap: `colspan` vs `rowspan`

In practical exams, professors give you a hand-drawn grid on paper and say: *"Write the HTML table for this with merged cells."*

### `colspan` (Horizontal Cell Merging)
Merges multiple **columns** in the same row:
```html
<!-- Merges 2 columns horizontally -->
<td colspan="2">Merged across 2 columns</td>
```
*Rule of thumb:* If you use `colspan="2"`, you must **delete 1 `<td>`** from that row so the column count matches!

### `rowspan` (Vertical Cell Merging)
Merges multiple **rows** down the same column:
```html
<!-- Merges 2 rows vertically down -->
<td rowspan="2">Merged down 2 rows</td>
```
*Rule of thumb:* If you use `rowspan="2"` in Row 1, you must **omit that `<td>` in Row 2**, because Row 1's cell stretches down into it!

---

## 🎓 College Exam & Viva Questions for Day 03
1. **"What is the difference between `<th>` and `<td>`?"**
   - `<th>` represents a header cell. Browsers render it bold and centered by default. Screen readers associate data cells with their respective `<th>` using the `scope="col"` or `scope="row"` attribute. `<td>` is regular table data.
2. **"Why should we use `<thead>`, `<tbody>`, and `<tfoot>` instead of just `<tr>` directly?"**
   - It allows browsers to print long multi-page tables while automatically repeating `<thead>` and `<tfoot>` on every printed page, and allows scrollable `<tbody>` with fixed headers.
