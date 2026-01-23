[👈 Go Back](../lvl1.md)

# Week 6 • Day 2: 🔨 Project Implementation (Part 1)

## Lecture Overview:
In this session, we will begin building your personal portfolio website. You'll start by creating the HTML structure, then add CSS styling, and finally integrate JavaScript for interactivity. We'll focus on setting up the foundation and implementing the core sections of your portfolio.

---

## Key Concepts:

### 1. Setting Up the Project 🏗️

Before coding, set up your project structure:

#### Create Project Folder:
```
my-portfolio/
├── index.html
├── styles.css
├── script.js
└── images/
    └── (your images here)
```

#### Basic HTML Structure:
Start with a clean HTML5 template:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Portfolio</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <!-- Your content goes here -->
    <script src="script.js"></script>
</body>
</html>
```

---

### 2. Building the HTML Structure 📄

Create semantic HTML for each section:

#### Header/Navigation:
```html
<header>
    <nav>
        <div class="logo">My Portfolio</div>
        <ul class="nav-links">
            <li><a href="#home">Home</a></li>
            <li><a href="#about">About</a></li>
            <li><a href="#skills">Skills</a></li>
            <li><a href="#projects">Projects</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </nav>
</header>
```

#### Hero Section:
```html
<section id="home" class="hero">
    <h1>Welcome to My Portfolio</h1>
    <p>I'm a Web Developer</p>
    <button class="cta-button">View My Work</button>
</section>
```

#### About Section:
```html
<section id="about" class="about">
    <h2>About Me</h2>
    <div class="about-content">
        <p>Your bio text goes here...</p>
    </div>
</section>
```

#### Skills Section:
```html
<section id="skills" class="skills">
    <h2>My Skills</h2>
    <div class="skills-grid">
        <div class="skill-item">
            <h3>HTML</h3>
            <p>Structure and semantics</p>
        </div>
        <div class="skill-item">
            <h3>CSS</h3>
            <p>Styling and layout</p>
        </div>
        <div class="skill-item">
            <h3>JavaScript</h3>
            <p>Interactivity and functionality</p>
        </div>
    </div>
</section>
```

#### Projects Section:
```html
<section id="projects" class="projects">
    <h2>My Projects</h2>
    <div class="projects-grid">
        <div class="project-card">
            <h3>Project 1</h3>
            <p>Description of your project...</p>
            <a href="#" class="project-link">View Project</a>
        </div>
        <div class="project-card">
            <h3>Project 2</h3>
            <p>Description of your project...</p>
            <a href="#" class="project-link">View Project</a>
        </div>
    </div>
</section>
```

#### Contact Section:
```html
<section id="contact" class="contact">
    <h2>Get In Touch</h2>
    <div class="contact-content">
        <p>Feel free to reach out!</p>
        <div class="social-links">
            <a href="#">Email</a>
            <a href="#">LinkedIn</a>
            <a href="#">GitHub</a>
        </div>
    </div>
</section>
```

#### Footer:
```html
<footer>
    <p>&copy; 2024 My Portfolio. All rights reserved.</p>
</footer>
```

---

### 3. Adding Basic CSS Styling 🎨

Start with a CSS reset and basic styling:

```css
/* Reset and Base Styles */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    line-height: 1.6;
    color: #333;
}

/* Header Styles */
header {
    background-color: #333;
    color: white;
    padding: 1rem;
    position: fixed;
    width: 100%;
    top: 0;
    z-index: 1000;
}

nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    max-width: 1200px;
    margin: 0 auto;
}

.nav-links {
    display: flex;
    list-style: none;
    gap: 2rem;
}

.nav-links a {
    color: white;
    text-decoration: none;
    transition: color 0.3s;
}

.nav-links a:hover {
    color: #4CAF50;
}

/* Hero Section */
.hero {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    background-color: #f0f0f0;
    padding-top: 80px;
}

.hero h1 {
    font-size: 3rem;
    margin-bottom: 1rem;
}

