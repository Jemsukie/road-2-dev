[👈 Go Back](../lvl1.md)

# Week 4 • Day 2: 🛠️ Functions and Control Flow

## Lecture Overview:
In this session, we will learn about functions and control flow in JavaScript. You'll discover how to define and use functions, work with conditional statements, and implement loops to create more dynamic and interactive scripts. By the end of this lesson, you'll be able to write scripts that can make decisions and repeat actions.

---

## Key Concepts:

### 1. What are Functions? 🔧
Functions are reusable blocks of code that perform a specific task. They help you organize your code and avoid repetition.

- **Why use functions?**  
  Functions make your code more organized, reusable, and easier to maintain. Instead of writing the same code multiple times, you can define it once and call it whenever needed.

---

### 2. Defining Functions 📝

There are several ways to define functions in JavaScript:

#### Function Declaration:
```javascript
function greet(name) {
    return "Hello, " + name + "!";
}
```

#### Function Expression:
```javascript
const greet = function(name) {
    return "Hello, " + name + "!";
};
```

#### Arrow Function (ES6):
```javascript
const greet = (name) => {
    return "Hello, " + name + "!";
};
```

**Calling a function:**
```javascript
let message = greet("Alice");
console.log(message); // Output: "Hello, Alice!"
```

---

### 3. Conditional Statements 🎯

Conditional statements allow your code to make decisions based on different conditions.

#### if/else Statement:
```javascript
let age = 18;

if (age >= 18) {
    console.log("You are an adult.");
} else {
    console.log("You are a minor.");
}
```

#### if/else if/else Statement:
```javascript
let score = 85;

if (score >= 90) {
    console.log("Grade: A");
} else if (score >= 80) {
    console.log("Grade: B");
} else if (score >= 70) {
    console.log("Grade: C");
} else {
    console.log("Grade: F");
}
```

#### Switch Statement:
```javascript
let day = "Monday";

switch(day) {
    case "Monday":
        console.log("Start of the work week!");
        break;
    case "Friday":
        console.log("TGIF!");
        break;
    default:
        console.log("It's a regular day.");
}
```

---

### 4. Loops 🔄

Loops allow you to repeat a block of code multiple times.

#### for Loop:
```javascript
for (let i = 0; i < 5; i++) {
    console.log("Count: " + i);
}
// Output: Count: 0, Count: 1, Count: 2, Count: 3, Count: 4
```

#### while Loop:
```javascript
let count = 0;
while (count < 5) {
    console.log("Count: " + count);
    count++;
}
```

#### for...of Loop (for arrays):
```javascript
let fruits = ["apple", "banana", "orange"];

for (let fruit of fruits) {
    console.log(fruit);
}
// Output: apple, banana, orange
```

---

### 5. Combining Functions and Control Flow 💡

You can combine functions with conditional statements and loops to create powerful scripts:

```javascript
function checkNumber(num) {
    if (num > 0) {
        return "Positive";
    } else if (num < 0) {
        return "Negative";
    } else {
        return "Zero";
    }
}

let numbers = [5, -3, 0, 10, -7];
for (let num of numbers) {
    console.log(num + " is " + checkNumber(num));
}
```

---

## 🛠️ Hands-On Activity: Create a Script with Functions and Control Flow

### Instructions:
1. Open your browser's DevTools Console (Right-click > Inspect > Console tab).

2. **Create a function that calculates the area of a rectangle:**
```javascript
function calculateArea(length, width) {
    return length * width;
}

let area = calculateArea(5, 3);
console.log("Area: " + area);
```

3. **Create a function that checks if a number is even or odd:**
```javascript
function checkEvenOdd(num) {
    if (num % 2 === 0) {
        return "Even";
    } else {
        return "Odd";
    }
}

console.log(checkEvenOdd(4)); // Output: Even
console.log(checkEvenOdd(7)); // Output: Odd
```

4. **Use a loop to process an array of numbers:**
```javascript
let numbers = [1, 2, 3, 4, 5];
let sum = 0;

for (let num of numbers) {
    sum += num;
}

console.log("Sum: " + sum);
```

---

## 🚀 Challenge: Build a Simple Calculator

Create a calculator function that can perform basic operations:

```javascript
function calculator(num1, num2, operation) {
    if (operation === "add") {
        return num1 + num2;
    } else if (operation === "subtract") {
        return num1 - num2;
    } else if (operation === "multiply") {
        return num1 * num2;
    } else if (operation === "divide") {
        if (num2 !== 0) {
            return num1 / num2;
        } else {
            return "Cannot divide by zero!";
        }
    } else {
        return "Invalid operation";
    }
}

// Test your calculator
console.log(calculator(10, 5, "add"));      // Output: 15
console.log(calculator(10, 5, "subtract")); // Output: 5
console.log(calculator(10, 5, "multiply")); // Output: 50
console.log(calculator(10, 5, "divide"));   // Output: 2
```

---

## 🎯 Additional Challenge: Grade Calculator

Create a function that takes an array of scores and returns the average grade:

```javascript
function calculateAverage(scores) {
    let sum = 0;
    for (let score of scores) {
        sum += score;
    }
    return sum / scores.length;
}

function getGrade(average) {
    if (average >= 90) return "A";
    if (average >= 80) return "B";
    if (average >= 70) return "C";
    if (average >= 60) return "D";
    return "F";
}

let studentScores = [85, 92, 78, 90, 88];
let average = calculateAverage(studentScores);
let grade = getGrade(average);

console.log("Average: " + average);
console.log("Grade: " + grade);
```

---

Stay curious and keep practicing — functions and control flow are the building blocks of interactive programming!
