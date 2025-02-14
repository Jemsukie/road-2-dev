[👈 Go Back](../lvl1.md)

# Week 3 • Day 1: 📱 Responsive Design

## Lecture Overview:
In this session, we will focus on building responsive web pages that adapt to different screen sizes. You’ll learn about media queries, fluid layouts, and best practices for ensuring a great user experience across devices.

---

## Key Concepts:
### 1. What is Responsive Design? 📐
Responsive design ensures that your web page looks and functions well on all devices—desktops, tablets, and smartphones—by adapting the layout based on the screen size.

- **Why is it important?**  
  More than half of web traffic comes from mobile devices, so building a responsive design is crucial for user engagement and SEO.

---

### 2. Media Queries 🛠️
Media queries are CSS rules that apply styles based on the size and capabilities of the device.

#### Syntax:
```css
@media (max-width: 768px) {
  body {
    background-color: lightblue;
  }
}
```

- `max-width: 768px`: This rule applies styles when the viewport width is 768 pixels or smaller (common tablet size).
- **Breakpoints:** Common screen width breakpoints:
  - `1200px` and above: Large screens (desktops)
  - `768px`: Tablets
  - `480px`: Smartphones

---

### 3. Fluid Layouts and Units 📏
Use **percentages, `em`, and `rem`** instead of fixed units (`px`) for a flexible layout.

Example:
```css
.container {
  width: 80%;
  padding: 2em;
}
```

**Responsive Images and Videos:**
```css
img {
  max-width: 100%;
  height: auto;
}
```

---

### 4. Responsive Navigation Menus 🍔
Implement a **mobile-friendly menu** using media queries.

```css
.nav {
  display: flex;
  justify-content: space-between;
}
@media (max-width: 768px) {
  .nav {
    flex-direction: column;
  }
}
```

---

## 🛠️ Hands-On Activity: Implement Responsive Design

### Instructions:
1. **Start with the provided HTML template**:
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Responsive Design Example</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <header>
    <h1>My Responsive Page</h1>
  </header>
  <main>
    <p>Resize the browser window to see the responsive design in action!</p>
  </main>
</body>
</html>
```

2. **Add media queries in your `styles.css` to make it responsive**:
```css
body {
  font-family: Arial, sans-serif;
}
header {
  background: steelblue;
  padding: 20px;
  text-align: center;
  color: white;
}
@media (max-width: 768px) {
  header {
    background: coral;
  }
}
```

3. **Test your webpage on different devices** (or use Chrome DevTools to simulate screen sizes).


## 🎯 Hands-On Activity: Build a Responsive Portfolio Page

### Instructions:
1. Create a basic portfolio with a `header`, `about` section, and `project gallery`.  
2. Use media queries to ensure it’s mobile-friendly.  
3. Add responsive images and a flexible navigation menu.
