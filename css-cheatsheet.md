# CSS Cheatsheet

A comprehensive reference guide for CSS properties, selectors, and techniques.

---

## Table of Contents

1. [What is CSS?](#1-what-is-css)
2. [How to Add CSS](#2-how-to-add-css)
   - [Inline CSS](#inline-css)
   - [Internal CSS](#internal-css)
   - [External CSS](#external-css)
3. [CSS Selectors](#3-css-selectors)
   - [Element Selector](#element-selector)
   - [Class Selector](#class-selector)
   - [ID Selector](#id-selector)
   - [Universal Selector](#universal-selector)
   - [Grouping Selector](#grouping-selector)
   - [Descendant Selector](#descendant-selector)
   - [Child Selector](#child-selector)
4. [Colors](#4-colors)
5. [Text Styling](#5-text-styling)
6. [Box Model](#6-box-model)
7. [Display Properties](#7-display-properties)
8. [Positioning](#8-positioning)
9. [Flexbox Basics](#9-flexbox-basics)
10. [Grid Basics](#10-grid-basics)
11. [Backgrounds](#11-backgrounds)
12. [Borders](#12-borders)
13. [Shadows](#13-shadows)
14. [Transitions & Animations](#14-transitions--animations)
15. [Pseudo-classes](#15-pseudo-classes)
16. [Pseudo-elements](#16-pseudo-elements)
17. [Responsive Design](#17-responsive-design)
18. [Units](#18-units)
19. [Common Properties Quick Reference](#19-common-properties-quick-reference)
20. [Best Practices](#20-best-practices)
21. [CSS Variables](#21-css-variables)

---

## 1. What is CSS?

**CSS** stands for **Cascading Style Sheets**. CSS describes how HTML elements should be displayed on screen, paper, or in other media. It controls layout, colors, fonts, and overall visual presentation.

---

## 2. How to Add CSS

### Inline CSS

Applied directly to an HTML element using the style attribute:

```html
<p style="color: blue; font-size: 16px;">Blue text</p>
```

### Internal CSS

Placed within a `<style>` tag in the `<head>` section:

```html
<style>
    p {
        color: blue;
        font-size: 16px;
    }
</style>
```

### External CSS

Linked from a separate .css file:

```html
<link rel="stylesheet" href="styles.css">
```

---

## 3. CSS Selectors

### Element Selector

Selects all elements of a specific type:

```css
p {
    color: blue;
}
```

### Class Selector

Selects all elements with a specific class:

```css
.my-class {
    color: red;
}
```

```html
<div class="my-class">Content</div>
```

### ID Selector

Selects the element with a specific ID:

```css
#my-id {
    color: green;
}
```

```html
<div id="my-id">Content</div>
```

### Universal Selector

Selects all elements:

```css
* {
    margin: 0;
    padding: 0;
}
```

### Grouping Selector

Selects multiple elements:

```css
h1, h2, h3 {
    color: navy;
}
```

### Descendant Selector

Selects all elements inside another element:

```css
div p {
    color: purple;
}
```

### Child Selector

Selects all direct children of an element:

```css
div > p {
    color: orange;
}
```

---

## 4. Colors

CSS supports multiple color formats:

```css
/* Named colors */
color: red;
background-color: blue;

/* Hex colors */
color: #ff0000;
background-color: #0000ff;

/* RGB colors */
color: rgb(255, 0, 0);
background-color: rgb(0, 0, 255);

/* RGBA colors (with transparency) */
color: rgba(255, 0, 0, 0.5);

/* HSL colors */
color: hsl(0, 100%, 50%);
```

---

## 5. Text Styling

| Property | Description | Example |
|----------|-------------|---------|
| `color` | Text color | `color: #333;` |
| `font-family` | Font type | `font-family: Arial, sans-serif;` |
| `font-size` | Text size | `font-size: 16px;` |
| `font-weight` | Text thickness | `font-weight: bold;` |
| `text-align` | Horizontal alignment | `text-align: center;` |
| `text-decoration` | Text decoration | `text-decoration: underline;` |
| `text-transform` | Case conversion | `text-transform: uppercase;` |
| `line-height` | Line spacing | `line-height: 1.5;` |
| `letter-spacing` | Character spacing | `letter-spacing: 2px;` |

```css
p {
    color: #333;
    font-family: Arial, sans-serif;
    font-size: 16px;
    font-weight: bold;
    text-align: center;
    text-decoration: underline;
    text-transform: uppercase;
    line-height: 1.5;
    letter-spacing: 2px;
}
```

---

## 6. Box Model

Every element is a rectangular box with:
- **Content**: The actual content
- **Padding**: Space inside the border
- **Border**: Border around the element
- **Margin**: Space outside the border

```
┌─────────────────────────────────┐
│         Margin                   │
│  ┌───────────────────────────┐  │
│  │      Border               │  │
│  │  ┌─────────────────────┐  │  │
│  │  │    Padding          │  │  │
│  │  │  ┌───────────────┐  │  │  │
│  │  │  │   Content     │  │  │  │
│  │  │  └───────────────┘  │  │  │
│  │  └─────────────────────┘  │  │
│  └───────────────────────────┘  │
└─────────────────────────────────┘
```

```css
div {
    width: 300px;
    height: 200px;
    padding: 20px;          /* Space inside border */
    border: 2px solid black; /* Border around element */
    margin: 10px;           /* Space outside border */
}
```

---

## 7. Display Properties

```css
display: block;        /* Takes full width, starts on new line */
display: inline;       /* Takes only needed width, no line break */
display: inline-block; /* Like inline but allows width/height */
display: none;         /* Hides element */
display: flex;         /* Flexible box layout */
display: grid;         /* Grid layout */
```

---

## 8. Positioning

| Position | Description |
|----------|-------------|
| `static` | Default positioning (normal flow) |
| `relative` | Relative to its normal position |
| `absolute` | Relative to nearest positioned ancestor |
| `fixed` | Relative to viewport (doesn't scroll) |
| `sticky` | Switches between relative and fixed |

```css
.positioned-element {
    position: relative;
    top: 10px;
    right: 20px;
    bottom: 10px;
    left: 20px;
    z-index: 10;  /* Stacking order */
}
```

---

## 9. Flexbox Basics

### Container Properties

```css
.flex-container {
    display: flex;

    /* Direction */
    flex-direction: row;  /* row, column, row-reverse, column-reverse */

    /* Alignment */
    justify-content: center;  /* flex-start, flex-end, center, space-between, space-around */
    align-items: center;      /* flex-start, flex-end, center, stretch */

    /* Wrapping */
    flex-wrap: wrap;  /* nowrap, wrap, wrap-reverse */

    /* Gap */
    gap: 10px;
}
```

### Item Properties

```css
.flex-item {
    flex: 1;              /* Grow, shrink, basis */
    order: 2;             /* Change order */
    align-self: flex-end; /* Override align-items */
}
```

---

## 10. Grid Basics

### Container Properties

```css
.grid-container {
    display: grid;

    /* Define columns and rows */
    grid-template-columns: 1fr 1fr 1fr;  /* 3 equal columns */
    grid-template-rows: 100px auto;       /* 2 rows */

    /* Gap */
    gap: 20px;

    /* Named areas */
    grid-template-areas:
        "header header header"
        "sidebar main main"
        "footer footer footer";
}
```

### Item Properties

```css
.grid-item {
    grid-column: 1 / 3;   /* Span columns 1 to 3 */
    grid-row: 2 / 4;      /* Span rows 2 to 4 */
    grid-area: header;    /* Assign to named area */
}
```

---

## 11. Backgrounds

```css
.element {
    background-color: #f0f0f0;
    background-image: url('image.jpg');
    background-size: cover;        /* cover, contain, 100px, 50% */
    background-position: center;   /* top, bottom, left, right, center */
    background-repeat: no-repeat;  /* repeat, repeat-x, repeat-y */
    background-attachment: fixed;  /* scroll, fixed */

    /* Shorthand */
    background: #f0f0f0 url('image.jpg') no-repeat center/cover;
}
```

---

## 12. Borders

```css
.element {
    border-width: 2px;
    border-style: solid;  /* solid, dashed, dotted, double */
    border-color: #333;
    border-radius: 10px;  /* Rounded corners */

    /* Shorthand */
    border: 2px solid #333;

    /* Individual sides */
    border-top: 1px solid red;
    border-right: 2px dashed blue;
    border-bottom: 3px dotted green;
    border-left: 4px double orange;
}
```

---

## 13. Shadows

```css
/* Box shadow */
.element {
    box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.3);
    /* horizontal vertical blur color */
}

/* Text shadow */
.text {
    text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
}

/* Multiple shadows */
.element {
    box-shadow:
        5px 5px 10px rgba(0, 0, 0, 0.3),
        -5px -5px 10px rgba(255, 255, 255, 0.5);
}
```

---

## 14. Transitions & Animations

### Transitions

```css
.element {
    transition: all 0.3s ease;

    /* Individual properties */
    transition-property: background-color;
    transition-duration: 0.3s;
    transition-timing-function: ease-in-out;
    transition-delay: 0.1s;
}

.element:hover {
    background-color: blue;
}
```

### Animations

```css
@keyframes slide-in {
    from {
        transform: translateX(-100%);
    }
    to {
        transform: translateX(0);
    }
}

.element {
    animation: slide-in 1s ease-in-out;
    animation-iteration-count: infinite;
    animation-direction: alternate;
}
```

---

## 15. Pseudo-classes

```css
/* Link states */
a:hover { color: red; }          /* Mouse over */
a:active { color: green; }       /* Being clicked */
a:visited { color: purple; }     /* Already visited */
a:link { color: blue; }          /* Unvisited link */

/* Form states */
input:focus { border: 2px solid blue; }  /* Has focus */
input:disabled { opacity: 0.5; }         /* Disabled */
input:checked { background: green; }     /* Checked (checkbox/radio) */

/* Structural pseudo-classes */
li:first-child { font-weight: bold; }           /* First child */
li:last-child { color: red; }                   /* Last child */
li:nth-child(2) { color: blue; }                /* Second child */
li:nth-child(odd) { background: #f0f0f0; }      /* Odd children */
li:nth-child(even) { background: #ffffff; }     /* Even children */
```

---

## 16. Pseudo-elements

```css
/* Add content before/after */
p::before {
    content: "→ ";
    color: blue;
}

p::after {
    content: " ←";
    color: red;
}

/* Style first letter/line */
p::first-letter {
    font-size: 2em;
    font-weight: bold;
}

p::first-line {
    text-transform: uppercase;
}

/* Selection styling */
::selection {
    background-color: yellow;
    color: black;
}
```

---

## 17. Responsive Design

### Media Queries

```css
/* Mobile styles (default) */
body {
    font-size: 14px;
}

/* Tablet */
@media screen and (min-width: 768px) {
    body {
        font-size: 16px;
    }
    .container {
        width: 90%;
    }
}

/* Desktop */
@media screen and (min-width: 1024px) {
    body {
        font-size: 18px;
    }
    .container {
        width: 1200px;
    }
}

/* Print styles */
@media print {
    .no-print {
        display: none;
    }
}
```

### Common Breakpoints

| Device | Breakpoint |
|--------|-----------|
| Mobile | `max-width: 480px` |
| Tablet | `max-width: 768px` |
| Desktop | `min-width: 1024px` |
| Large Desktop | `min-width: 1200px` |

---

## 18. Units

| Unit | Description | Example |
|------|-------------|---------|
| `px` | Pixels (absolute) | `font-size: 16px;` |
| `%` | Percentage of parent | `width: 50%;` |
| `em` | Relative to parent font-size | `padding: 1.5em;` |
| `rem` | Relative to root font-size | `margin: 2rem;` |
| `vw` | Viewport width (1vw = 1%) | `width: 50vw;` |
| `vh` | Viewport height (1vh = 1%) | `height: 100vh;` |
| `vmin` | Smaller of vw or vh | `font-size: 5vmin;` |
| `vmax` | Larger of vw or vh | `font-size: 5vmax;` |

---

## 19. Common Properties Quick Reference

### Sizing

```css
width: 100px;
height: 100px;
max-width: 1200px;
min-height: 500px;
```

### Spacing

```css
/* All sides */
margin: 10px;
padding: 10px;

/* Top/bottom, Left/right */
margin: 10px 20px;

/* Top, Left/right, Bottom */
margin: 10px 20px 30px;

/* Top, Right, Bottom, Left (clockwise) */
margin: 10px 20px 30px 40px;
```

### Visibility

```css
opacity: 0.5;              /* 0 (transparent) to 1 (opaque) */
visibility: hidden;        /* hidden, visible */
display: none;             /* Remove from layout */
overflow: hidden;          /* visible, hidden, scroll, auto */
```

### Cursor

```css
cursor: pointer;           /* default, pointer, not-allowed, grab, etc. */
```

### Z-index

```css
z-index: 10;              /* Stacking order (requires position) */
```

---

## 20. Best Practices

1. ✅ **Use external CSS files** for maintainability
2. ✅ **Follow a naming convention** (BEM, SMACSS, etc.)
3. ✅ **Keep selectors simple** and avoid deep nesting
4. ✅ **Use CSS variables** for repeated values
5. ✅ **Write mobile-first** responsive styles
6. ✅ **Minimize use of !important**
7. ✅ **Group related properties** together
8. ✅ **Comment complex** or non-obvious code
9. ✅ **Use shorthand properties** when appropriate
10. ✅ **Validate your CSS** with a linter

---

## 21. CSS Variables

### Defining Variables

```css
:root {
    --primary-color: #3498db;
    --secondary-color: #2ecc71;
    --font-size: 16px;
    --spacing: 20px;
    --border-radius: 8px;
}
```

### Using Variables

```css
.button {
    background-color: var(--primary-color);
    font-size: var(--font-size);
    padding: var(--spacing);
    border-radius: var(--border-radius);
}

.heading {
    color: var(--primary-color);
}

/* Fallback value */
.element {
    color: var(--text-color, #333);
}
```

### Changing Variables with JavaScript

```javascript
document.documentElement.style.setProperty('--primary-color', '#e74c3c');
```

---

## Additional Resources

- [MDN CSS Reference](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [CSS Tricks](https://css-tricks.com/)
- [Can I Use](https://caniuse.com/) - Browser compatibility checker
- [CSS Validator](https://jigsaw.w3.org/css-validator/)

---

**Happy Styling!** Practice these concepts to master CSS and create beautiful web designs.
