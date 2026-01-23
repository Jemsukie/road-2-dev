[👈 Go Back](../lvl1.md)

# Week 5 • Day 1: 🖱️ Event Handling

## Lecture Overview:
In this session, we will learn how to handle events in JavaScript. Events are actions that occur in the browser, such as clicks, form submissions, and keyboard input. You'll discover how to listen for these events and respond to them, making your web pages interactive and responsive to user actions.

---

## Key Concepts:

### 1. What are Events? 🎯
Events are actions or occurrences that happen in the browser, such as:
- **Click events**: When a user clicks a button or link
- **Form events**: When a user submits a form or changes input values
- **Keyboard events**: When a user presses keys
- **Mouse events**: When a user moves or hovers over elements
- **Window events**: When the page loads or the window is resized

- **Why are events important?**  
  Events allow you to create interactive web pages that respond to user actions, making your websites dynamic and engaging.

---

### 2. Adding Event Listeners 👂

Event listeners are functions that wait for a specific event to occur and then execute code in response.

#### Basic Syntax:
```javascript
element.addEventListener("event-type", function() {
    // Code to execute when event occurs
});
```

#### Example: Click Event
```javascript
let button = document.getElementById("my-button");

button.addEventListener("click", function() {
    console.log("Button was clicked!");
    alert("Hello from the button!");
});
```

---

### 3. Common Event Types 📋

#### Click Events:
```javascript
let button = document.querySelector("button");
button.addEventListener("click", function() {
    console.log("Button clicked!");
});
```

#### Form Events:
```javascript
let form = document.querySelector("form");
form.addEventListener("submit", function(event) {
    event.preventDefault(); // Prevents form from submitting
    console.log("Form submitted!");
});
```

#### Input Events:
```javascript
let input = document.querySelector("input");
input.addEventListener("input", function() {
    console.log("Input value changed:", input.value);
});
```

#### Change Events:
```javascript
let select = document.querySelector("select");
select.addEventListener("change", function() {
    console.log("Selection changed:", select.value);
});
```

#### Mouse Events:
```javascript
let element = document.querySelector(".box");

element.addEventListener("mouseenter", function() {
    console.log("Mouse entered the element");
});

element.addEventListener("mouseleave", function() {
    console.log("Mouse left the element");
});
```

#### Keyboard Events:
```javascript
document.addEventListener("keydown", function(event) {
    console.log("Key pressed:", event.key);
});
```

---

### 4. Event Object 📦

When an event occurs, JavaScript creates an event object that contains information about the event.

```javascript
let button = document.querySelector("button");

button.addEventListener("click", function(event) {
    console.log("Event type:", event.type);
    console.log("Target element:", event.target);
    console.log("Mouse X position:", event.clientX);
    console.log("Mouse Y position:", event.clientY);
});
```

#### Preventing Default Behavior:
```javascript
let link = document.querySelector("a");

link.addEventListener("click", function(event) {
    event.preventDefault(); // Prevents the link from navigating
    console.log("Link clicked but navigation prevented");
});
```

---

### 5. Multiple Event Listeners 🔄

You can add multiple event listeners to the same element:

```javascript
let button = document.querySelector("button");

button.addEventListener("click", function() {
    console.log("First click handler");
});

button.addEventListener("click", function() {
    console.log("Second click handler");
});
```

---

### 6. Removing Event Listeners 🗑️

You can remove event listeners using `removeEventListener`:

```javascript
function handleClick() {
    console.log("Button clicked!");
}

let button = document.querySelector("button");
button.addEventListener("click", handleClick);

// Later, remove the event listener
button.removeEventListener("click", handleClick);
```

---

## 🛠️ Hands-On Activity: Implement Event Listeners for Interactive Elements

### Instructions:
1. **Create a new HTML file** with the following structure:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Event Handling Practice</title>
    <style>
        button {
            padding: 10px 20px;
            font-size: 16px;
            margin: 10px;
            cursor: pointer;
        }
        .box {
            width: 200px;
            height: 200px;
            background-color: lightblue;
            margin: 20px;
        }
    </style>
