# 🎯 JavaScript Event Handling & Interactive Elements Assignment

Welcome to the **ultimate JavaScript playground**! 🎉 This assignment is where we turn boring web pages into dynamic, responsive, *alive* experiences. Get ready to master **event handling**, build **interactive components**, and validate forms like a pro! 💪

## 📁 Assignment Structure

```
📂 js-event-assignment/
├── index.html         # Your playground – where it all comes together
├── style.css          # Keep it cute (optional but encouraged)
└── script.js          # The JavaScript wizardry happens here
```

---

## 🧪 What to Build

Here’s what your interactive bundle of joy should include:

### 1. Event Handling 🎈  
- Button click ✅  
- Hover effects ✅  
- Keypress detection ✅  
- Bonus: A secret action for a *double-click* or *long press* 🤫

### 2. Interactive Elements 🎮  
- A button that changes text or color  
- An image gallery or slideshow  
- Tabs or accordion-style content  
- Bonus: Add some animation using JS or CSS ✨

### 3. Form Validation 📋✅  
- Required field checks  
- Email format validation  
- Password rules (e.g., min 8 characters)  
- Bonus: Real-time feedback while typing

---

## 🧙‍♂️ Pro Tips

- Keep your code clean and commented – your future self will thank you!
- Think about **user experience** – what makes your site more *fun* to use?
- Don’t be afraid to **Google and experiment** – that’s how real developers roll!

---

## 🎉 Now Go Make It Fun!

Remember – this isn't just code. It's your **first step toward creating magical user experiences**. So play around, break stuff (then fix it), and most of all, have FUN! 😄

Happy Coding! 💻✨  


<button id="clickBtn">Click Me!</button>
<p id="clickResult"></p>

document.getElementById("clickBtn").addEventListener("click", function() {
  document.getElementById("clickResult").textContent = "You clicked the button!";
});

const button = document.getElementById("clickBtn");

button.addEventListener("mouseover", function() {
  button.style.backgroundColor = "lightblue";
});

button.addEventListener("mouseout", function() {
  button.style.backgroundColor = "";
});

document.addEventListener("keydown", function(event) {
  document.getElementById("clickResult").textContent = `Key pressed: ${event.key}`;
});

button.addEventListener("dblclick", function() {
  alert("Double-clicked!");
});

let pressTimer;

button.addEventListener("mousedown", function() {
  pressTimer = setTimeout(function() {
    alert("Long press detected!");
  }, 1000);  // 1000ms = 1 second
});

button.addEventListener("mouseup", function() {
  clearTimeout(pressTimer);
});

2. Interactive Elements 🎮

 <button id="colorBtn">Change Color</button>

 document.getElementById("colorBtn").addEventListener("click", function() {
  this.style.backgroundColor = "green";
  this.textContent = "Color Changed!";
});

<img id="slideshow" src="image1.jpg" alt="Image Slideshow" width="300">
<button id="nextImg">Next Image</button>

let images = ["image1.jpg", "image2.jpg", "image3.jpg"];
let currentIndex = 0;

document.getElementById("nextImg").addEventListener("click", function() {
  currentIndex = (currentIndex + 1) % images.length;
  document.getElementById("slideshow").src = images[currentIndex];
});

<div class="accordion">
  <button class="accordion-button">Section 1</button>
  <div class="accordion-content">
    <p>Content for section 1...</p>
  </div>
  <button class="accordion-button">Section 2</button>
  <div class="accordion-content">
    <p>Content for section 2...</p>
  </div>
</div>

.accordion-content {
  display: none;
}

.accordion-button.active + .accordion-content {
  display: block;
}

const buttons = document.querySelectorAll(".accordion-button");

buttons.forEach(button => {
  button.addEventListener("click", function() {
    this.classList.toggle("active");
    const content = this.nextElementSibling;
    content.style.display = content.style.display === "block" ? "none" : "block";
  });
});

3. Form Validation 📋✅

   <form id="myForm">
  <input type="text" id="username" required placeholder="Enter your username">
  <button type="submit">Submit</button>
</form>

document.getElementById("myForm").addEventListener("submit", function(event) {
  const username = document.getElementById("username").value;
  if (!username) {
    alert("Username is required!");
    event.preventDefault(); // Prevents form submission
  }
});

document.getElementById("myForm").addEventListener("submit", function(event) {
  const username = document.getElementById("username").value;
  if (!username) {
    alert("Username is required!");
    event.preventDefault(); // Prevents form submission
  }
});

<form id="emailForm">
  <input type="email" id="email" placeholder="Enter your email" required>
  <button type="submit">Submit</button>
</form>

document.getElementById("emailForm").addEventListener("submit", function(event) {
  const email = document.getElementById("email").value;
  const emailRegex = /^[a-zA-Z0-9._-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/;
  if (!emailRegex.test(email)) {
    alert("Please enter a valid email address!");
    event.preventDefault();
  }
});

Password Rule (min 8 characters)

<form id="passwordForm">
  <input type="password" id="password" placeholder="Enter your password" required>
  <button type="submit">Submit</button>
</form>

document.getElementById("passwordForm").addEventListener("submit", function(event) {
  const password = document.getElementById("password").value;
  if (password.length < 8) {
    alert("Password must be at least 8 characters long!");
    event.preventDefault();
  }
});

Bonus: Real-Time Feedback While Typing

document.getElementById("password").addEventListener("input", function() {
  const password = this.value;
  const feedback = document.getElementById("feedback");
  if (password.length >= 8) {
    feedback.textContent = "Password is strong!";
    feedback.style.color = "green";
  } else {
    feedback.textContent = "Password is too short!";
    feedback.style.color = "red";
  }
});



