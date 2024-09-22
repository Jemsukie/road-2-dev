[👈 Go Back](../lvl1.md)

# Week 2 • Day 2: 🛠️ CSS Selectors and Properties

## Lecture Overview:
Today, we'll dive deeper into CSS selectors and properties. By the end of this session, you’ll know how to target elements using different selectors (element, class, ID) and apply styles using a variety of CSS properties. You’ll also have hands-on practice styling HTML elements using these selectors.

## Key Concepts:
- CSS Selectors: Element, Class, and ID.
- Common CSS Properties: color, font-size, margin, padding, etc.
- Combining selectors to apply specific styles.

---

## 🔍 CSS Selectors

Selectors allow you to target specific HTML elements that you want to style. The three basic types of selectors are:

### 1. **Element Selector**
The element selector applies styles to all elements of the specified type (e.g., all `<p>` tags).

```css
p {
    color: green;
}
```

### 2. **Class Selector**
A class selector applies styles to any HTML element with a matching class. It is defined with a dot (.) followed by the class name. You can apply a class to multiple elements.
```css
.my-class {
    font-size: 20px;
    color: red;
}
```
HTML Example:
```html
<p class="my-class">This is a paragraph with a class.</p>
```

### 3. ID Selector
An ID selector applies styles to a single element with a specific ID. It is defined with a hash (#) followed by the ID name. IDs should be unique to a single element.
```css
#my-id {
    background-color: lightblue;
    padding: 10px;
}
```
HTML Example:
```html
<div id="my-id">This is a div with an ID.</div>
```


## 🎨 Common CSS Properties
Once you've selected an element using a selector, you can apply various properties to style it. Some commonly used properties are:

- `color` 
  - Sets the text color of an element.
  ```css
    h1 {
        color: navy;
    }
  ```
- `font-size`
  - Sets the size of the text.
  ```css
    p {
        font-size: 18px;
    }
  ```
- `margin`
  - Controls the space outside an element's border.
  ```css
    div {
        margin: 20px;
    }
  ```
- `padding`
  - Controls the space inside an element's border.
  ```css
    div {
        padding: 15px;
    }
  ```

## 🔗 Combining Selectors
You can combine selectors to target more specific elements:

1. Element and Class Combination:
```css
p.highlight {
    color: blue;
}
```
This will only apply the style to `<p>` elements that have the `highlight` class.

2. Element and ID Combination:
```css
div#special {
    text-align: center;
}
```
This will only style the `<div>` element with the `special ID`.


## 🎯 Hands-On Activity: Apply Basic Styles

### Instructions:
1. Create a new CSS file named `selectors.css`.
2. Add the following styles to target different HTML elements using class and ID selectors:
```css
/* Element selector */
h1 {
    color: darkgreen;
    text-align: center;
}

/* Class selector */
.highlight {
    background-color: yellow;
    font-style: italic;
}

/* ID selector */
#special {
    color: red;
    font-weight: bold;
    border: 2px solid black;
    padding: 10px;
}
```
3. Create a new HTML file named `selectors.html`:
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS Selectors Example</title>
    <link rel="stylesheet" href="selectors.css">
</head>
<body>
    <h1>CSS Selectors in Action</h1>
    <p>This is a regular paragraph.</p>
    <p class="highlight">This is a paragraph with the "highlight" class.</p>
    <div id="special">This is a div with the "special" ID.</div>
</body>
</html>
```
4. Open `selectors.html` in your browser and observe how the different styles are applied.

