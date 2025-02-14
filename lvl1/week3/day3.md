[👈 Go Back](../lvl1.md)

# Week 3 • Day 3: 🔲 CSS Grid Layout

## Lecture Overview:
In this session, we will learn about CSS Grid Layout, a powerful layout system in CSS that allows you to create complex and responsive web layouts with ease. By the end of this lesson, you’ll be able to build a grid-based layout for a webpage.

---

## Key Concepts:

### 1. What is CSS Grid? 📏
CSS Grid is a two-dimensional layout system that allows you to control both rows and columns in a web layout.

- **Why use CSS Grid?**  
  CSS Grid simplifies the process of building web layouts compared to traditional methods like float or Flexbox.

---

### 2. Basic Grid Terminology 📚
- **Grid Container**: The element that has `display: grid`.  
- **Grid Items**: The direct children of the grid container.  
- **Grid Lines**: The dividing lines that create rows and columns.  

### 3. Basic Grid Properties 🔑

#### Container Properties:
- `display: grid`: Defines a grid container.
- `grid-template-columns`: Defines the number and size of columns.  
  ```css
  .container {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr; /* Creates three equal columns */
  }
  ```

- `grid-template-rows`: Defines the number and size of rows.
  ```css
  .container {
    grid-template-rows: 100px 200px;
  }
  ```

- `gap`: Adds spacing between grid items.  
  ```css
  .container {
    gap: 20px;
  }
  ```

---

### 4. Practical Example: Creating a Simple Grid Layout

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CSS Grid Layout</title>
  <style>
    body {
      font-family: Arial, sans-serif;
    }
    .grid-container {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 10px;
    }
    .grid-item {
      background: lightblue;
      padding: 20px;
      text-align: center;
    }
  </style>
</head>
<body>
  <div class="grid-container">
    <div class="grid-item">1</div>
    <div class="grid-item">2</div>
    <div class="grid-item">3</div>
    <div class="grid-item">4</div>
    <div class="grid-item">5</div>
    <div class="grid-item">6</div>
  </div>
</body>
</html>
```

---

## 🛠️ Hands-On Activity: Build a Grid-Based Layout

### Instructions:
1. Create a new HTML file and add a container with multiple child elements.
2. Use CSS Grid to organize the elements into rows and columns.
3. Experiment with different values for `grid-template-columns`, `grid-template-rows`, and `gap` to customize your layout.

---

## 🚀 Challenge: Create a Portfolio Grid
1. Build a portfolio section with project cards arranged in a grid.  
2. Use `grid-template-areas` to create a custom layout.  
3. Ensure your grid is responsive by adjusting the column count for smaller screens.

Example:
```css
.portfolio {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 20px;
}
.project-card {
  background: lightgray;
  padding: 20px;
  border: 1px solid #ccc;
}
```

---
