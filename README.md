# Markdown to PDF Generator

A lightweight, client‑side web app that lets you write Markdown and instantly preview it as HTML—and then print or save it as a formatted PDF.

---

## Features

- **Live Preview**  
  Type Markdown into the textarea and see real‑time HTML rendering below.

- **Print‑to‑PDF**  
  Click **Generate PDF** (or use your browser’s Print dialog) to produce a paginated, A4‑sized PDF.

- **Zero Dependencies (except `marked`)**  
  Uses the [Marked](https://github.com/markedjs/marked) library for fast Markdown-to-HTML parsing.

- **Print Styles**  
  Special CSS rules ensure:
  - Margins of 0.5 in on A4 pages  
  - Headings don’t break across pages  
  - Printable content only (hides controls)

---

## Getting Started

1. **Download or clone** this repo.  
2. **Open** `index.html` in any modern browser.  
3. **Write** your Markdown in the top textarea.  
4. **Click** “Generate PDF” (or press **Ctrl+P** / **⌘+P**) to print/save.

---

## File Structure

```

.
├── index.html      # Main page with textarea, preview pane, and print styles
└── README.md       # Project overview and instructions

```

---

## How It Works

1. **Markdown Input**  
   A `<textarea>` captures user‑entered Markdown.

2. **Live Conversion**  
   On each keystroke, JavaScript calls:
   ```js
   const html = marked.parse(markdown);
   ```

and injects the output into the preview `<div>`.

3. **Print Styles**
   The `@media print` CSS block removes UI controls, sets page margins, and optimizes page breaks.

4. **PDF Generation**
   Hitting **Generate PDF** triggers `window.print()`, opening the browser’s Print dialog. Select “Save as PDF” to export.

---

## Dependencies

* [Marked](https://cdn.jsdelivr.net/npm/marked/marked.min.js) (loaded via CDN)

---

## Customization

* **Page Size**
  Change `@page { size: A4; }` to `letter` or custom dimensions.

* **Margins**
  Adjust `margin: 0.5in;` in the `@page` block.

* **Fonts**
  Edit the `body { font-family: … }` rule.

* **Styling**
  Add any additional CSS under the existing `<style>` tag.

---
