[👈 Go Back](../lvl1.md)

# Week 2, Day 1: 🎨 Introduction to CSS

## Lecture Overview:
In this session, we will introduce CSS (Cascading Style Sheets) and explore how it is used to style HTML elements. By the end of the lesson, you will understand the different ways to apply CSS to your web pages and be able to apply basic styles such as colors, fonts, and backgrounds.

## Key Concepts:
- What is CSS?
- Different types of CSS: inline, internal, and external.
- CSS syntax and selectors.
- Applying basic styles to an HTML page.

---

## 🌐 What is CSS?

CSS (Cascading Style Sheets) is a stylesheet language used to describe the presentation of a document written in HTML or XML. CSS controls the layout of multiple web pages all at once, allowing for greater flexibility and control over the design.

---

## 🏗️ Types of CSS

There are three main ways to apply CSS to an HTML document:

### 1. **Inline CSS**
Inline CSS is used to apply styles directly within an HTML element using the `style` attribute. 

```html
<h1 style="color: blue;">This is a heading</h1>
```

### 2. Internal CSS
Internal CSS is defined within the `<style>` tag in the `<head>` section of an HTML document.

```html
<head>
    <style>
        h1 {
            color: blue;
        }
    </style>
</head>
```

### 3. External CSS
External CSS is written in a separate .css file and linked to the HTML document using the `<link>` tag.

```html
<head>
    <link rel="stylesheet" href="styles.css">
</head>
```


## ✍️ CSS Syntax and Selectors

CSS is made up of selectors and declaration blocks. A basic CSS rule consists of a selector and a set of declarations enclosed in curly braces.

Example:
```css
h1 {
    color: blue; /* Property: color, Value: blue */
    font-size: 24px; /* Property: font-size, Value: 24px */
}
```

### Selectors:
- `Element Selector:` Selects all elements of a given type (e.g., `h1`).
- `Class Selector:` Selects elements with a specific class (e.g., `.class-name`).
- `ID Selector:` Selects a unique element with a specific ID (e.g., `#id-name`).


## 🎯 Hands-On Activity: Apply Basic Styles

### Instructions:
1. Create a new CSS file named `styles.css` and include the following styles:
```css
body {
    background-color: #f0f0f0; /* Light gray background */
    font-family: Arial, sans-serif; /* Font style */
}

h1 {
    color: darkblue; /* Dark blue heading */
    text-align: center; /* Centered text */
}

p {
    color: #333; /* Dark gray text */
    line-height: 1.5; /* Improved line spacing */
}
```

2. Create a new HTML file named index.html and link the CSS file:
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Styled Page</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <h1>Welcome to My Styled Page</h1>
    <p>This is a paragraph styled with CSS.</p>
</body>
</html>
```

3. Open `index.html` in your browser to see the applied styles.
