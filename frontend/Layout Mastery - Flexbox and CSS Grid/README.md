# Flexbox & CSS Grid (Layout Mastery)

## Overview

This module covers modern CSS layout systems: **Flexbox** and **CSS Grid**. These tools are essential for building responsive, scalable, and professional web layouts.

# 1. FLEXBOX

## 1.1 What is Flexbox?

Flexbox (Flexible Box Layout) is a **1-dimensional layout system** used to arrange items in a row or column.

It is best suited for:
- Navigation bars
- Toolbars
- Centering elements
- Small UI components

### Basic Setup

```css
.container {
  display: flex;
}
```

### 1.2 Flexbox Main Concepts

Flexbox works along two axes:
- Main axis → horizontal (default row direction)
- Cross axis → vertical

### 1.3 Alignment & Spacing

**A. Justify Content (Main Axis Alignment)**
Controls horizontal spacing between items.
```css
.container {
  display: flex;
  justify-content: space-between;
}
```

**Common values:**
- flex-start → items aligned left
- flex-end → items aligned right
- center → items centered
- space-between → equal spacing between items
- space-around → space around items
- space-evenly → equal spacing everywhere

**Application Example**
Used in navigation bars to spread menu items evenly.

**B. Align Items (Cross Axis Alignment)**
Controls vertical alignment of items.
```css
.container {
  display: flex;
  align-items: center;
}
```
**Common Values:**
stretch (default)
flex-start
flex-end
center

**Application Example**
Used to vertically center items inside a header or navbar.

**C. Gap (Modern Spacing Method)**
```css 
.container {
  display: flex;
  gap: 20px;
}
```

**Why it matters:**
- Cleaner than margins
- Automatically manages spacing between items

**D. Flex Direction**
```css
.container {
  display: flex;
  flex-direction: column;
}
```

**Options:**
- row (default)
- column
- row-reverse
- column-reverse

**Application Example**
Used in stacking form inputs vertically.

**E. Wrapping Items**
```css
.container {
  display: flex;
  flex-wrap: wrap;
}
```

**Application Example**
Used in responsive layouts where items should move to the next line.

### 1.4 Flex Item Control
**Flex Grow**
Allows items to expand.

```css
.item {
  flex-grow: 1;
}
```

**Flex Shrink**
Allows items to shrink when space is limited.

```css
.item {
  flex-shrink: 1;
}
```

**Flex Basis**
Defines initial size.

```css
.item {
  flex-basis: 200px;
}
```

**Flex Shortcut**

```css
.item {
  flex: 1;
}
```

### 1.5 Flexbox Real Example: Navbar
```html
<div class="navbar">
  <div class="logo">Logo</div>
  <div class="menu">Menu</div>
  <div class="profile">Profile</div>
</div>
```

**Give feedback**
```css
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 15px;
}
``` 
**Result:**
A responsive navigation bar with evenly spaced items.

# 2. CSS GRID

## 2.1 What is CSS Grid?
CSS Grid is a 2-dimensional layout system used for rows and columns.

**It is best suited for:**
- Page layouts
- Dashboards
- Complex UI systems

### 2.2 Basic Setup
```css
.container {
  display: grid;
}
```

### 2.3 Defining Columns & Rows

**Columns**
```css
.container {
  grid-template-columns: 200px 200px 200px;
}
```

**Flexible Columns**
```css
.container {
  grid-template-columns: 1fr 1fr 1fr;
}
```

**Meaning of fr**
Represents a fraction of available space
Rows

```css
.container {
  grid-template-rows: 100px 200px;
}
```

### 2.4 Grid Gap
```css
.container {
  gap: 20px;
}
```

**Application Example**
Used in card layouts and dashboards.

### 2.5 Responsive Grid Layout
```css
.container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
}
```

**Benefits:**
- Automatically adjusts layout
- Responsive without media queries

### 2.6 Placing Grid Items
**Using Line Numbers**
```css
.item {
  grid-column: 1 / 3;
}
```

**Using Named Areas**
```css
.container {
  display: grid;
  grid-template-areas:
    "header header"
    "sidebar content"
    "footer footer";
}
.header { grid-area: header; }
.sidebar { grid-area: sidebar; }
.content { grid-area: content; }
.footer { grid-area: footer; }
```
**Application Example**
Used in full website layouts.



