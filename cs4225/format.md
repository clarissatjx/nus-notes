# Notes Format Guide

All lecture notes are written as **A4 HTML files** using a consistent design system. When asked to make notes, produce a single `.html` file saved inside the relevant lecture folder (e.g. `4225 lectures/lecture 6/Lecture 6 NoSQL Notes.html`).

---

## File Structure

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Lecture N — Topic | CS4225/CS5425</title>
  <style> /* full CSS block — copy from template */ </style>
</head>
<body>
<div class="page">
  <!-- Header -->
  <!-- Sections 0, 1, 2, ... -->
</div>
</body>
</html>
```

---

## CSS — Copy This Exactly

```css
@import url('https://fonts.googleapis.com/css2?family=Source+Serif+4:ital,wght@0,300;0,400;0,600;1,400&family=JetBrains+Mono:wght@400;500&family=DM+Sans:wght@400;500;600&display=swap');

*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

:root {
  --teal:        #0F6E56;
  --teal-light:  #E1F5EE;
  --teal-mid:    #1D9E75;
  --purple:      #3C3489;
  --purple-light:#EEEDFE;
  --amber:       #854F0B;
  --amber-light: #FAEEDA;
  --blue:        #0C447C;
  --blue-light:  #E6F1FB;
  --coral:       #712B13;
  --coral-light: #FAECE7;
  --red-light:   #FCEBEB;
  --red:         #791F1F;
  --green-light: #EAF3DE;
  --green:       #27500A;
  --gray:        #444441;
  --gray-light:  #F1EFE8;
  --border:      #D3D1C7;
  --text:        #1a1a1a;
  --text-muted:  #5F5E5A;
  --font-body:   'DM Sans', sans-serif;
  --font-mono:   'JetBrains Mono', monospace;
}

html, body {
  background: #ffffff;
  color: var(--text);
  font-family: var(--font-body);
  font-size: 11pt;
  line-height: 1.65;
}

.page {
  width: 210mm;
  min-height: 297mm;
  margin: 0 auto;
  padding: 18mm 16mm 18mm 16mm;
}

.lecture-header { border-bottom: 2.5px solid var(--teal-mid); padding-bottom: 10px; margin-bottom: 22px; }
.lecture-title  { font-size: 20pt; font-weight: 600; color: var(--text); letter-spacing: -0.3px; }
.lecture-sub    { font-size: 9pt; color: var(--text-muted); margin-top: 3px; letter-spacing: 0.3px; }

.section       { margin-bottom: 20px; }
.section-title { font-size: 12pt; font-weight: 600; color: var(--text); display: flex; align-items: center; gap: 8px; margin-bottom: 9px; padding-bottom: 4px; border-bottom: 0.75px solid var(--border); }

.badge { font-size: 8pt; font-weight: 600; padding: 2px 9px; border-radius: 20px; letter-spacing: 0.2px; }
.bt { background: var(--teal-light);   color: var(--teal); }
.bp { background: var(--purple-light); color: var(--purple); }
.ba { background: var(--amber-light);  color: var(--amber); }
.bb { background: var(--blue-light);   color: var(--blue); }
.bc { background: var(--coral-light);  color: var(--coral); }

p    { font-size: 10.5pt; color: var(--text); line-height: 1.65; margin-bottom: 7px; }
code { font-family: var(--font-mono); font-size: 9pt; background: var(--gray-light); padding: 1px 5px; border-radius: 3px; color: var(--text); }

.grid2 { display: grid; grid-template-columns: 1fr 1fr;         gap: 8px; margin-bottom: 9px; }
.grid3 { display: grid; grid-template-columns: 1fr 1fr 1fr;     gap: 8px; margin-bottom: 9px; }
.grid4 { display: grid; grid-template-columns: 1fr 1fr 1fr 1fr; gap: 8px; margin-bottom: 9px; }

