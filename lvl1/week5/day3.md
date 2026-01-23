[👈 Go Back](../lvl1.md)

# Week 5 • Day 3: 🎛️ Combining JavaScript with HTML/CSS

## Lecture Overview:
In this session, we will integrate everything you've learned about JavaScript, HTML, and CSS to create dynamic and interactive web pages. You'll learn how to combine these technologies effectively, manipulate CSS classes dynamically, and build complete interactive features that respond to user actions.

---

## Key Concepts:

### 1. Integrating JavaScript with HTML/CSS 🔗

JavaScript works seamlessly with HTML and CSS to create interactive web experiences. The key is understanding how to:
- Select HTML elements
- Modify CSS properties and classes
- Respond to user events
- Update content dynamically

**The Integration Flow:**
```
HTML (Structure) + CSS (Styling) + JavaScript (Behavior) = Interactive Web Page
```

---

### 2. Dynamic Styling with JavaScript 🎨

You can change styles in multiple ways:

#### Direct Style Manipulation:
```javascript
let element = document.querySelector(".box");
element.style.backgroundColor = "blue";
element.style.width = "300px";
element.style.borderRadius = "10px";
```

#### Class-Based Styling (Recommended):
This approach is cleaner and more maintainable:

**CSS:**
```css
.box {
    width: 200px;
    height: 200px;
    background-color: lightblue;
    transition: all 0.3s;
}

.box.active {
    background-color: green;
    transform: scale(1.2);
}

.box.highlight {
    box-shadow: 0 4px 8px rgba(0,0,0,0.3);
}
```

**JavaScript:**
```javascript
let box = document.querySelector(".box");
box.classList.add("active");
box.classList.add("highlight");
```

---

### 3. Manipulating Multiple Elements 🔄

You can select and modify multiple elements at once:

```javascript
// Select all elements with class "item"
let items = document.querySelectorAll(".item");

// Loop through and modify each
items.forEach(function(item, index) {
    item.style.backgroundColor = index % 2 === 0 ? "lightblue" : "lightgreen";
    item.addEventListener("click", function() {
        item.classList.toggle("selected");
    });
});
```

---

### 4. Creating Interactive Components 🧩

Combine HTML structure, CSS styling, and JavaScript behavior to create reusable components:

#### Example: Interactive Button Component

**HTML:**
```html
<button class="interactive-btn" data-action="toggle">
    Click Me
</button>
```

**CSS:**
```css
.interactive-btn {
    padding: 10px 20px;
    background-color: #4CAF50;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: all 0.3s;
}

.interactive-btn:hover {
    background-color: #45a049;
    transform: translateY(-2px);
}

.interactive-btn.active {
    background-color: #f44336;
}
```

**JavaScript:**
```javascript
let button = document.querySelector(".interactive-btn");

button.addEventListener("click", function() {
    button.classList.toggle("active");
    if (button.classList.contains("active")) {
        button.textContent = "Active!";
    } else {
        button.textContent = "Click Me";
    }
});
```

---

### 5. Complete Example: Interactive Card Component

Here's a complete example that demonstrates all concepts:

**HTML:**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Card</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="card" id="card">
        <h2 id="card-title">Interactive Card</h2>
        <p id="card-description">This card responds to user interactions.</p>
        <button id="toggle-btn">Toggle Style</button>
        <button id="color-btn">Change Color</button>
    </div>
    
    <script src="script.js"></script>
</body>
</html>
```

**CSS (styles.css):**
```css
body {
    font-family: Arial, sans-serif;
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    margin: 0;
    background-color: #f0f0f0;
}

.card {
    width: 300px;
    padding: 30px;
    background-color: white;
    border-radius: 10px;
    box-shadow: 0 2px 10px rgba(0,0,0,0.1);
    transition: all 0.3s;
}

.card.expanded {
    width: 400px;
    padding: 40px;
}

.card.blue-theme {
    background-color: #e3f2fd;
    border: 2px solid #2196F3;
}

.card.green-theme {
    background-color: #e8f5e9;
    border: 2px solid #4CAF50;
}

button {
    padding: 10px 20px;
    margin: 5px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    background-color: #2196F3;
    color: white;
    transition: background-color 0.3s;
}

button:hover {
    background-color: #1976D2;
}
```

**JavaScript (script.js):**
```javascript
let card = document.getElementById("card");
let toggleBtn = document.getElementById("toggle-btn");
let colorBtn = document.getElementById("color-btn");
let cardTitle = document.getElementById("card-title");

