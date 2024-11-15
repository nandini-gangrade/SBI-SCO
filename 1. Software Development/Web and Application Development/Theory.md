## **HTML5 – Deep Dive**

#### **1. What is HTML5?**

HTML5 is the latest version of **HTML (HyperText Markup Language)**, the standard language used for creating and structuring content on the web. HTML5 offers new features, elements, and attributes, which make web pages more interactive, dynamic, and user-friendly. It enhances multimedia support (videos, audio), increases semantic clarity, and optimizes web performance.

---

#### **2. Basic HTML Structure (The Skeleton of an HTML Document)**

Before we dive into specific features, let's first understand the basic structure of an HTML5 document. Every HTML document starts with a **DOCTYPE** declaration to specify the version of HTML, followed by the `<html>`, `<head>`, and `<body>` elements.

##### **Syntax**:
```html
<!DOCTYPE html> <!-- Declares the document type as HTML5 -->
<html lang="en">
  <head>
    <meta charset="UTF-8"> <!-- Specifies the character set for the page -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0"> <!-- Responsive design -->
    <title>HTML5 Deep Dive</title> <!-- Page title displayed in the browser tab -->
  </head>
  <body>
    <h1>Welcome to HTML5!</h1> <!-- Main heading -->
    <p>This is a paragraph.</p> <!-- Paragraph element -->
  </body>
</html>
```

#### **Explanation of the Components**:

- **`<!DOCTYPE html>`**: Specifies the document type as HTML5 and helps browsers render the page correctly.
- **`<html lang="en">`**: The `<html>` tag wraps the entire document content and has a `lang` attribute to specify the language of the document (e.g., `en` for English).
- **`<head>`**: Contains metadata for the document, such as the title of the page, meta tags for charset and viewport (important for mobile responsiveness), and links to external CSS/JS files.
- **`<body>`**: Contains the visible content of the page, like headings, paragraphs, images, etc.

---

#### **3. HTML5 New Features and Semantic Elements**

HTML5 introduced several new elements that are semantically meaningful. These elements help define the structure of a web page more clearly and improve accessibility.

##### **New HTML5 Semantic Elements**:

- **`<header>`**: Represents a container for introductory content, navigation links, or logo.
  ```html
  <header>
    <h1>My Website</h1>
    <nav>
      <ul>
        <li><a href="#home">Home</a></li>
        <li><a href="#about">About</a></li>
      </ul>
    </nav>
  </header>
  ```

- **`<footer>`**: Contains footer information about the document, often used for copyright, contact info, or links.
  ```html
  <footer>
    <p>&copy; 2024 My Website</p>
  </footer>
  ```

- **`<article>`**: Represents a piece of self-contained content, like a blog post or news article.
  ```html
  <article>
    <h2>HTML5 Features</h2>
    <p>This is an article about HTML5.</p>
  </article>
  ```

- **`<section>`**: Represents a thematic section of content, typically with a heading.
  ```html
  <section>
    <h2>About Us</h2>
    <p>We are a web development company.</p>
  </section>
  ```

- **`<nav>`**: Defines navigation links.
  ```html
  <nav>
    <ul>
      <li><a href="#home">Home</a></li>
      <li><a href="#services">Services</a></li>
    </ul>
  </nav>
  ```

#### **Why Use Semantic Tags?**

- **Improved Readability**: These tags provide clarity, both for developers and browsers.
- **SEO Benefits**: Search engines can better understand the content of the page, leading to better ranking.
- **Accessibility**: Screen readers and other assistive technologies can more easily navigate the page.

---

#### **4. Forms in HTML5**

HTML5 introduced new form input types that improve user experience and input validation. Some of the new input types are:

- **`<input type="email">`**: Used for email address input. The browser will validate that the input is in the correct email format.
  ```html
  <form>
    <label for="email">Email:</label>
    <input type="email" id="email" name="email" required>
  </form>
  ```

- **`<input type="tel">`**: Used for telephone number input. The browser may show a number pad on mobile devices.
  ```html
  <form>
    <label for="phone">Phone:</label>
    <input type="tel" id="phone" name="phone">
  </form>
  ```

