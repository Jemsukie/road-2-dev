[👈 Go Back](../lvl1.md)

# Week 2 • Day 3: 📦 Box Model and Layout

## Lecture Overview:
In this session, we will explore the CSS box model, a fundamental concept for controlling the layout of web pages. By understanding how margins, borders, padding, and content work together, you'll gain control over your page's structure. We will also introduce basic layout techniques to help you create well-organized designs.

## Key Concepts:
- What is the CSS box model?
- Understanding margins, borders, padding, and content.
- Basic layout techniques: width, height, and display properties.

---

## 📦 What is the CSS Box Model?

The box model is a fundamental concept in CSS that describes how every element on a web page is essentially a rectangular box. The model consists of four parts:

1. **Content**: The actual content of the element (e.g., text, images).
2. **Padding**: Clears an area around the content, inside the border.
3. **Border**: Surrounds the padding and content.
4. **Margin**: Clears an area outside the border, pushing other elements away.

---

## 🔍 Understanding Margins, Borders, Padding, and Content

Here’s a visual representation of how these properties work together in the box model:

```css
/* Example CSS */
.box {
    width: 300px;
    padding: 20px; /* Space between content and border */
    border: 5px solid darkblue; /* Border surrounding the content */
    margin: 10px; /* Space outside the border */
}
```

### Explanation:
- `Content`: The area where your text or images are displayed.
- `Padding`: Space between the content and the border.
- `Border`: Defines the boundary around the content and padding.
- `Margin`: Space outside the border, separating the element from others.

## Basic Layout Techniques

### 1. **Width and Height Properties**
You can control the size of an element using the `width` and `height` properties. These values can be defined in various units, such as pixels (`px`), percentages (`%`), or viewport units (`vw`, `vh`).
```css
.box {
    width: 50%; /* Element will take up 50% of the container's width */
    height: 200px; /* Fixed height */
}
```

### 2. **Display Property**
The `display` property controls how an element is displayed on the web page. Common values include:

- `block`: The element will take up the full width of its container.
- `inline`: The element will only take up as much space as its content.
- `inline-block`: Allows the element to be styled like a block element while behaving like an inline element.
```css
.block-element {
    display: block;
}

.inline-element {
    display: inline;
}
```

## 🎯 Hands-On Activity: Create a Simple Layout Using the Box Model

### Instructions:

1. Create a new CSS file named `layout.css` and include the following styles:
```css
.container {
    width: 80%;
    margin: 0 auto; /* Centers the container horizontally */
}

.box {
    background-color: lightblue;
    padding: 20px;
    border: 3px solid darkblue;
    margin: 15px 0; /* Adds vertical spacing between boxes */
    width: 100%;
}

.header {
    background-color: darkblue;
    color: white;
    padding: 10px;
    text-align: center;
}
```

2. Create a new HTML file named `layout.html` and link the CSS file:
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Box Model Layout</title>
    <link rel="stylesheet" href="layout.css">
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>Simple Layout with CSS Box Model</h1>
        </div>
        <div class="box">
            <p>This is the first box, demonstrating the box model with padding, borders, and margins.</p>
        </div>
        <div class="box">
            <p>This is the second box. Adjust the padding, border, and margin values to see how they affect the layout.</p>
        </div>
    </div>
</body>
</html>
```

3. Open `layout.html` in your browser to see how the boxes are styled using the box model.