let themes = ["blue-theme", "green-theme"];
let currentTheme = 0;

toggleBtn.addEventListener("click", function() {
    card.classList.toggle("expanded");
    if (card.classList.contains("expanded")) {
        cardTitle.textContent = "Expanded Card";
    } else {
        cardTitle.textContent = "Interactive Card";
    }
});

colorBtn.addEventListener("click", function() {
    // Remove current theme
    card.classList.remove(themes[currentTheme]);
    
    // Switch to next theme
    currentTheme = (currentTheme + 1) % themes.length;
    card.classList.add(themes[currentTheme]);
});
```

---

## 🛠️ Hands-On Activity: Enhance a Webpage with JavaScript

### Instructions:
1. **Create a complete HTML file** with structure, styling, and interactivity:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Enhanced Webpage</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
        }
        
        .header {
            background-color: #333;
            color: white;
            padding: 20px;
            text-align: center;
        }
        
        .content {
            padding: 20px;
            background-color: #f9f9f9;
            margin: 20px 0;
            border-radius: 5px;
        }
        
        .button-group {
            display: flex;
            gap: 10px;
            margin: 20px 0;
        }
        
        button {
            padding: 10px 20px;
            background-color: #4CAF50;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        
        button:hover {
            background-color: #45a049;
        }
        
        .hidden {
            display: none;
        }
        
        .highlight {
            background-color: yellow;
            padding: 5px;
        }
    </style>
</head>
<body>
    <div class="header">
        <h1 id="main-title">My Enhanced Webpage</h1>
    </div>
    
    <div class="content">
        <p id="description">This webpage demonstrates JavaScript integration with HTML and CSS.</p>
        <div class="button-group">
            <button id="change-title-btn">Change Title</button>
            <button id="highlight-btn">Highlight Text</button>
            <button id="hide-btn">Toggle Visibility</button>
        </div>
    </div>
    
    <script>
        // Your JavaScript code goes here
    </script>
</body>
</html>
```

2. **Add JavaScript to change the title:**
```javascript
let changeTitleBtn = document.getElementById("change-title-btn");
let mainTitle = document.getElementById("main-title");
let titles = ["My Enhanced Webpage", "Interactive Page", "Dynamic Content", "JavaScript Demo"];
let titleIndex = 0;

changeTitleBtn.addEventListener("click", function() {
    titleIndex = (titleIndex + 1) % titles.length;
    mainTitle.textContent = titles[titleIndex];
});
```

3. **Add JavaScript to highlight text:**
```javascript
let highlightBtn = document.getElementById("highlight-btn");
let description = document.getElementById("description");

highlightBtn.addEventListener("click", function() {
    description.classList.toggle("highlight");
});
```

4. **Add JavaScript to toggle visibility:**
```javascript
let hideBtn = document.getElementById("hide-btn");
let content = document.querySelector(".content");

hideBtn.addEventListener("click", function() {
    if (content.style.display === "none") {
        content.style.display = "block";
        hideBtn.textContent = "Hide Content";
    } else {
        content.style.display = "none";
        hideBtn.textContent = "Show Content";
    }
});
```

---

## 🚀 Challenge: Build a Complete Interactive Dashboard

