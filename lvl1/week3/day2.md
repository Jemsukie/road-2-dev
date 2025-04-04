[👈 Go Back](../lvl1.md)

# Week 3 • Day 2: 📏 Flexbox Layout

## Lecture Overview:
In this session, we will explore the basics of Flexbox, a powerful layout tool in CSS that helps you create flexible and responsive designs. By the end of this lesson, you will be able to create layouts such as navigation bars, galleries, and more.

---

## Key Concepts:

### 1. What is Flexbox? 🧩
Flexbox (Flexible Box Layout) is a CSS layout model that provides an efficient way to align and distribute space among items in a container, even when their sizes are dynamic.

- **Why use Flexbox?**  
  Flexbox makes it easier to design flexible, responsive layouts without using float or positioning hacks.

---

### 2. Flexbox Terminology 📚

- **Container**: The element that uses `display: flex`.  
- **Items**: The direct children of the flex container.

### 3. Basic Flexbox Properties 🔑

#### Container Properties:
- `display: flex`: Defines a flex container.
- `flex-direction`: Specifies the direction of the items (row, column).  
  ```css
  .container {
    display: flex;
    flex-direction: row; /* Default value */
  }
  ```

- `justify-content`: Aligns items horizontally.  
  Options: `flex-start`, `center`, `space-between`, `space-around`, `space-evenly`.

  ```css
  .container {
    justify-content: center;
  }
  ```

- `align-items`: Aligns items vertically.  
  Options: `stretch`, `center`, `flex-start`, `flex-end`, `baseline`.  
  ```css
  .container {
    align-items: center;
  }
  ```

---

### 4. Practical Example: Creating a Simple Navigation Bar

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Flexbox Navigation Bar</title>
  <style>
    body {
      font-family: Arial, sans-serif;
    }
    .nav {
      display: flex;
      justify-content: space-between;
      background: steelblue;
      padding: 20px;
      color: white;
    }
    .nav-item {
      margin: 0 10px;
    }
  </style>
</head>
<body>
  <nav class="nav">
    <div class="nav-item">Home</div>
    <div class="nav-item">About</div>
    <div class="nav-item">Contact</div>
  </nav>
</body>
</html>
```

---

## 🛠️ Hands-On Activity: Create a Layout Using Flexbox

### Instructions:
1. Create a new HTML file and add a container with several child elements.  
2. Apply Flexbox properties to create a gallery or a navigation bar.
3. Use different `justify-content` and `align-items` values to experiment with layout alignment.

---

## 🚀 Challenge: Build a Responsive Gallery
1. Create a gallery with multiple images inside a flex container.
2. Use `flex-wrap` to allow items to wrap onto the next row when needed.
3. Add spacing and alignment for a clean, responsive design.

Example:
```css
.gallery {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
}
.gallery-item {
  flex: 1 1 calc(33.333% - 10px);
  background: lightgray;
  height: 150px;
}
```

---

### See [CSS Flexbox Layout Guide](https://css-tricks.com/snippets/css/a-guide-to-flexbox/) for more detailed explanation
