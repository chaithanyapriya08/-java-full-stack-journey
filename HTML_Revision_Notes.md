# 📗 HTML — Complete Revision Notes

Detailed but exam/interview-ready notes. Organized so you can either read top-to-bottom to learn, or jump to a section for quick revision.

---

## 1. What is HTML?

HTML (HyperText Markup Language) is the standard markup language used to structure content on the web. It's not a programming language — it has no logic — it only defines structure and meaning of content using **tags** and **elements**.

- **Tag:** the markup itself, e.g. `<p>`
- **Element:** the tag + its content + closing tag, e.g. `<p>Hello</p>`
- **Attribute:** extra info added inside the opening tag, e.g. `<p class="intro">`

---

## 2. Basic Document Structure

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Page Title</title>
    <meta charset="UTF-8">
  </head>
  <body>
    <!-- visible content goes here -->
  </body>
</html>
```

| Part | Purpose |
|---|---|
| `<!DOCTYPE html>` | Tells the browser this is HTML5 |
| `<html>` | Root element of the page |
| `<head>` | Metadata — not shown on page (title, links, meta tags) |
| `<title>` | Text shown on the browser tab |
| `<body>` | Everything visible to the user |

---

## 3. Headings & Paragraphs

```html
<h1>Biggest heading</h1>
<h6>Smallest heading</h6>
<p>A paragraph of text.</p>
```
- Only **one `<h1>`** per page (best practice, also good for SEO)
- Headings should follow logical order (don't skip from h1 to h4)

---

## 4. Text Formatting Tags

| Tag | Meaning |
|---|---|
| `<b>` | Bold (visual only) |
| `<strong>` | Bold + semantically "important" |
| `<i>` | Italic (visual only) |
| `<em>` | Italic + semantically "emphasized" |
| `<u>` | Underline |
| `<mark>` | Highlighted text |
| `<small>` | Smaller text |
| `<sub>` / `<sup>` | Subscript / Superscript |
| `<del>` | Strikethrough (deleted text) |

**Interview tip:** `<b>` vs `<strong>` and `<i>` vs `<em>` — the first pair is purely visual, the second pair carries *meaning* for screen readers and SEO. Prefer `<strong>`/`<em>` in real projects.

---

## 5. HTML Entities

Used to display reserved/special characters.

```html
&lt;    →  <
&gt;    →  >
&amp;   →  &
&nbsp;  →  (non-breaking space)
&copy;  →  ©
&quot;  →  "
```

---

## 6. Links (Anchor Tag)

```html
<a href="https://google.com">Google</a>
<a href="https://google.com" target="_blank">New tab</a>
<a href="https://google.com" target="_self">Same tab (default)</a>
<a href="#section2">Jump to section on same page</a>
<a href="mailto:test@mail.com">Email link</a>
<a href="resume.pdf" download>Download file</a>
```

| Attribute | Purpose |
|---|---|
| `href` | Destination URL |
| `target="_blank"` | Opens the link in a **new tab/window** |
| `target="_self"` | Opens the link in the **same tab** (this is the default — you don't need to write it, but it's useful to know it exists) |
| `download` | Instead of navigating to the link, it **downloads the file** to the user's device. Can also give it a custom filename: `<a href="resume.pdf" download="MyResume.pdf">Download</a>` |
| `title` | Tooltip text on hover |

---

## 7. Navigation

```html
<nav>
  <a href="#">Home</a>
  <a href="#">About</a>
  <a href="#">Contact</a>
</nav>
```
`<nav>` is a **semantic tag** — it doesn't look different from a `<div>` but tells browsers/screen readers "this is navigation."

---

## 8. Lists

```html
<ul>                 <!-- unordered: bullets -->
  <li>Item</li>
</ul>

<ol>                 <!-- ordered: numbers -->
  <li>Item</li>
</ol>

<dl>                  <!-- description list -->
  <dt>Term</dt>
  <dd>Definition</dd>
</dl>
```
Lists can be **nested** — a `<ul>` or `<ol>` inside an `<li>`.

---

## 9. Images

```html
<img src="cat.jpg" alt="A cute cat" width="200" height="150">
```
| Attribute | Purpose |
|---|---|
| `src` | Image file path/URL |
| `alt` | Text shown if image fails to load; used by screen readers (accessibility) |
| `width` / `height` | Size in pixels |

`<img>` is a **self-closing/void element** — no closing tag needed.

---

## 10. Tables

```html
<table border="1">
  <tr>
    <th>Name</th>
    <th>Age</th>
  </tr>
  <tr>
    <td>Priya</td>
    <td>22</td>
  </tr>
</table>
```
| Tag | Meaning |
|---|---|
| `<table>` | Table container |
| `<tr>` | Table row |
| `<th>` | Header cell (bold, centered by default) |
| `<td>` | Data cell |
| `colspan` / `rowspan` | Merge cells across columns/rows |

---

## 11. Forms

```html
<form action="/submit" method="POST">
  <label for="name">Name:</label>
  <input type="text" id="name" name="name">

  <label for="email">Email:</label>
  <input type="email" id="email" name="email">

  <input type="submit" value="Submit">
