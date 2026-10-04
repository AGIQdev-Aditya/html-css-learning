# 🧪 Day 03 Test & Viva Checkpoint

Time limit: **8 Minutes**  
Rules: Try to answer in your head before clicking **Reveal Answer**.

---

### Question 1 (Viva Question)
**"What is the semantic tag pair used for glossaries or metadata where you have a term and an explanation?"**

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
The `<dl>` (Description List) element, which contains pairs of `<dt>` (Description Term) and `<dd>` (Description Details / Description Definition).
</details>

---

### Question 2 (Exam Code Analysis)
**Look at this table row. How many total columns does this row occupy?**
```html
<tr>
  <td colspan="3">Summary Report</td>
  <td>25 Passed</td>
  <td>5 Failed</td>
</tr>
```

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
**5 columns.**  
The first `<td>` has `colspan="3"` (occupies 3 columns). Then there are 2 more regular `<td>` elements ($3 + 1 + 1 = 5$).
</details>

---

### Question 3 (Lab Viva Trap)
**"If you put `rowspan="3"` on the first `<td>` in Row 1, how many `<td>` elements must you omit in Row 2 and Row 3?"**

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
You must omit **1 `<td>` in Row 2** and **1 `<td>` in Row 3** at that specific column index, because the cell from Row 1 spans vertically downwards into both rows. If you don't omit them, the table will get pushed sideways and break the column grid alignment.
</details>

---

### 🛠️ Practical Challenge (5 Minutes)
1. Open `Day_03/index.html` in your browser.
2. In Exercise 3, add a third shift: `"Night (22:00 - 06:00)"` with 1 inspector and `PASS` status.
3. Update the `tfoot` total from `"3 Units"` to `"4 Units"`.
4. Refresh and make sure the table borders stay perfectly aligned!