Create a dashboard with multiple interactive features:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Dashboard</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: Arial, sans-serif;
            background-color: #f5f5f5;
        }
        
        .dashboard {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        .header {
            background-color: #333;
            color: white;
            padding: 20px;
            border-radius: 5px;
            margin-bottom: 20px;
        }
        
        .stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-bottom: 20px;
        }
        
        .stat-card {
            background-color: white;
            padding: 20px;
            border-radius: 5px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
            text-align: center;
        }
        
        .stat-card h3 {
            color: #666;
            margin-bottom: 10px;
        }
        
        .stat-card .value {
            font-size: 32px;
            font-weight: bold;
            color: #2196F3;
        }
        
        .controls {
            background-color: white;
            padding: 20px;
            border-radius: 5px;
            margin-bottom: 20px;
        }
        
        button {
            padding: 10px 20px;
            margin: 5px;
            background-color: #2196F3;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        
        button:hover {
            background-color: #1976D2;
        }
        
        .theme-dark {
            background-color: #1a1a1a;
            color: white;
        }
        
        .theme-dark .stat-card,
        .theme-dark .controls {
            background-color: #2a2a2a;
        }
    </style>
</head>
<body>
    <div class="dashboard">
        <div class="header">
            <h1>Interactive Dashboard</h1>
            <button id="theme-toggle">Toggle Theme</button>
        </div>
        
        <div class="stats">
            <div class="stat-card">
                <h3>Users</h3>
                <div class="value" id="users-count">0</div>
            </div>
            <div class="stat-card">
                <h3>Views</h3>
                <div class="value" id="views-count">0</div>
            </div>
            <div class="stat-card">
                <h3>Revenue</h3>
                <div class="value" id="revenue-count">$0</div>
            </div>
        </div>
        
        <div class="controls">
            <h2>Controls</h2>
            <button id="increment-users">+ Users</button>
            <button id="increment-views">+ Views</button>
            <button id="increment-revenue">+ Revenue</button>
            <button id="reset-all">Reset All</button>
        </div>
    </div>
    
    <script>
        let usersCount = 0;
        let viewsCount = 0;
        let revenueCount = 0;
        
        let usersDisplay = document.getElementById("users-count");
        let viewsDisplay = document.getElementById("views-count");
        let revenueDisplay = document.getElementById("revenue-count");
        
        let themeToggle = document.getElementById("theme-toggle");
        let body = document.body;
        
        function updateDisplays() {
            usersDisplay.textContent = usersCount;
            viewsDisplay.textContent = viewsCount;
            revenueDisplay.textContent = "$" + revenueCount;
        }
        
        document.getElementById("increment-users").addEventListener("click", function() {
            usersCount++;
            updateDisplays();
        });
        
        document.getElementById("increment-views").addEventListener("click", function() {
            viewsCount += 10;
            updateDisplays();
        });
        
        document.getElementById("increment-revenue").addEventListener("click", function() {
            revenueCount += 100;
            updateDisplays();
        });
        
        document.getElementById("reset-all").addEventListener("click", function() {
            usersCount = 0;
            viewsCount = 0;
            revenueCount = 0;
            updateDisplays();
        });
        
        themeToggle.addEventListener("click", function() {
            body.classList.toggle("theme-dark");
        });
    </script>
</body>
</html>
```

---

## 🎯 Additional Challenge: Build a Todo List App

Create a complete todo list application:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Todo List</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            max-width: 600px;
            margin: 50px auto;
            padding: 20px;
        }
        
        .todo-container {
            background-color: #f9f9f9;
            padding: 20px;
            border-radius: 10px;
        }
        
        input[type="text"] {
            width: 70%;
            padding: 10px;
            font-size: 16px;
        }
        
        button {
            padding: 10px 20px;
            background-color: #4CAF50;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        
        ul {
            list-style-type: none;
            padding: 0;
        }
        
        li {
            background-color: white;
            padding: 10px;
            margin: 5px 0;
            border-radius: 5px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .completed {
            text-decoration: line-through;
            opacity: 0.6;
        }
        
        .delete-btn {
            background-color: #f44336;
            padding: 5px 10px;
            font-size: 12px;
        }
    </style>
</head>
<body>
    <div class="todo-container">
        <h1>My Todo List</h1>
        <input type="text" id="todo-input" placeholder="Enter a new task">
        <button id="add-btn">Add Task</button>
        <ul id="todo-list"></ul>
    </div>
    
    <script>
        let todoInput = document.getElementById("todo-input");
        let addBtn = document.getElementById("add-btn");
        let todoList = document.getElementById("todo-list");
        
        addBtn.addEventListener("click", function() {
            let taskText = todoInput.value.trim();
            if (taskText !== "") {
                let li = document.createElement("li");
                li.innerHTML = `
                    <span>${taskText}</span>
                    <button class="delete-btn">Delete</button>
                `;
                
                li.querySelector("span").addEventListener("click", function() {
                    li.querySelector("span").classList.toggle("completed");
                });
                
                li.querySelector(".delete-btn").addEventListener("click", function() {
                    li.remove();
                });
                
                todoList.appendChild(li);
                todoInput.value = "";
            }
        });
        
        todoInput.addEventListener("keypress", function(event) {
            if (event.key === "Enter") {
                addBtn.click();
            }
        });
    </script>
</body>
</html>
```

---

Congratulations! You've successfully learned how to combine JavaScript, HTML, and CSS to create dynamic and interactive web pages. You're now ready to build your own projects!