.cta-button {
    padding: 12px 30px;
    background-color: #4CAF50;
    color: white;
    border: none;
    border-radius: 5px;
    font-size: 1rem;
    cursor: pointer;
    transition: background-color 0.3s;
}

.cta-button:hover {
    background-color: #45a049;
}

/* Section Styles */
section {
    padding: 80px 20px;
    max-width: 1200px;
    margin: 0 auto;
}

section h2 {
    text-align: center;
    font-size: 2.5rem;
    margin-bottom: 3rem;
}

/* Skills Grid */
.skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 2rem;
}

.skill-item {
    background-color: #f9f9f9;
    padding: 2rem;
    border-radius: 10px;
    text-align: center;
}

/* Projects Grid */
.projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 2rem;
}

.project-card {
    background-color: white;
    padding: 2rem;
    border-radius: 10px;
    box-shadow: 0 2px 10px rgba(0,0,0,0.1);
}

.project-link {
    display: inline-block;
    margin-top: 1rem;
    color: #4CAF50;
    text-decoration: none;
}

/* Footer */
footer {
    background-color: #333;
    color: white;
    text-align: center;
    padding: 2rem;
}
```

---

### 4. Making It Responsive 📱

Add media queries for mobile devices:

```css
/* Responsive Design */
@media (max-width: 768px) {
    .nav-links {
        flex-direction: column;
        gap: 1rem;
    }
    
    .hero h1 {
        font-size: 2rem;
    }
    
    .skills-grid,
    .projects-grid {
        grid-template-columns: 1fr;
    }
}
```

---

### 5. Adding Basic JavaScript Interactivity ⚡

Add smooth scrolling and basic interactions:

```javascript
// Smooth scrolling for navigation links
document.querySelectorAll('a[href^="#"]').forEach(anchor => {
    anchor.addEventListener('click', function (e) {
        e.preventDefault();
        const target = document.querySelector(this.getAttribute('href'));
        if (target) {
            target.scrollIntoView({
                behavior: 'smooth',
                block: 'start'
            });
        }
    });
});

// CTA Button functionality
const ctaButton = document.querySelector('.cta-button');
if (ctaButton) {
    ctaButton.addEventListener('click', function() {
        document.querySelector('#projects').scrollIntoView({
            behavior: 'smooth'
        });
    });
}
```

---

## 🛠️ Hands-On Activity: Start Building Your Portfolio

### Instructions:
1. **Create your project folder structure:**
   - Create a folder named `my-portfolio`
   - Create `index.html`, `styles.css`, and `script.js`
   - Create an `images` folder

2. **Set up the HTML structure:**
   - Copy the HTML template
   - Add all sections (Header, Hero, About, Skills, Projects, Contact, Footer)
   - Fill in your personal content

3. **Add basic CSS styling:**
   - Start with the reset and base styles
   - Style each section
   - Make it responsive

4. **Add JavaScript:**
   - Implement smooth scrolling
   - Add any interactive features

5. **Test your website:**
   - Open `index.html` in your browser
   - Test on different screen sizes
   - Check that all links work

---

## 🚀 Challenge: Complete the Foundation

Complete these tasks:

1. **HTML Structure:**
   - [ ] Create all sections
   - [ ] Add your personal content
   - [ ] Include proper semantic HTML

2. **CSS Styling:**
   - [ ] Style all sections
   - [ ] Make it responsive
   - [ ] Add hover effects

3. **JavaScript:**
   - [ ] Smooth scrolling navigation
   - [ ] Interactive buttons
   - [ ] Any additional features

4. **Testing:**
   - [ ] Test on desktop
   - [ ] Test on mobile
   - [ ] Fix any issues

---

## 🎯 Tips for Success

- **Start Simple**: Get the basic structure working first
- **Test Frequently**: Check your work in the browser often
- **Use Browser DevTools**: Inspect elements and debug issues
- **Keep It Organized**: Use comments in your code
- **Don't Perfectionist**: You can refine in the next session

---

Great progress! You've built the foundation of your portfolio. In the next session, we'll add final touches, refine the design, and polish your project.
