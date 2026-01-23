[👈 Go Back](../lvl1.md)

# Week 5 • Day 2: 🔄 Basic Interactivity

## Lecture Overview:
In this session, we will learn how to create interactive features on web pages by dynamically changing styles and content. You'll discover how to toggle visibility, update text, modify CSS properties, and create engaging user experiences that respond to user actions in real-time.

---

## Key Concepts:

### 1. Changing Styles Dynamically 🎨

JavaScript allows you to modify CSS styles directly, enabling you to create visual feedback and animations.

#### Modifying Individual Style Properties:
```javascript
let element = document.querySelector(".box");

element.style.color = "blue";
element.style.fontSize = "24px";
element.style.backgroundColor = "yellow";
element.style.padding = "20px";
```

#### Using CSS Classes:
Instead of changing individual properties, you can toggle CSS classes:

```javascript
let element = document.querySelector(".box");

// Add a class
element.classList.add("highlight");

// Remove a class
element.classList.remove("highlight");

// Toggle a class (add if missing, remove if present)
element.classList.toggle("active");
```

**CSS:**
```css
.highlight {
    background-color: yellow;
    font-weight: bold;
}

.active {
    transform: scale(1.1);
    transition: transform 0.3s;
}
```

---

### 2. Updating Content Dynamically 📝

You can change the text content, HTML content, and attributes of elements in response to user actions.

#### Changing Text Content:
```javascript
let heading = document.getElementById("title");
heading.textContent = "New Title";
heading.innerText = "Another Title";
```

#### Changing HTML Content:
```javascript
let container = document.getElementById("content");
container.innerHTML = "<p>New paragraph with <strong>bold</strong> text</p>";
```

#### Changing Attributes:
```javascript
let image = document.querySelector("img");
image.src = "new-image.jpg";
image.alt = "New description";

let link = document.querySelector("a");
link.href = "https://www.example.com";
link.textContent = "Visit Example";
```

---

### 3. Toggling Visibility 👁️

You can show and hide elements dynamically:

#### Using Display Property:
```javascript
let element = document.getElementById("my-element");

// Hide element
element.style.display = "none";

// Show element
element.style.display = "block";
```

#### Using Visibility Property:
```javascript
let element = document.getElementById("my-element");

// Hide element (takes up space)
element.style.visibility = "hidden";

// Show element
element.style.visibility = "visible";
```

#### Using Opacity:
```javascript
let element = document.getElementById("my-element");

// Make transparent
element.style.opacity = "0";

// Make visible
element.style.opacity = "1";
```

---

### 4. Creating Interactive Features 💡

Combine event handling with style and content changes to create interactive elements:

#### Example: Toggle Button
```javascript
let button = document.getElementById("toggle-btn");
let content = document.getElementById("content");

button.addEventListener("click", function() {
    if (content.style.display === "none") {
        content.style.display = "block";
        button.textContent = "Hide";
    } else {
        content.style.display = "none";
        button.textContent = "Show";
    }
});
```

#### Example: Color Changer
```javascript
let button = document.getElementById("color-btn");
let box = document.getElementById("color-box");
let colors = ["red", "blue", "green", "yellow", "purple"];
let currentIndex = 0;

button.addEventListener("click", function() {
    currentIndex = (currentIndex + 1) % colors.length;
    box.style.backgroundColor = colors[currentIndex];
});
```

---

### 5. Practical Example: Interactive Card

Here's a complete example that demonstrates multiple interactive features:

**HTML:**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Card</title>
    <style>
        .card {
            width: 300px;
            padding: 20px;
            border: 2px solid #ccc;
            border-radius: 10px;
            margin: 20px;
            transition: all 0.3s;
        }
        .card.highlight {
            border-color: blue;
            box-shadow: 0 4px 8px rgba(0,0,0,0.2);
        }
        .hidden {
            display: none;
        }
    </style>
</head>
<body>
    <div class="card" id="card">
        <h2>Interactive Card</h2>
        <p id="card-text">This is a card with interactive features.</p>
        <button id="highlight-btn">Highlight</button>
        <button id="hide-btn">Hide Text</button>
    </div>
    
    <script>
        let card = document.getElementById("card");
        let cardText = document.getElementById("card-text");
        let highlightBtn = document.getElementById("highlight-btn");
        let hideBtn = document.getElementById("hide-btn");
        
        highlightBtn.addEventListener("click", function() {
            card.classList.toggle("highlight");
        });
        
        hideBtn.addEventListener("click", function() {
            if (cardText.style.display === "none") {
                cardText.style.display = "block";
                hideBtn.textContent = "Hide Text";
            } else {
                cardText.style.display = "none";
                hideBtn.textContent = "Show Text";
            }
        });
    </script>
