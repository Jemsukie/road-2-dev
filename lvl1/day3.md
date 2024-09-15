[👈 Go Back](./lvl1.md)

# Week 1 • Day 3: 🖊️ HTML Forms

## Lecture Overview:
In today's session, we will dive into HTML forms and input elements. Forms are crucial for gathering user input, whether it's for logging in, submitting contact details, or filling out surveys. By the end of the session, you will be able to create a functional contact form using various input types.

## Key Concepts:
- The purpose of HTML forms.
- Common form elements and attributes.
- Input types: text, email, password, radio, checkbox.
- Form submission and the `action` attribute.

---

## 🌐 What are HTML Forms?

HTML forms are a way for users to interact with a webpage by submitting data to a server. Forms use the `<form>` element to contain input fields where users can type information or select options.

---

## 🏗️ Basic HTML Form Structure

Every form starts with a `<form>` element, which contains various input elements like text fields, checkboxes, and buttons. Here's a simple form structure:

```html
<form action="/submit" method="post">
    <label for="name">Name:</label>
    <input type="text" id="name" name="name" required>
    <br><br>
    
    <label for="email">Email:</label>
    <input type="email" id="email" name="email" required>
    <br><br>
    
    <label for="message">Message:</label>
    <textarea id="message" name="message"></textarea>
    <br><br>
    
    <button type="submit">Submit</button>
</form>
```

## Breakdown:
- `<form>`: Defines the form and its action (where the data goes upon submission).
- `<label>`: Describes the input field to the user.
- `<input>`: Collects user input. Common types include text, email, password.
- `<textarea>`: Used for larger text input, such as a message.
- `<button>`: Submits the form when clicked.

## Common Form Input Types
Forms can include various types of inputs depending on the data you're collecting:

### 1. Text Input (type="text")
```html
<input type="text" name="username" placeholder="Enter your name">
```

### 2. Email Input (type="email")
```html
<input type="email" name="email" placeholder="Enter your email">
```

### 3. Password Input (type="password")
```html
<input type="password" name="password" placeholder="Enter your password">
```

### 4. Radio Buttons (type="radio")
```html
<label>
  <input type="radio" name="gender" value="male"> Male
</label>
<label>
  <input type="radio" name="gender" value="female"> Female
</label>
```

### 5. Checkboxes (type="checkbox")
```html
<label>
  <input type="checkbox" name="subscribe" value="newsletter"> Subscribe to Newsletter
</label>
```

## 🎯 Hands-On Activity: Create Your First HTML Page

### Instructions:
1. Open your text editor and create a new HTML file.
2. Copy and paste the following code to create a simple contact form:
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Contact Form</title>
</head>
<body>

    <h1>Contact Us</h1>

    <form action="/submit" method="post">
        <label for="name">Name:</label>
        <input type="text" id="name" name="name" required>
        <br><br>
        
        <label for="email">Email:</label>
        <input type="email" id="email" name="email" required>
        <br><br>
        
        <label for="message">Message:</label>
        <textarea id="message" name="message" placeholder="Write your message here..."></textarea>
        <br><br>
        
        <button type="submit">Submit</button>
    </form>

</body>
</html>
```
3. Save the file as contact_form.html and open it in your browser.
4. Experiment by filling out the form fields and submitting the data.
