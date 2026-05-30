# Responsive Web Design

## Introduction

Responsive Web Design (RWD) is the process of building websites that automatically adapt to different screen sizes, devices, and orientations. A responsive website provides a good user experience whether viewed on:

* Mobile phones
* Tablets
* Laptops
* Desktop computers
* Smart TVs

Modern websites must be responsive because users access the web from many different devices.

---

# 1. Mobile-First Design

## What is Mobile-First Design?

Mobile-first design is a design strategy where you first build the website layout for small screens (mobile devices) before adding styles for larger screens.

Instead of shrinking a desktop website down to mobile size, you start with mobile and progressively enhance the layout for tablets and desktops.

---

## Why Mobile-First?

### Advantages

* Better performance on mobile devices
* Cleaner and simpler layouts
* Improved user experience
* Easier scaling to larger devices
* Encourages optimized design

---

## Traditional Approach vs Mobile-First

| Traditional Desktop-First  | Mobile-First                    |
| -------------------------- | ------------------------------- |
| Start with desktop layout  | Start with mobile layout        |
| Remove features for mobile | Add features for larger screens |
| Can become cluttered       | Cleaner and more organized      |
| Often slower on phones     | Better mobile performance       |

---

# Basic Mobile-First Example

## HTML

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mobile First Design</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <div class="container">
        <h1>Responsive Website</h1>
        <p>This layout starts from mobile design.</p>
    </div>

</body>
</html>
```

---

## CSS

```css
/* Mobile Styles First */
body {
    margin: 0;
    font-family: Arial, sans-serif;
    background: #f4f4f4;
}

.container {
    padding: 20px;
    background: white;
    margin: 10px;
    border-radius: 10px;
}

h1 {
    font-size: 24px;
}

/* Tablet Styles */
@media (min-width: 768px) {
    .container {
        max-width: 700px;
        margin: 40px auto;
    }

    h1 {
        font-size: 36px;
    }
}

/* Desktop Styles */
@media (min-width: 1024px) {
    .container {
        max-width: 1000px;
    }

    h1 {
        font-size: 48px;
    }
}
```

---

## Explanation

### Mobile Styles

These styles apply to all devices by default:

```css
.container {
    padding: 20px;
}
```

This means the mobile layout is the base layout.

---

### Tablet Styles

```css
@media (min-width: 768px)
```

When the screen width reaches 768px or larger, the tablet styles become active.

---

### Desktop Styles

```css
@media (min-width: 1024px)
```

When the screen width becomes 1024px or larger, desktop styles are applied.

---

# 2. Media Queries

## What are Media Queries?

Media queries are CSS rules used to apply different styles depending on:

* Screen width
* Screen height
* Device orientation
* Resolution
* Device type

Media queries make responsive design possible.

---

# Basic Syntax

```css
@media (condition) {
    /* CSS Rules */
}
```

---

# Example

```css
@media (max-width: 600px) {
    body {
        background: lightblue;
    }
}
```

### Explanation

If the screen width is 600px or smaller, the background becomes light blue.

---

# Common Breakpoints

| Device  | Width            |
| ------- | ---------------- |
| Mobile  | 0px – 767px      |
| Tablet  | 768px – 1023px   |
| Desktop | 1024px and above |

---

# Using Multiple Media Queries

```css
/* Mobile */
body {
    background: white;
}

/* Tablet */
@media (min-width: 768px) {
    body {
        background: lightgray;
    }
}

/* Desktop */
@media (min-width: 1024px) {
    body {
        background: gray;
    }
}
```

---

# Responsive Navigation Example

## HTML

```html
<nav>
    <ul class="menu">
        <li><a href="#">Home</a></li>
        <li><a href="#">About</a></li>
        <li><a href="#">Services</a></li>
        <li><a href="#">Contact</a></li>
    </ul>
</nav>
```

---

## CSS

```css
.menu {
    list-style: none;
    padding: 0;
    display: flex;
    flex-direction: column;
    gap: 10px;
}

.menu a {
    text-decoration: none;
    background: black;
    color: white;
    padding: 10px;
    display: block;
}

/* Desktop Navigation */
@media (min-width: 768px) {
    .menu {
        flex-direction: row;
        justify-content: center;
    }
}
```

---

## Explanation

### Mobile View

```css
flex-direction: column;
```

The navigation links appear vertically.

---

### Desktop View

```css
flex-direction: row;
```

The navigation links appear horizontally.

---

# Media Query Features

## 1. Width

```css
@media (min-width: 768px)
```

Applies styles when width is 768px or more.

---

## 2. Height

```css
@media (min-height: 700px)
```

Applies styles based on screen height.

---

## 3. Orientation

```css
@media (orientation: landscape)
```

Applies styles when device is in landscape mode.

---

## 4. Dark Mode

```css
@media (prefers-color-scheme: dark) {
    body {
        background: black;
        color: white;
    }
}
```

---

# 3. Responsive Units

## What are Responsive Units?

Responsive units automatically scale elements according to screen size or parent size.

They help create flexible layouts.

---

# Types of Responsive Units

## 1. Percentage (%)

### Meaning

Percentage values are relative to the parent element.

---

## Example

```css
.container {
    width: 80%;
}
```

### Explanation

The container takes 80% of its parent width.

---

# Practical Example

## HTML

```html
<div class="parent">
    <div class="child"></div>