- **`<input type="date">`**: Used for date input. Displays a date picker on compatible browsers.
  ```html
  <form>
    <label for="birthdate">Birthdate:</label>
    <input type="date" id="birthdate" name="birthdate">
  </form>
  ```

- **`<input type="range">`**: Represents a range control, like a slider.
  ```html
  <form>
    <label for="volume">Volume:</label>
    <input type="range" id="volume" name="volume" min="0" max="100">
  </form>
  ```

- **`<input type="search">`**: Represents a search input field. It can show a search box with clear options.
  ```html
  <form>
    <label for="search">Search:</label>
    <input type="search" id="search" name="search">
  </form>
  ```

##### **Forms Validation in HTML5**:
HTML5 includes native form validation using attributes like `required`, `pattern`, `minlength`, `maxlength`, etc. These attributes eliminate the need for JavaScript for simple validations.

```html
<form>
  <label for="username">Username:</label>
  <input type="text" id="username" name="username" required minlength="4" maxlength="12">
  <input type="submit" value="Submit">
</form>
```

**Explanation**:  
- The `required` attribute ensures that the user cannot submit the form without filling in the field.
- `minlength` and `maxlength` ensure that the username is between 4 and 12 characters.

---

#### **5. Multimedia in HTML5**

HTML5 makes it easy to embed multimedia content directly into web pages without the need for third-party plugins like Flash.

- **`<audio>`**: Used for embedding audio files like MP3, WAV, and Ogg.
  ```html
  <audio controls>
    <source src="audio.mp3" type="audio/mp3">
    Your browser does not support the audio element.
  </audio>
  ```

- **`<video>`**: Used for embedding video content. Supports multiple formats like MP4, WebM, and Ogg.
  ```html
  <video width="320" height="240" controls>
    <source src="movie.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
  ```

- **`<picture>`**: A new tag for responsive images, allowing different image formats based on screen size.
  ```html
  <picture>
    <source media="(max-width: 600px)" srcset="image-small.jpg">
    <source media="(min-width: 601px)" srcset="image-large.jpg">
    <img src="image-default.jpg" alt="Image description">
  </picture>
  ```

---

#### **6. Canvas Element in HTML5**

The `<canvas>` element allows for drawing graphics via JavaScript, such as creating images, animations, or even interactive games. It acts as a drawing surface on a web page.

```html
<canvas id="myCanvas" width="500" height="500"></canvas>
<script>
  var canvas = document.getElementById("myCanvas");
  var ctx = canvas.getContext("2d");
  ctx.fillStyle = "#FF0000";
  ctx.fillRect(10, 10, 150, 100); // Draws a red rectangle
</script>
```

---

#### **7. Geolocation API**

HTML5 introduces the **Geolocation API** for accessing a user's geographical location. This feature is useful for location-based services, such as mapping applications.

```html
<button onclick="getLocation()">Get Location</button>
<p id="location"></p>

<script>
  function getLocation() {
    if (navigator.geolocation) {
      navigator.geolocation.getCurrentPosition(showPosition);
    } else {
      document.getElementById("location").innerHTML = "Geolocation is not supported by this browser.";
    }
  }

  function show

Position(position) {
    document.getElementById("location").innerHTML = "Latitude: " + position.coords.latitude + 
    "<br>Longitude: " + position.coords.longitude;
  }
</script>
```

---

### **Summary of Key HTML5 Features**:

- **New Semantic Elements**: `<header>`, `<footer>`, `<article>`, `<section>`, `<nav>`, etc., for better structure and accessibility.
- **Forms and Input Types**: Improved form controls with new input types like `email`, `date`, `range`, `tel`, etc.
- **Multimedia**: `<audio>`, `<video>`, and `<canvas>` for embedding and drawing media directly on web pages.
- **Geolocation API**: Access user location for location-based services.

---

<br>

### **CSS – Cascading Style Sheets (Detailed Explanation)**

#### **1. What is CSS?**

CSS (Cascading Style Sheets) is used to style and format the layout of HTML documents. It controls the look and feel of a web page, such as colors, fonts, spacing, alignment, and positioning. CSS is responsible for making web pages visually appealing and user-friendly.

---

#### **2. Basic CSS Syntax**

The basic syntax of CSS involves selecting an HTML element and applying styles to it.