.card       { border: 0.75px solid var(--border); border-radius: 7px; padding: 9px 11px; background: #fff; }
.card-title { font-size: 9.5pt; font-weight: 600; color: var(--text); margin-bottom: 4px; }
.card-body  { font-size: 9.5pt; color: var(--text-muted); line-height: 1.55; }

.phase-row   { display: flex; align-items: stretch; gap: 0; margin-bottom: 10px; }
.phase-box   { flex: 1; border-radius: 7px; padding: 10px; text-align: center; }
.phase-arrow { display: flex; align-items: center; padding: 0 5px; color: var(--text-muted); font-size: 14pt; }
.phase-title { font-size: 10.5pt; font-weight: 600; margin-bottom: 3px; }
.phase-desc  { font-size: 8.5pt; line-height: 1.4; }
.ph-teal   { background: var(--teal-light); }   .ph-teal .phase-title   { color: var(--teal); }   .ph-teal .phase-desc   { color: #0F6E56; }
.ph-purple { background: var(--purple-light); } .ph-purple .phase-title { color: var(--purple); } .ph-purple .phase-desc { color: #534AB7; }
.ph-amber  { background: var(--amber-light); }  .ph-amber .phase-title  { color: var(--amber); }  .ph-amber .phase-desc  { color: #854F0B; }
.ph-blue   { background: var(--blue-light); }   .ph-blue .phase-title   { color: var(--blue); }   .ph-blue .phase-desc   { color: #0C447C; }
.ph-coral  { background: var(--coral-light); }  .ph-coral .phase-title  { color: var(--coral); }  .ph-coral .phase-desc  { color: #712B13; }

/* Highlight boxes */
.hl { border-left: 3px solid var(--teal-mid); background: var(--teal-light);  border-radius: 0 6px 6px 0; padding: 8px 11px; margin-bottom: 9px; font-size: 9.5pt; color: #085041; line-height: 1.55; }
.wl { border-left: 3px solid #EF9F27;         background: var(--amber-light); border-radius: 0 6px 6px 0; padding: 8px 11px; margin-bottom: 9px; font-size: 9.5pt; color: var(--amber); line-height: 1.55; }
.il { border-left: 3px solid #378ADD;         background: var(--blue-light);  border-radius: 0 6px 6px 0; padding: 8px 11px; margin-bottom: 9px; font-size: 9.5pt; color: var(--blue); line-height: 1.55; }
.rl { border-left: 3px solid #C74848;         background: var(--red-light);   border-radius: 0 6px 6px 0; padding: 8px 11px; margin-bottom: 9px; font-size: 9.5pt; color: var(--red); line-height: 1.55; }

.code-block { background: var(--gray-light); border: 0.75px solid var(--border); border-radius: 6px; padding: 9px 12px; font-family: var(--font-mono); font-size: 8.5pt; line-height: 1.6; white-space: pre; margin-bottom: 9px; color: var(--text); }

.step-item { display: flex; align-items: flex-start; gap: 9px; margin-bottom: 7px; font-size: 9.5pt; color: var(--text); line-height: 1.55; }
.step-num  { width: 20px; height: 20px; border-radius: 50%; background: #9FE1CB; color: #085041; display: flex; align-items: center; justify-content: center; font-size: 8.5pt; font-weight: 600; flex-shrink: 0; margin-top: 1px; }

.qa-block { margin-bottom: 9px; }
.qa-q { font-size: 9.5pt; font-weight: 600; color: var(--text); margin-bottom: 3px; }
.qa-a { font-size: 9.5pt; color: var(--text-muted); line-height: 1.55; padding-left: 10px; border-left: 2px solid var(--border); }

.tag { display: inline-block; font-size: 8pt; font-weight: 600; padding: 1px 7px; border-radius: 3px; margin-right: 3px; }
.tg { background: var(--green-light); color: var(--green); }
.tr { background: var(--red-light);   color: var(--red); }
.ta { background: var(--amber-light); color: var(--amber); }
.tb { background: var(--blue-light);  color: var(--blue); }

.cmp    { width: 100%; border-collapse: collapse; font-size: 9.5pt; margin-bottom: 9px; }
.cmp th { background: var(--gray-light); color: var(--text); font-weight: 600; padding: 6px 10px; text-align: left; border: 0.75px solid var(--border); }
.cmp td { padding: 5px 10px; border: 0.75px solid var(--border); color: var(--text-muted); vertical-align: top; line-height: 1.5; }
.cmp td strong { color: var(--text); }

.divider { border-top: 0.75px solid var(--border); margin: 14px 0; }

@media print {
  * { -webkit-print-color-adjust: exact; print-color-adjust: exact; }
  html, body { background: #fff; }
  .page { width: 100%; padding: 15mm 14mm; }
  .section { page-break-inside: avoid; }
  .card    { page-break-inside: avoid; }
  @page { size: A4; margin: 0; }
}
```

---

## Header

```html
<div class="lecture-header">
  <div class="lecture-title">Lecture N &mdash; Topic</div>
  <div class="lecture-sub">CS4225 / CS5425  &middot;  Big Data Systems for Data Science  &middot;  National University of Singapore</div>
</div>
```

---

## Section Structure

Every section follows this shell:

```html
<div class="section">
  <div class="section-title"><span class="badge bt">N</span> Section Title</div>
  <!-- content -->
</div>
```

Badge colours cycle roughly by topic type:

- `.bt` teal — introductory / "what is" sections
- `.bp` purple — implementation / mechanics
- `.ba` amber — concepts / theory
- `.bb` blue — examples / applications
- `.bc` coral — comparisons / exam sections

---

## Standard Section Order

Every set of notes should cover these sections in order:


| #    | Section                                                   | Badge             |
| ---- | --------------------------------------------------------- | ----------------- |
| 0    | Recap / context from previous lectures                    | `.bt`             |
| 1    | What is X? — plain-language definition + core insight box | `.bt`             |
| 2    | Why does X matter? — motivation, real-world problem       | `.bt`             |
| 3–N  | Core concepts, mechanics, worked examples                 | `.bp` `.ba` `.bb` |
| N+1  | Comparison table (if applicable, e.g. X vs Y)             | `.bc`             |
| N+2  | Exam-style Q&A                                            | `.bc`             |
| Last | Key Takeaways — numbered `.hl` box                        | `.bt`             |


---

## Components — When to Use Each

### Cards (`.card`) — inside a grid

Use for side-by-side comparisons, listing properties, or showing 2–4 parallel concepts.

```html
<div class="grid2">
  <div class="card">
    <div class="card-title">Title</div>
    <div class="card-body">Body text here.</div>
  </div>
  <div class="card"> ... </div>
</div>
```

Grid options: `.grid2` (2 cols), `.grid3` (3 cols), `.grid4` (4 cols).

---

### Phase Row — for sequential flows

Use for pipelines or processes with distinct stages (e.g. Map → Shuffle → Reduce).

```html
<div class="phase-row">
  <div class="phase-box ph-teal">
    <div class="phase-title">Stage 1</div>
    <div class="phase-desc">Description</div>
  </div>
  <div class="phase-arrow">&rarr;</div>
  <div class="phase-box ph-purple"> ... </div>
  <div class="phase-arrow">&rarr;</div>
  <div class="phase-box ph-amber"> ... </div>
</div>
```

Colours: `ph-teal`, `ph-purple`, `ph-amber`, `ph-blue`, `ph-coral`.

---

### Highlight Boxes — callouts

```html
<div class="hl">Green-teal — core insight, key definition, main takeaway</div>
<div class="wl">Amber — exam trap, warning, common mistake</div>
<div class="il">Blue — extra info, clarification, interesting detail</div>
<div class="rl">Red — danger / incorrect / what NOT to do</div>
```

---

### Numbered Steps — for ordered processes

```html
<div class="step-item"><span class="step-num">1</span><div>Step description here.</div></div>
<div class="step-item"><span class="step-num">2</span><div>Step description here.</div></div>
```

---

### Code Block — for pseudocode, signatures, examples

```html
<div class="code-block">map    (k1, v1)       → List(k2, v2)
reduce (k2, List(v2)) → List(k3, v3)</div>
```

For inline code snippets use `<code>like this</code>`.

#### Syntax token classes — colour-coding inside `.code-block`

Add these CSS classes to the `<style>` block (after the `.code-block` rule):

```css
/* Syntax token classes — use inside .code-block */
.kw { color: #3C3489; font-weight: 600; }   /* keyword (lambda, val, FROM, SELECT…) */
.st { color: #0F6E56; }                      /* string literal */
.cm { color: #8A8880; font-style: italic; }  /* comment (# … or // …) */
.nm { color: #854F0B; }                      /* number / numeric literal */
.fn { color: #0C447C; }                      /* function or method name */
```

Then wrap tokens inside the code block with `<span>` tags. The `white-space: pre` on `.code-block` is preserved because spans are inline and add no whitespace.


| Class | Colour            | Used for                                                                                                                                       |
| ----- | ----------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| `.kw` | Purple            | Language keywords: `lambda`, `val`, `case class`, `from`, `import`, `in`; SQL: `SELECT`, `FROM`, `GROUP BY`, `ORDER BY`, `LIMIT`, `DESC`, `AS` |
| `.st` | Teal              | String literals: `"hello"`, `"hdfs://..."`                                                                                                     |
| `.cm` | Muted gray italic | Comments: `# Python comment`, `// Scala comment`                                                                                               |
| `.nm` | Amber             | Numeric literals: `3`, `5`, `100`                                                                                                              |
| `.fn` | Blue              | Function/method names at call sites: `.map`, `.filter`, `.collect`, `len`                                                                      |


**Example — Python:**

```html
<div class="code-block">dataRDD = sc.<span class="fn">parallelize</span>([<span class="st">"Alice"</span>, <span class="st">"Bob"</span>], <span class="nm">3</span>)
nameLen = dataRDD.<span class="fn">map</span>(<span class="kw">lambda</span> s: <span class="fn">len</span>(s))  <span class="cm"># lazy — nothing runs yet</span>
nameLen.<span class="fn">collect</span>()</div>
```

**Example — SQL inside Python string:**

```html
<div class="code-block">spark.<span class="fn">sql</span>("""
    <span class="kw">SELECT</span> col, <span class="fn">sum</span>(count) <span class="kw">AS</span> total
    <span class="kw">FROM</span> tbl
    <span class="kw">GROUP BY</span> col
    <span class="kw">LIMIT</span> <span class="nm">5</span>
""")</div>
```

**Example — Scala:**

```html
<div class="code-block"><span class="cm">// Scala only</span>
<span class="kw">val</span> flights = df.<span class="fn">as</span>[Flight]  <span class="cm">// typed Dataset</span>
flights.<span class="fn">collect</span>()</div>
```

---

### Comparison Table (`.cmp`) — for X vs Y comparisons

```html
<table class="cmp">
  <tr><th>Dimension</th><th>Option A</th><th>Option B</th></tr>
  <tr><td><strong>Label</strong></td><td>A detail</td><td>B detail</td></tr>
</table>
```

---

### Q&A Block — exam-style questions at the end

```html
<div class="qa-block">
  <div class="qa-q">Q: Question text?</div>
  <div class="qa-a">Answer text.</div>
</div>
```

---

### Tags — inline labels

```html
<span class="tag tg">✓ Good / Pro</span>
<span class="tag tr">✗ Bad / Con</span>
<span class="tag ta">Warning</span>
<span class="tag tb">Info</span>
```

---

### Divider

```html
<div class="divider"></div>
```

---

### Supplementary section marker

Use when part of the lecture is supplementary / not examinable. Place between the last core section & Exam-style QNA, and the first supplementary section:

```html
<div style="display: flex; align-items: center; gap: 10px; margin: 22px 0 18px 0;">
  <div style="flex: 1; border-top: 1.5px solid #854F0B;"></div>
  <div style="background: var(--amber-light); border: 1px solid var(--amber); border-radius: 20px; padding: 3px 14px; font-size: 8.5pt; font-weight: 600; color: var(--amber); white-space: nowrap; letter-spacing: 0.3px;">SUPPLEMENTARY — Sections N onwards</div>
  <div style="flex: 1; border-top: 1.5px solid #854F0B;"></div>
</div>
```

---

## Custom Inline Diagrams

For architecture diagrams (e.g. MongoDB sharding), build them with inline `style=""` using the CSS variables. Keep boxes consistent with the colour scheme:

- Application nodes → `var(--purple-light)` / `var(--purple)` border
- Routing/middleware → `var(--teal-light)` / `var(--teal)` border
- Config/metadata → `var(--amber-light)` / `var(--amber)` border
- Data/storage nodes → `var(--blue-light)` / `var(--blue)` border

---

## Content Rules

- **Do not include a Section 0** that recaps the previous lecture(s).
- **"What is X"** sections always include a `.hl` box with the core insight in bold.
- **Worked examples** must be concrete — use real values, not placeholders.
- **Exam tips** go in `.wl` (amber warning) boxes, or in the dedicated Q&A section.
- Use `&mdash;` for em-dashes, `&rarr;` for arrows, `&middot;` for bullets in subheadings.