</body>
</html>
```

---

## 🛠️ Hands-On Activity: Create Interactive Features

### Instructions:
1. **Create a new HTML file** with the following structure:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Features</title>
    <style>
        .box {
            width: 200px;
            height: 200px;
            background-color: lightblue;
            margin: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s;
        }
        .box.large {
            width: 300px;
            height: 300px;
        }
        .box.blue {
            background-color: blue;
            color: white;
        }
    </style>
</head>
<body>
    <h1>Interactive Features Demo</h1>
    
    <div class="box" id="interactive-box">Hover or Click Me!</div>
    
    <button id="size-btn">Change Size</button>
    <button id="color-btn">Change Color</button>
    <button id="text-btn">Change Text</button>
    
    <script>
        // Your JavaScript code goes here
    </script>
</body>
</html>
```

2. **Add interactivity to change the box size:**
```javascript
let sizeBtn = document.getElementById("size-btn");
let box = document.getElementById("interactive-box");

sizeBtn.addEventListener("click", function() {
    box.classList.toggle("large");
});
```

3. **Add interactivity to change the box color:**
```javascript
let colorBtn = document.getElementById("color-btn");

colorBtn.addEventListener("click", function() {
    box.classList.toggle("blue");
});
```

4. **Add interactivity to change the text:**
```javascript
let textBtn = document.getElementById("text-btn");
let messages = ["Hello!", "How are you?", "Great to see you!", "Click again!"];
let messageIndex = 0;

textBtn.addEventListener("click", function() {
    box.textContent = messages[messageIndex];
    messageIndex = (messageIndex + 1) % messages.length;
});
```

---

## 🚀 Challenge: Build a Theme Switcher

Create a button that switches between light and dark themes:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Theme Switcher</title>
    <style>
        body {
            padding: 20px;
            transition: background-color 0.3s, color 0.3s;
        }
        body.light {
            background-color: white;
            color: black;
        }
        body.dark {
            background-color: #333;
            color: white;
        }
        button {
            padding: 10px 20px;
            font-size: 16px;
            cursor: pointer;
        }
    </style>
</head>
<body class="light">
    <h1>Theme Switcher</h1>
    <p>Click the button to switch between light and dark themes.</p>
    <button id="theme-btn">Switch to Dark Mode</button>
    
    <script>
        let themeBtn = document.getElementById("theme-btn");
        let body = document.body;
        
        themeBtn.addEventListener("click", function() {
            if (body.classList.contains("light")) {
                body.classList.remove("light");
                body.classList.add("dark");
                themeBtn.textContent = "Switch to Light Mode";
            } else {
                body.classList.remove("dark");
                body.classList.add("light");
                themeBtn.textContent = "Switch to Dark Mode";
            }
        });
    </script>
</body>
</html>
```

---

## 🎯 Additional Challenge: Interactive Image Gallery

Create an image gallery with next/previous buttons:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Image Gallery</title>
    <style>
        .gallery {
            text-align: center;
        }
        .gallery img {
            max-width: 500px;
            height: auto;
            margin: 20px;
        }
        button {
            padding: 10px 20px;
            font-size: 16px;
            margin: 10px;
        }
    </style>
</head>
<body>
    <div class="gallery">
        <h1>Image Gallery</h1>
        <img id="gallery-image" src="image1.jpg" alt="Gallery Image">
        <br>
        <button id="prev-btn">Previous</button>
        <button id="next-btn">Next</button>
        <p>Image <span id="image-number">1</span> of <span id="total-images">3</span></p>
    </div>
    
    <script>
        let images = ["image1.jpg", "image2.jpg", "image3.jpg"];
        let currentIndex = 0;
        let galleryImage = document.getElementById("gallery-image");
        let imageNumber = document.getElementById("image-number");
        let totalImages = document.getElementById("total-images");
        let prevBtn = document.getElementById("prev-btn");
        let nextBtn = document.getElementById("next-btn");
        
        totalImages.textContent = images.length;
        
        function updateImage() {
            galleryImage.src = images[currentIndex];
            imageNumber.textContent = currentIndex + 1;
        }
        
        nextBtn.addEventListener("click", function() {
            currentIndex = (currentIndex + 1) % images.length;
            updateImage();
        });
        
        prevBtn.addEventListener("click", function() {
            currentIndex = (currentIndex - 1 + images.length) % images.length;
            updateImage();
        });
    </script>
</body>
</html>
```

---

Excellent progress! You've learned how to create interactive features. In the next session, we'll combine all these concepts to build a complete interactive webpage.