##### **Syntax**:
```css
selector {
    property: value;
}
```

- **Selector**: It targets the HTML element you want to style.
- **Property**: The style you want to apply (e.g., `color`, `font-size`, `margin`).
- **Value**: The value for the property (e.g., `red`, `16px`, `20px`).

##### **Example**:
```css
h1 {
    color: blue;
    font-size: 24px;
    margin: 20px;
}
```
This will make the text inside `<h1>` tags blue, with a font size of 24px and 20px margin around it.

---

#### **3. Types of CSS: Inline, Internal, and External**

1. **Inline CSS**: Directly in the HTML element using the `style` attribute.
   ```html
   <h1 style="color: blue; font-size: 24px;">Hello World</h1>
   ```

2. **Internal CSS**: Defined in the `<style>` tag within the `<head>` section of the HTML document.
   ```html
   <head>
     <style>
       h1 {
         color: blue;
         font-size: 24px;
       }
     </style>
   </head>
   ```

3. **External CSS**: Defined in a separate `.css` file and linked to the HTML document.
   ```html
   <link rel="stylesheet" href="styles.css">
   ```

##### **Which Type to Use?**
- **Inline**: Useful for quick styling of a specific element.
- **Internal**: Good for styles used only on that page.
- **External**: Best for large websites, as it allows you to reuse the same CSS file across multiple pages, making it more maintainable.

---

#### **4. CSS Box Model**

The **CSS Box Model** is fundamental to web design. Every HTML element is considered a rectangular box, and the model defines how elements are spaced and how they interact with each other.

The box model consists of:
- **Content**: The actual content of the element, such as text or an image.
- **Padding**: The space around the content, inside the border.
- **Border**: A line surrounding the padding (optional).
- **Margin**: The space outside the border, between the element and others.

##### **Diagram of the Box Model**:

```
+-------------------------------+
|           Margin               |
|  +-------------------------+    |
|  |        Border            |    |
|  |  +-------------------+   |    |
|  |  |   Padding         |   |    |
|  |  | +-------------+   |   |    |
|  |  | |  Content   |   |   |    |
|  |  | +-------------+   |   |    |
|  |  +-------------------+   |    |
|  +-------------------------+    |
+-------------------------------+
```

---

#### **5. CSS Layout Techniques: Flexbox & Grid**

- **Flexbox**: A layout model for arranging items in a row or column, offering flexibility in terms of alignment, spacing, and wrapping.

##### **Flexbox Example**:
```css
.container {
  display: flex;
  justify-content: space-between;
}
.item {
  width: 30%;
  background-color: lightblue;
}
```
```html
<div class="container">
  <div class="item">Item 1</div>
  <div class="item">Item 2</div>
  <div class="item">Item 3</div>
</div>
```

**Explanation**:
- `display: flex` turns the container into a flexbox.
- `justify-content: space-between` distributes the items with equal space between them.

- **Grid**: A two-dimensional layout system for arranging elements into rows and columns.

##### **Grid Example**:
```css
.container {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  gap: 10px;
}
.item {
  background-color: lightgreen;
}
```
```html
<div class="container">
  <div class="item">Item 1</div>
  <div class="item">Item 2</div>
  <div class="item">Item 3</div>
</div>
```

**Explanation**:
- `grid-template-columns: 1fr 1fr 1fr` creates three equal columns.
- `gap: 10px` adds a gap between items.

---

#### **6. Advanced CSS Concepts: Transitions, Animations, and Pseudo-classes**

- **Transitions**: A smooth change in property values over a specified time.  
  Example: Transitioning the color of a button when hovered over.

```css
button {
  background-color: blue;
  color: white;
  transition: background-color 0.3s ease;
}

button:hover {
  background-color: green;
}
```

- **Animations**: More complex than transitions, animations allow for multiple steps with `@keyframes`.

```css
@keyframes slide {
  from {
    transform: translateX(0);
  }
  to {
    transform: translateX(100px);
  }
}

div {
  animation: slide 2s infinite;
}
```

- **Pseudo-classes**: Special states of elements.  
  Example: `:hover`, `:focus`, `:nth-child()`, etc.

```css
a:hover {
  color: red;
}
```

