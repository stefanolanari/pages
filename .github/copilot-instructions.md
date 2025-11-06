# PDFMake Learning Examples - Copilot Instructions

This repository contains Italian-language educational examples demonstrating PDFMake library capabilities for client-side PDF generation.

## Project Architecture

This is a collection of standalone HTML examples, each demonstrating specific PDFMake features:
- **`pdfmake/ese_b*.html`**: Progressive examples teaching PDFMake concepts (boxes, lines, styling, formatting)
- **`test.html`**: Advanced example showing ECharts integration with vector PDF export
- **Generated PDFs**: Each example creates corresponding `ese_b*_h53.pdf` files

## File Naming Convention

Follow the established pattern:
- `ese_b##_pdfmake.html` for numbered examples
- Descriptive titles in `<title>` tags (Italian)
- Generated PDFs use `ese_b##_h53.pdf` format

## PDFMake Code Patterns

### Standard HTML Structure
Every example follows this template:
```html
<!doctype html>
<html lang="it">
<head>
  <meta charset="utf-8" />
  <title>[Descriptive Italian title]</title>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/pdfmake/0.2.10/pdfmake.min.js"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/pdfmake/0.2.10/vfs_fonts.min.js"></script>
  <style>
    body {
      font-family: Arial, Helvetica, sans-serif;
      padding: 2rem;
    }
    button {
      padding: 10px 18px;
      border-radius: 6px;
      border: none;
      background: #0077cc;
      color: white;
      font-size: 15px;
      cursor: pointer;
    }
    button:hover {
      background: #005fa3;
    }
  </style>
</head>
<body>
  <h2>[Italian heading]</h2>
  <button onclick="generaPDF()">Genera PDF</button>
  <script>
    function generaPDF() {
      const dd = { /* PDFMake document definition */ };
      pdfMake.createPdf(dd).open();
    }
  </script>
</body>
```

### Document Definition Patterns
- **Page setup**: Always use `pageSize: 'A4'` and consistent margins `[40, 60, 40, 60]`
- **Content structure**: Use array of objects with `text`, `canvas`, or table elements
- **Styling**: Define global styles in `styles` object (see `ese_b07_pdfmake.html`)
- **Text formatting**: Use array syntax for inline styling: `{ text: ['normal', { text: 'bold', bold: true }] }`
- **Canvas elements**: For shapes/lines, use `canvas` with `type: 'rect'|'line'` objects

### Common Conventions
- **Comments**: Use Italian comments with emoji prefixes (🎨, 📄, etc.)
- **Variables**: Use descriptive Italian names (`generaPDF`, `dd` for document definition)
- **Margins**: Consistent spacing using `margin: [left, top, right, bottom]` arrays
- **Colors**: Use web color names or hex codes, prefer named colors for readability

## Key Learning Progression

Examples build complexity:
1. `ese_b01`: Basic boxes and positioning
2. `ese_b02`: [Check content]
3. `ese_b03`: Lines with colors and thickness
4. `ese_b06`: Word-level text formatting  
5. `ese_b07`: Global style definitions
6. `test.html`: Advanced ECharts SVG integration

## Development Workflow

- Examples are standalone - open directly in browser
- No build process or dependencies beyond CDN scripts
- Each example generates its own PDF via `pdfMake.createPdf().open()`

## Special Integration Points

**ECharts Integration** (`test.html`):
- Uses SVG renderer: `echarts.init(element, null, { renderer: 'svg' })`
- Extracts SVG for vector PDF inclusion
- Demonstrates advanced chart-to-PDF workflow

When creating new examples, maintain the educational progression and follow the established Italian language and styling conventions.