</head>
<body>
    <h1>Event Handling Examples</h1>
    
    <button id="click-btn">Click Me!</button>
    <button id="alert-btn">Show Alert</button>
    
    <div class="box" id="hover-box">Hover over me!</div>
    
    <form id="my-form">
        <input type="text" id="name-input" placeholder="Enter your name">
        <button type="submit">Submit</button>
    </form>
    
    <script>
        // Your JavaScript code goes here
    </script>
</body>
</html>
```

2. **Add a click event listener to the button:**
```javascript
let clickBtn = document.getElementById("click-btn");
clickBtn.addEventListener("click", function() {
    console.log("Button was clicked!");
    clickBtn.textContent = "Clicked!";
});
```

3. **Add a form submit event listener:**
```javascript
let form = document.getElementById("my-form");
form.addEventListener("submit", function(event) {
    event.preventDefault();
    let name = document.getElementById("name-input").value;
    alert("Hello, " + name + "!");
});
```

4. **Add mouse event listeners:**
```javascript
let hoverBox = document.getElementById("hover-box");
hoverBox.addEventListener("mouseenter", function() {
    hoverBox.style.backgroundColor = "lightgreen";
});

hoverBox.addEventListener("mouseleave", function() {
    hoverBox.style.backgroundColor = "lightblue";
});
```

---

## 🚀 Challenge: Build an Interactive Button Counter

Create a counter that increases when a button is clicked:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Button Counter</title>
</head>
<body>
    <h1>Click Counter</h1>
    <p>Count: <span id="count">0</span></p>
    <button id="increment-btn">Click to Count</button>
    <button id="reset-btn">Reset</button>
    
    <script>
        let count = 0;
        let countDisplay = document.getElementById("count");
        let incrementBtn = document.getElementById("increment-btn");
        let resetBtn = document.getElementById("reset-btn");
        
        incrementBtn.addEventListener("click", function() {
            count++;
            countDisplay.textContent = count;
        });
        
        resetBtn.addEventListener("click", function() {
            count = 0;
            countDisplay.textContent = count;
        });
    </script>
</body>
</html>
```

---

## 🎯 Additional Challenge: Interactive Form Validation

Create a form that validates input in real-time:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Form Validation</title>
    <style>
        .error {
            color: red;
        }
        .success {
            color: green;
        }
    </style>
</head>
<body>
    <h1>Sign Up Form</h1>
    <form id="signup-form">
        <input type="text" id="username" placeholder="Username" required>
        <span id="username-error"></span>
        <br><br>
        
        <input type="email" id="email" placeholder="Email" required>
        <span id="email-error"></span>
        <br><br>
        
        <button type="submit">Submit</button>
    </form>
    
    <script>
        let usernameInput = document.getElementById("username");
        let emailInput = document.getElementById("email");
        let usernameError = document.getElementById("username-error");
        let emailError = document.getElementById("email-error");
        
        usernameInput.addEventListener("input", function() {
            if (usernameInput.value.length < 3) {
                usernameError.textContent = "Username must be at least 3 characters";
                usernameError.className = "error";
            } else {
                usernameError.textContent = "✓ Valid username";
                usernameError.className = "success";
            }
        });
        
        emailInput.addEventListener("input", function() {
            let email = emailInput.value;
            if (email.includes("@") && email.includes(".")) {
                emailError.textContent = "✓ Valid email";
                emailError.className = "success";
            } else {
                emailError.textContent = "Please enter a valid email";
                emailError.className = "error";
            }
        });
        
        let form = document.getElementById("signup-form");
        form.addEventListener("submit", function(event) {
            event.preventDefault();
            alert("Form submitted successfully!");
        });
    </script>
</body>
</html>
```

---

Great job! You've learned how to handle events in JavaScript. In the next session, we'll explore how to create more interactive features by changing styles and content dynamically.