---

#### **7. CSS Media Queries (Responsive Design)**

Media queries are essential for creating responsive designs that adjust to different screen sizes and devices (like mobile, tablets, etc.).

##### **Example of Media Query**:
```css
/* Default styles */
body {
  font-size: 16px;
}

/* For screens wider than 600px */
@media screen and (min-width: 600px) {
  body {
    font-size: 18px;
  }
}
```

**Explanation**:  
- By using media queries, we can apply different styles based on the viewport size or other device characteristics.

---

<br>

## **JavaScript – Introduction, Syntax, and Core Concepts**

#### **1. What is JavaScript?**

JavaScript is a **scripting language** that enables dynamic behavior on web pages. It allows for interactivity, such as form validation, animations, and complex features like Ajax requests and DOM manipulation.

---

#### **2. JavaScript Syntax and Structure**

JavaScript syntax consists of:

- **Variables**: Used to store data.
  ```javascript
  var name = "John";  // Declares a variable
  let age = 25;       // Declares a variable with block scope
  const city = "New York"; // Declares a constant (immutable value)
  ```

- **Data Types**: JavaScript has several data types: strings, numbers, booleans, arrays, objects, null, undefined, and symbols.
  ```javascript
  let str = "Hello";    // String
  let num = 100;        // Number
  let isActive = true;  // Boolean
  ```

- **Functions**: Used to encapsulate reusable code.
  ```javascript
  function greet(name) {
    console.log("Hello, " + name);
  }
  greet("Alice");  // Outputs: Hello, Alice
  ```

- **Control Flow**: Includes conditional statements like `if`, `else`, and loops (`for`, `while`).
  ```javascript
  let number = 10;
  if (number > 5) {
    console.log("Greater than 5");
  } else {
    console.log("Less than or equal to 5");
  }
  ```

---

#### **3. DOM Manipulation in JavaScript**

The **DOM (Document Object Model)** represents the structure of an HTML document. JavaScript allows you to manipulate the DOM to change the content or style of a webpage dynamically.

##### **Example** – Changing the Text of an Element:
```html
<p id="greeting">Hello, World!</p>
<button onclick="changeText()">Change Text</button>

<script>
  function changeText() {
    document.getElementById("greeting").innerHTML = "Goodbye, World!";
  }
</script>
```

---

#### **4. Event Handling in JavaScript**

JavaScript provides the ability to handle user interactions through **events** like clicks, keypresses, and mouse movements.

##### **Example** – Handling Click Event:
```html
<button onclick="alert('Button clicked!')">Click Me</button>
```

---

#### **5. Asynchronous JavaScript: Callback Functions, Promises, and Async/Await**

Asynchronous programming is essential for tasks like network requests and timers.

- **Callback Functions**: Functions passed as arguments to other functions.
  ```javascript
  setTimeout(function() {
    console.log("Hello after 2 seconds");
  }, 2000);
  ```

- **Promises**: Represents a value that might be available now, or in the future, or never.
  ```javascript
  let promise = new Promise(function(resolve, reject) {
    let success = true;
    if (success) {
      resolve("Success!");
    } else {
      reject("Error occurred");
    }
  });
  ```

- **Async/Await**: Makes asynchronous code look synchronous.
  ```javascript
  async function fetchData() {
    let response = await fetch("https://api.example.com");
    let data = await response.json();
    console.log(data);
  }
  ```
  
---

### **6. Advanced JavaScript Concepts**

#### **a) Closures**

A **closure** is a function that has access to its own scope, the scope in which it was created, and the global scope. This concept allows functions to retain access to variables from the outer function even after the outer function has finished executing.

##### **Example**:
```javascript
function outerFunction(outerVariable) {
    return function innerFunction(innerVariable) {
        console.log(outerVariable);  // Access outerVariable
        console.log(innerVariable);  // Access innerVariable
    }
}

const closureExample = outerFunction("I am outside!");
closureExample("I am inside!");
```

**Explanation**:
- The `innerFunction` is able to access the `outerVariable` because it forms a closure with `outerFunction`. The closure allows `innerFunction` to keep access to the variables from its outer scope even after `outerFunction` has completed.

---

#### **b) The `this` Keyword**

