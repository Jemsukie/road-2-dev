[👈 Go Back](../lvl1.md)

# Week 4 • Day 3: 🌐 JavaScript in the DOM

## Lecture Overview:
In this session, we will explore how JavaScript interacts with the Document Object Model (DOM). You'll learn what the DOM is, how to select elements from a webpage, and how to manipulate them dynamically. By the end of this lesson, you'll be able to write JavaScript that changes content, styles, and structure of web pages in real-time.

---

## Key Concepts:

### 1. What is the DOM? 🌳
The DOM (Document Object Model) is a programming interface that represents the structure of an HTML document as a tree of objects. JavaScript can interact with these objects to change the content, structure, and styling of a webpage.

- **Why is it important?**  
  The DOM allows JavaScript to make web pages interactive and dynamic. Without it, web pages would be static and unresponsive to user actions.

**Visual Representation:**
```
Document (HTML)
  └── html
      ├── head
      │   └── title
      └── body
          ├── h1
          ├── p
          └── div
              └── button
```

---

### 2. Selecting DOM Elements 🎯

Before you can manipulate elements, you need to select them. JavaScript provides several methods to select elements:

#### getElementById:
Selects an element by its unique ID attribute.

```javascript
let heading = document.getElementById("main-heading");
```

**HTML:**
```html
<h1 id="main-heading">Welcome</h1>
```

#### querySelector:
Selects the first element that matches a CSS selector.

```javascript
let paragraph = document.querySelector("p");
let firstDiv = document.querySelector(".container");
let button = document.querySelector("#my-button");
```

#### querySelectorAll:
Selects all elements that match a CSS selector (returns a NodeList).

```javascript
let allParagraphs = document.querySelectorAll("p");
let allButtons = document.querySelectorAll(".btn");
```

#### getElementsByClassName:
Selects all elements with a specific class name.

```javascript
let items = document.getElementsByClassName("item");
```

#### getElementsByTagName:
Selects all elements with a specific tag name.

```javascript
let paragraphs = document.getElementsByTagName("p");
```

---

### 3. Manipulating DOM Elements ✏️

Once you've selected an element, you can change its content, attributes, and styles.

#### Changing Text Content:
```javascript
let heading = document.getElementById("main-heading");
heading.textContent = "New Heading Text";
heading.innerHTML = "<strong>Bold Heading</strong>";
```

#### Changing Attributes:
```javascript
let image = document.querySelector("img");
image.src = "new-image.jpg";
image.alt = "New image description";

let link = document.querySelector("a");
link.href = "https://www.example.com";
```

#### Changing Styles:
```javascript
let paragraph = document.querySelector("p");
paragraph.style.color = "blue";
paragraph.style.fontSize = "20px";
paragraph.style.backgroundColor = "yellow";
```

#### Adding and Removing Classes:
```javascript
let element = document.querySelector(".box");
element.classList.add("highlight");
element.classList.remove("old-class");
element.classList.toggle("active");
```

---

### 4. Creating and Removing Elements 🏗️

You can dynamically create new elements and add them to the DOM, or remove existing ones.

#### Creating Elements:
```javascript
// Create a new paragraph element
let newParagraph = document.createElement("p");
newParagraph.textContent = "This is a new paragraph!";

// Add it to the page
let container = document.getElementById("container");
container.appendChild(newParagraph);
```

#### Removing Elements:
```javascript
let elementToRemove = document.getElementById("old-element");
elementToRemove.remove();
```

---

### 5. Practical Example: Dynamic Content Update

Here's a complete example that demonstrates DOM manipulation:

**HTML:**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DOM Manipulation</title>
</head>
<body>
    <h1 id="title">Hello World</h1>
    <p id="message">Click the button to change me!</p>
    <button id="change-btn">Change Content</button>
    
    <script>
        let button = document.getElementById("change-btn");
        let title = document.getElementById("title");
        let message = document.getElementById("message");
        
        button.addEventListener("click", function() {
            title.textContent = "Content Changed!";
            message.textContent = "The button was clicked!";
            message.style.color = "green";
        });
    </script>
</body>
</html>
```

---

## 🛠️ Hands-On Activity: Write JavaScript to Dynamically Change Webpage Content

### Instructions:
1. **Create a new HTML file** with the following structure:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DOM Practice</title>
    <style>
        .highlight {
            background-color: yellow;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <h1 id="main-heading">Welcome</h1>
    <p id="description">This is a paragraph.</p>
    <button id="update-btn">Update Content</button>
    <div id="container"></div>
    
    <script>
        // Your JavaScript code goes here
    </script>
</body>
</html>
```

2. **Add JavaScript to change the heading:**
```javascript
let heading = document.getElementById("main-heading");
heading.textContent = "Hello, DOM!";
```

3. **Add JavaScript to change the paragraph:**
```javascript
let paragraph = document.getElementById("description");
paragraph.textContent = "This paragraph was changed by JavaScript!";
paragraph.style.color = "blue";
```

4. **Create a function that adds a new element:**
```javascript
function addNewElement() {
    let container = document.getElementById("container");
    let newDiv = document.createElement("div");
    newDiv.textContent = "This is a new element!";
    newDiv.classList.add("highlight");
    container.appendChild(newDiv);
}

// Call the function
addNewElement();
```

---

## 🚀 Challenge: Build an Interactive List

Create a webpage where users can add items to a list dynamically:

**HTML:**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive List</title>
</head>
<body>
    <h1>My To-Do List</h1>
    <input type="text" id="item-input" placeholder="Enter an item">
    <button id="add-btn">Add Item</button>
    <ul id="item-list"></ul>
    
    <script>
        let addButton = document.getElementById("add-btn");
        let input = document.getElementById("item-input");
        let list = document.getElementById("item-list");
        
        addButton.addEventListener("click", function() {
            let itemText = input.value;
            if (itemText.trim() !== "") {
                let listItem = document.createElement("li");
                listItem.textContent = itemText;
                list.appendChild(listItem);
                input.value = ""; // Clear the input
            }
        });
    </script>
</body>
</html>
```

---

## 🎯 Additional Challenge: Counter App

Create a simple counter that increases and decreases a number:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Counter App</title>
</head>
<body>
    <h1>Counter: <span id="count">0</span></h1>
    <button id="increment-btn">+</button>
    <button id="decrement-btn">-</button>
    <button id="reset-btn">Reset</button>
    
    <script>
        let count = 0;
        let countDisplay = document.getElementById("count");
        let incrementBtn = document.getElementById("increment-btn");
        let decrementBtn = document.getElementById("decrement-btn");
        let resetBtn = document.getElementById("reset-btn");
        
        function updateDisplay() {
            countDisplay.textContent = count;
        }
        
        incrementBtn.addEventListener("click", function() {
            count++;
            updateDisplay();
        });
        
        decrementBtn.addEventListener("click", function() {
            count--;
            updateDisplay();
        });
        
        resetBtn.addEventListener("click", function() {
            count = 0;
            updateDisplay();
        });
    </script>
</body>
</html>
```

---

You've now learned how to interact with the DOM! In the next session, we'll explore event handling to make your web pages even more interactive.