</form>
```

**Common input types:**
`text`, `email`, `password`, `number`, `checkbox`, `radio`, `date`, `file`, `submit`

| Attribute | Purpose |
|---|---|
| `action` | Where form data is sent |
| `method` | `GET` (visible in URL) or `POST` (hidden, used for sensitive data) |
| `for` (on label) | Links label to input's `id`, so clicking label focuses the input |

---

## 12. Media (Audio/Video)

```html
<audio controls>
  <source src="song.mp3" type="audio/mpeg">
</audio>

<video controls width="300">
  <source src="movie.mp4" type="video/mp4">
</video>
```

---

## 13. iframe

```html
<iframe src="https://example.com" width="300" height="200"></iframe>
```
Embeds another web page inside the current page (e.g. embedding a YouTube video or Google Map).

---

## 14. Semantic HTML (important for interviews!)

Semantic tags describe their *meaning*, not just their appearance — improves accessibility, SEO, and code readability.

| Tag | Meaning |
|---|---|
| `<header>` | Top section of page/section |
| `<nav>` | Navigation links |
| `<main>` | Main content of the page |
| `<section>` | A thematic grouping of content |
| `<article>` | Self-contained content (blog post, news item) |
| `<aside>` | Side content (like a sidebar) |
| `<footer>` | Bottom section |

**Why it matters:** Using `<div>` for everything works visually, but semantic tags help screen readers, SEO crawlers, and other developers understand your page structure at a glance.

---

## 15. Deprecated / Legacy Tags (avoid these)

| Old Tag | Modern Replacement |
|---|---|
| `<marquee>` | CSS animations |
| `<font>` | CSS `font-family`, `color` |
| `<center>` | CSS `text-align: center` |
| `<b>`/`<i>` for emphasis | `<strong>`/`<em>` |

---

## 16. Common Interview Questions (quick answers)

**Q: What's the difference between HTML elements and tags?**
A tag is the markup (`<p>`); an element is the tag + content + closing tag (`<p>text</p>`).

**Q: What are void/self-closing elements?**
Elements with no content or closing tag: `<img>`, `<br>`, `<input>`, `<hr>`.

**Q: Difference between `id` and `class`?**
`id` is unique per page (one element only), `class` can be reused on multiple elements.

**Q: What's the difference between `<div>` and `<span>`?**
`<div>` is block-level (takes full width, starts on new line), `<span>` is inline (only takes the space it needs).

**Q: What is semantic HTML and why use it?**
Tags that describe meaning (`<nav>`, `<article>`) rather than just appearance — improves accessibility and SEO.

**Q: GET vs POST in forms?**
GET appends data to the URL (visible, limited length, used for searches); POST sends data in the request body (hidden, used for sensitive/large data).

---

## 📖 Key Definitions (Glossary)

| Term | Definition |
|---|---|
| **HTML** | HyperText Markup Language — the standard markup language used to structure content on the web. |
| **Tag** | A keyword wrapped in angle brackets that marks the start or end of an element, e.g. `<p>` or `</p>`. |
| **Element** | A complete unit made of an opening tag, its content, and a closing tag, e.g. `<p>Hello</p>`. |
| **Attribute** | Extra information added inside an opening tag to modify an element's behavior or appearance, e.g. `class`, `id`, `src`. |
| **Void/Self-closing Element** | An element with no content and no closing tag, e.g. `<img>`, `<br>`, `<hr>`, `<input>`. |
| **Block-level Element** | An element that starts on a new line and takes up the full width available, e.g. `<div>`, `<p>`, `<h1>`. |
| **Inline Element** | An element that only takes up as much width as its content and doesn't start a new line, e.g. `<span>`, `<a>`, `<b>`. |
| **Semantic HTML** | Using tags that describe the *meaning* of their content (like `<nav>`, `<article>`) instead of generic tags like `<div>`, improving accessibility and SEO. |
| **Attribute vs Value** | An attribute is the property name (`href`), the value is what it's set to (`"https://google.com"`), written as `href="https://google.com"`. |
| **DOM (Document Object Model)** | The tree-like structure browsers create from HTML, representing every element as a node that can be accessed/modified (usually via JavaScript). |
| **Nesting** | Placing one HTML element inside another, e.g. an `<li>` inside a `<ul>`. |
| **Deprecated Tag** | An old HTML tag no longer recommended for use because a modern (usually CSS-based) alternative exists, e.g. `<marquee>`, `<font>`. |
| **Accessibility (a11y)** | Designing web content so it's usable by people with disabilities, e.g. using `alt` text on images for screen readers. |
| **SEO (Search Engine Optimization)** | Practices (like using semantic tags, proper headings, `alt` text) that help search engines understand and rank a webpage. |
| **Metadata** | Data about the page itself, not shown to users directly — found inside `<head>`, e.g. `<title>`, `<meta>`. |
| **Boilerplate** | The standard, repeated starting structure of an HTML file (`<!DOCTYPE html>`, `<html>`, `<head>`, `<body>`). |

---

## 🧠 Fast Revision Cheat Sheet

```
Structure     → html, head, body, title
Text          → h1-h6, p, b, i, strong, em, mark
Links         → a href, target="_blank"
Lists         → ul/ol/li, dl/dt/dd
Media         → img, audio, video, iframe
Tables        → table, tr, th, td
Forms         → form, input, label, action, method
Semantic      → header, nav, main, section, article, aside, footer
Void elements → img, br, hr, input (no closing tag)
```
