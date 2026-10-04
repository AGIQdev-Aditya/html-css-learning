# 🧪 Day 06 Test & Viva Checkpoint

Time limit: **8 Minutes**  
Rules: Try to answer in your head before clicking **Reveal Answer**.

---

### Question 1 (College Exam Calculation — Specificity Battle)
**Consider the following two CSS rules. Which color will the heading text turn?**
```html
<h1 id="page-title" class="title-heading">Inspection Studio</h1>
```
```css
#page-title {
  color: green;
}
h1.title-heading {
  color: red;
}
```

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
**Green.**  
- Rule 1 (`#page-title`) has an ID selector, giving it a specificity score of `0, 1, 0, 0`.
- Rule 2 (`h1.title-heading`) has 1 element tag + 1 class, giving it a specificity score of `0, 0, 1, 1`.
- Even though Rule 2 has 2 selectors, a single ID selector always beats any combination of classes and element tags!
</details>

---

### Question 2 (Viva Trap)
**"What does the `A` in `rgba(201, 181, 156, 0.4)` stand for, and what are its minimum and maximum values?"**

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
The `A` stands for **Alpha** (transparency/opacity channel).  
Its values range from `0.0` (100% fully transparent / invisible) to `1.0` (100% fully opaque / solid).
</details>

---

### Question 3 (Selector Trivia)
**What is the difference between `div p` and `div > p`?**

<details>
<summary>🔍 Reveal Answer</summary>

**Answer:**  
- `div p` is a **Descendant Selector**: It targets *any* `<p>` inside a `<div>`, regardless of how deeply nested it is (e.g., `<div><section><p>` is targeted).
- `div > p` is a **Direct Child Selector**: It *only* targets `<p>` elements that are direct, immediate children of the `<div>` (e.g., `<div><section><p>` would NOT be targeted).
</details>

---

### 🛠️ Practical Challenge (5 Minutes)
1. Open `Day_06/index.html` in your browser.
2. In `Day_06/style.css`, create a third badge class: `.badge-amber` with an orange-gold background (`rgba(217, 119, 6, 0.15)`) and text color `#D97706`.
3. Add a third card to `Day_06/index.html` using your new `.badge-amber`!
4. Refresh and observe how clean modern CSS classes make styling effortless!