In JavaScript, the `this` keyword refers to the object that is currently executing the code. The value of `this` is determined by how a function is called.

##### **Example**:
```javascript
function person() {
    this.name = "Alice";
    this.sayName = function() {
        console.log(this.name); // 'this' refers to the person object
    }
}

const p = new person();
p.sayName();  // Outputs: Alice
```

**Explanation**:
- When the method `sayName()` is called on the object `p`, the `this` keyword inside the method refers to the object `p` itself.

---

#### **c) JavaScript Hoisting**

**Hoisting** is a JavaScript mechanism where variables and function declarations are moved to the top of their containing scope during the compile phase, before the code has been executed.

##### **Example**:
```javascript
console.log(a);  // undefined
var a = 5;

hoistedFunction(); // This works due to hoisting

function hoistedFunction() {
    console.log("Function is hoisted!");
}
```

**Explanation**:
- **Variables** declared with `var` are hoisted to the top but initialized with `undefined`.
- **Functions** declared with `function` are fully hoisted, so you can call them before they are defined in the code.

---

### **7. Asynchronous JavaScript: Callbacks, Promises, Async/Await**

#### **a) Callback Functions**

A **callback** is a function passed into another function as an argument to be executed later. Callbacks are used to handle asynchronous operations.

##### **Example**:
```javascript
function fetchData(callback) {
    setTimeout(() => {
        console.log("Data fetched!");
        callback();
    }, 2000);
}

fetchData(function() {
    console.log("Callback function executed!");
});
```

**Explanation**:
- The `callback` is executed after the `setTimeout` completes.

---

#### **b) Promises**

A **Promise** is an object representing the eventual completion (or failure) of an asynchronous operation.

##### **Example**:
```javascript
let promise = new Promise(function(resolve, reject) {
    let success = true;
    if (success) {
        resolve("Data fetched successfully!");
    } else {
        reject("Error fetching data");
    }
});

promise.then(function(result) {
    console.log(result); // "Data fetched successfully!"
}).catch(function(error) {
    console.log(error); // "Error fetching data"
});
```

**Explanation**:
- **`resolve`** is called if the operation succeeds.
- **`reject`** is called if the operation fails.

---

#### **c) Async/Await**

**Async/Await** makes asynchronous code easier to write and read by using a synchronous-style code flow.

##### **Example**:
```javascript
async function getData() {
    let response = await fetch("https://api.example.com");
    let data = await response.json();
    console.log(data);
}

getData();
```

**Explanation**:
- **`async`**: Marks a function as asynchronous.
- **`await`**: Waits for a promise to resolve before continuing the execution of the code.

---

### **8. HTTP/HTTPS, AJAX, and REST APIs**

#### **a) HTTP vs. HTTPS**

- **HTTP (HyperText Transfer Protocol)** is the foundation of any data exchange on the web. It’s used to transfer data between the browser and the server.
- **HTTPS (HyperText Transfer Protocol Secure)** is the secure version of HTTP. It uses encryption (SSL/TLS) to secure the data exchanged between the client and server.

##### **Difference between HTTP and HTTPS**:
- **HTTP**: Data is transferred in plain text.
- **HTTPS**: Data is encrypted, providing security against eavesdropping and tampering.

---

#### **b) AJAX (Asynchronous JavaScript and XML)**

**AJAX** allows web pages to update data asynchronously without reloading the entire page. It is commonly used to fetch data from a server and update parts of a web page dynamically.