</div>
```

---

## CSS

```css
.parent {
    width: 100%;
    background: gray;
}

.child {
    width: 50%;
    height: 100px;
    background: blue;
}
```

---

## Result

The blue box occupies half the width of the parent.

---

# 2. rem

## Meaning

`rem` stands for Root EM.

It is based on the root HTML font size.

Default browser font size:

```css
1rem = 16px
```

---

# Example

```css
h1 {
    font-size: 2rem;
}
```

### Explanation

```css
2rem = 32px
```

because:

```css
16 × 2 = 32
```

---

# Why rem is Important

* Better accessibility
* Easier scaling
* Consistent spacing
* Responsive typography

---

# rem Example

```css
html {
    font-size: 16px;
}

h1 {
    font-size: 3rem;
}

p {
    font-size: 1rem;
}
```

---

# 3. vh (Viewport Height)

## Meaning

`vh` represents a percentage of the viewport height.

```css
100vh = full screen height
```

---

# Example

```css
.hero {
    height: 100vh;
}
```

### Explanation

The hero section fills the entire screen height.

---

# Practical Example

## HTML

```html
<section class="hero">
    <h1>Welcome</h1>
</section>
```

---

## CSS

```css
.hero {
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    background: purple;
    color: white;
}
```

---

# 4. vw (Viewport Width)

## Meaning

`vw` represents a percentage of the viewport width.

```css
100vw = full screen width
```

---

# Example

```css
.banner {
    width: 100vw;
}
```

---

# Responsive Typography with vw

```css
h1 {
    font-size: 5vw;
}
```

### Explanation

The text size changes according to screen width.

---

# Comparing Units

| Unit | Meaning                     | Best Use               |
| ---- | --------------------------- | ---------------------- |
| %    | Relative to parent          | Flexible layouts       |
| rem  | Relative to root font size  | Typography and spacing |
| vh   | Relative to viewport height | Full-screen sections   |
| vw   | Relative to viewport width  | Responsive sizing      |

---

# Combining Responsive Units

```css
.container {
    width: 90%;
    max-width: 1200px;
    padding: 2rem;
}

.hero {
    height: 100vh;
}

h1 {
    font-size: 5vw;
}
```

---

# Full Responsive Layout Project

## HTML

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Responsive Layout</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <header>
        <h1>My Responsive Website</h1>
    </header>

    <main class="grid-container">
        <div class="card">Card 1</div>
        <div class="card">Card 2</div>
        <div class="card">Card 3</div>
        <div class="card">Card 4</div>
    </main>

</body>
</html>
```

---

## CSS

```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    background: #f4f4f4;
}

header {
    background: black;
    color: white;
    text-align: center;
    padding: 2rem;
}

.grid-container {
    display: grid;
    grid-template-columns: 1fr;
    gap: 20px;
    padding: 20px;
}

.card {
    background: white;
    padding: 2rem;
    border-radius: 10px;
    text-align: center;
}

/* Tablet */
@media (min-width: 768px) {
    .grid-container {
        grid-template-columns: repeat(2, 1fr);
    }
}

/* Desktop */
@media (min-width: 1024px) {
    .grid-container {
        grid-template-columns: repeat(4, 1fr);
    }
}
```

---

# Explanation of the Project

## Mobile View

```css
grid-template-columns: 1fr;
```

Only one column is shown.

---

## Tablet View

```css
grid-template-columns: repeat(2, 1fr);
```

Two columns are displayed.

---

## Desktop View

```css
grid-template-columns: repeat(4, 1fr);
```

Four columns are displayed.

---

# Best Practices for Responsive Web Design

## 1. Use Mobile-First Approach

Always design for small screens first.

---

## 2. Use Flexible Layouts

Avoid fixed widths whenever possible.

Instead of:

```css
width: 1200px;
```

Use:

```css
width: 90%;
max-width: 1200px;
```

---

## 3. Use Relative Units

Prefer:

* rem
* %
* vh
* vw

Instead of fixed pixels.

---

## 4. Optimize Images

```css
img {
    max-width: 100%;
    height: auto;
}
```

This prevents images from overflowing.

---

# Common Responsive Design Mistakes

| Mistake                | Problem                        |
| ---------------------- | ------------------------------ |
| Using fixed widths     | Layout breaks on small screens |
| Ignoring mobile users  | Poor user experience           |
| Too many media queries | Difficult maintenance          |
| Large images           | Slow loading                   |
| Small text             | Poor readability               |

---

# Practice Exercises

## Exercise 1

Create a responsive navigation bar that:

* Stacks vertically on mobile
* Displays horizontally on desktop

---

## Exercise 2

Build a responsive card layout using CSS Grid.

Requirements:

* 1 column on mobile
* 2 columns on tablet
* 4 columns on desktop

---

## Exercise 3

Create a hero section that:

* Uses 100vh
* Centers content vertically and horizontally
* Has responsive text using vw

---

# Assignment

Build a responsive portfolio homepage containing:

* Header
* Navigation bar
* Hero section
* Responsive card section
* Footer

Requirements:

* Use mobile-first design
* Use media queries
* Use rem for typography
* Use vh and vw where necessary
* Ensure layout works on mobile, tablet, and desktop