##### **Example of AJAX using Fetch**:
```javascript
fetch("https://api.example.com/data")
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

**Explanation**:
- **`fetch()`** sends an HTTP request to the server.
- **`.then()`** handles the response once it's received.
- **`.catch()`** handles any errors that occur during the request.

---

#### **c) REST APIs (Representational State Transfer)**

**REST** is an architectural style for designing networked applications. It relies on stateless communication and uses HTTP methods (GET, POST, PUT, DELETE) to perform operations on resources.

##### **Common HTTP Methods**:
1. **GET**: Fetches data from the server.
2. **POST**: Sends data to the server to create a new resource.
3. **PUT**: Updates an existing resource on the server.
4. **DELETE**: Deletes a resource from the server.

##### **Example of a REST API request**:
```javascript
fetch("https://api.example.com/users", {
    method: "GET", // HTTP method
    headers: {
        "Content-Type": "application/json"
    }
})
.then(response => response.json())
.then(data => console.log(data));
```

**Explanation**:
- The **GET** request is used to fetch the list of users from the API.

---

### **9. Cookies**

Cookies are small pieces of data stored by the browser that can be used to remember information about the user (e.g., preferences, login status).

#### **a) Setting a Cookie**:
```javascript
document.cookie = "username=John; expires=Wed, 1 Jan 2025 12:00:00 UTC; path=/";
```

#### **b) Reading a Cookie**:
```javascript
let cookies = document.cookie;
console.log(cookies);  // "username=John; ..."
```

**Explanation**:
- **`document.cookie`** is used to read or set cookies.
- Cookies are set with a name-value pair and can have attributes like expiration date and path.

---

Let’s continue from **HTTP/HTTPS, AJAX, REST APIs**, and **Cookies** in full detail, expanding on each topic and covering everything you need to know, from basic concepts to advanced aspects.

---

### **10. HTTP vs HTTPS**

#### **a) HTTP (Hypertext Transfer Protocol)**

**HTTP** is a protocol used for transmitting hypertext via the web. It defines the rules for how clients (like browsers) and servers communicate. HTTP is used to request and deliver web pages, images, and other resources.

- **Stateless**: HTTP is stateless, meaning each request is independent, and the server does not store any information about previous requests.
- **Port**: HTTP uses port 80 by default.
- **Unencrypted**: Data sent over HTTP is in plaintext, making it vulnerable to interception by attackers.

##### **HTTP Request Example**:
```http
GET /index.html HTTP/1.1
Host: www.example.com
```
- **GET**: The HTTP method used to request the `index.html` page.
- **HTTP/1.1**: The version of HTTP.
- **Host**: The domain to which the request is sent.

#### **b) HTTPS (Hypertext Transfer Protocol Secure)**

**HTTPS** is the secure version of HTTP, which uses **SSL/TLS** (Secure Sockets Layer/Transport Layer Security) to encrypt the data transferred between the client and server. This ensures that the data cannot be read or modified during transmission, protecting it from eavesdropping, man-in-the-middle attacks, and tampering.

- **Encryption**: HTTPS encrypts data, making it secure against third-party interception.
- **Authentication**: Ensures that the website the user is communicating with is genuine and not a fake or malicious site.
- **Port**: HTTPS uses port 443 by default.

##### **Key Differences Between HTTP and HTTPS**:
1. **Security**: HTTPS encrypts data, while HTTP does not.
2. **Port**: HTTP uses port 80, while HTTPS uses port 443.
3. **URL**: HTTPS URLs start with `https://` (instead of `http://`).
4. **Certificate**: HTTPS requires an SSL/TLS certificate installed on the server to establish a secure connection.

**Example of HTTPS Request**:
```http
GET /home HTTP/1.1
Host: www.example.com
```
- This would be encrypted when transmitted.

#### **How SSL/TLS Works**:
1. **Handshake**: The client and server exchange cryptographic keys and establish a secure connection.
2. **Encryption**: Data is encrypted before transmission and decrypted by the recipient.
3. **Session**: After the handshake, a secure session is established for the duration of the connection.

---

### **11. AJAX (Asynchronous JavaScript and XML)**

**AJAX** is a technique used in web development to create asynchronous web applications. It allows web pages to load data from a server without refreshing the entire page, providing a more dynamic and faster user experience.

#### **a) How AJAX Works**

AJAX works by using JavaScript (or jQuery) to send HTTP requests to a server and retrieve data without reloading the page.

##### **Basic Workflow**:
1. **JavaScript triggers an HTTP request** (e.g., when a user clicks a button).
2. The **AJAX request** is sent to the server asynchronously.
3. The server processes the request and sends back data (usually in JSON, XML, or plain text).
4. JavaScript processes the response and updates the web page.

#### **b) XMLHttpRequest vs Fetch API**

- **XMLHttpRequest (XHR)**: The old way of making AJAX requests, which is more complicated and harder to use.
- **Fetch API**: A modern, promise-based API that simplifies making asynchronous requests.

##### **Using XMLHttpRequest**:
```javascript
var xhr = new XMLHttpRequest();
xhr.open("GET", "https://api.example.com/data", true);
xhr.onload = function() {
    if (xhr.status == 200) {
        console.log(xhr.responseText);
    }
};
xhr.send();
```

##### **Using Fetch API**:
```javascript
fetch("https://api.example.com/data")
    .then(response => response.json())
    .then(data => console.log(data))
    .catch(error => console.log('Error:', error));
```

- **`fetch()`** returns a **Promise**, which makes handling asynchronous code easier and cleaner.
- **`.then()`** is used to handle successful responses.
- **`.catch()`** is used for error handling.

---

### **12. REST APIs (Representational State Transfer)**

**REST** is an architectural style for designing networked applications. REST APIs allow clients to interact with a server using standard HTTP methods (GET, POST, PUT, DELETE) and communicate data in a stateless, structured way.

#### **a) Core Principles of REST**
1. **Stateless**: Each request from a client to a server must contain all the information the server needs to understand and fulfill the request.
2. **Client-Server**: The client and server are independent of each other. The server is responsible for managing data, while the client is responsible for the user interface.
3. **Uniform Interface**: REST relies on standard HTTP methods (GET, POST, PUT, DELETE) to perform operations on resources (data entities).
4. **Cacheable**: Responses must explicitly specify whether they can be cached or not.
5. **Layered System**: The architecture can be composed of hierarchical layers, where each layer interacts only with the layer directly above or below it.
6. **Code on Demand (Optional)**: The server can provide executable code to the client (though this is rarely used).

#### **b) HTTP Methods in REST**
- **GET**: Retrieve data from the server.
- **POST**: Create a new resource on the server.
- **PUT**: Update an existing resource on the server.
- **DELETE**: Remove a resource from the server.

##### **Example of a REST API**:
```javascript
// GET request to fetch user data
fetch("https://api.example.com/users/1")
    .then(response => response.json())
    .then(data => console.log(data))
    .catch(error => console.error('Error:', error));

// POST request to create a new user
fetch("https://api.example.com/users", {
    method: "POST",
    headers: {
        "Content-Type": "application/json"
    },
    body: JSON.stringify({
        name: "John Doe",
        email: "john.doe@example.com"
    })
})
    .then(response => response.json())
    .then(data => console.log("User created:", data))
    .catch(error => console.error("Error:", error));
```

**Explanation**:
- The **GET** request fetches data for a user with ID `1`.
- The **POST** request creates a new user on the server by sending the user data in the body of the request.

#### **c) JSON and XML in REST APIs**

While **JSON** (JavaScript Object Notation) is the most commonly used format for data exchange in REST APIs due to its simplicity, **XML** can also be used.

- **JSON** is lightweight, easy to read, and easy to parse.
- **XML** is more verbose and requires additional parsing but supports more complex data structures.

---

### **13. Cookies**

Cookies are small pieces of data stored by the browser that can be used to remember information about the user, such as login status, preferences, or items in a shopping cart.

#### **a) Setting a Cookie**
```javascript
document.cookie = "username=John; expires=Wed, 1 Jan 2025 12:00:00 UTC; path=/";
```

- **`expires`**: Specifies the expiration date of the cookie. If not specified, the cookie will expire when the session ends (when the browser is closed).
- **`path`**: Defines the URL path for which the cookie is valid. By default, it’s the path of the page where the cookie is set.

#### **b) Reading a Cookie**
```javascript
let cookies = document.cookie;
console.log(cookies); // "username=John; ..."
```

- **`document.cookie`** is used to get or set cookies associated with the current document.

#### **c) Deleting a Cookie**
To delete a cookie, you set its expiration date to a past date:
```javascript
document.cookie = "username=John; expires=Thu, 01 Jan 1970 00:00:00 UTC; path=/";
```

#### **d) Cookie Attributes**
- **Secure**: The cookie will only be sent over HTTPS connections.
- **HttpOnly**: The cookie cannot be accessed via JavaScript, making it more secure for storing session data.
- **SameSite**: Controls whether cookies are sent with cross-site requests, helping to prevent CSRF attacks.

---
