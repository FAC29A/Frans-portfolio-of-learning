## 1. Write code that executes asynchronously
- Sometimes we don't want coe to execute straight away.
- Can delay code using setTimeout and setInterval. Clear these using clearTimeout and clearInterval:
<img src="https://github.com/FAC29A/Frans-portfolio-of-learning/assets/124707247/598bf818-0553-4cd8-977a-0f34b486372c" width="400" height="auto" alt="setTimeout">
<img src="https://github.com/FAC29A/Frans-portfolio-of-learning/assets/124707247/f92c6dec-c4a0-451d-89e7-83ad215232fc" width="400" height="auto" alt="setInterval, clearInterval">


- We can also use promises
- Promises and .then are useful if we are waiting for something to happen before we execute code (e.g. if fetching data from an API)
- .then also avoids nesting nightmares!

  
<img src="https://github.com/FAC29A/Frans-portfolio-of-learning/assets/124707247/f22b77a7-3ea9-4fc9-bd37-527a6e869faf" alt ="then avoids nesting" width="400" height="auto">
<img src="https://github.com/FAC29A/Frans-portfolio-of-learning/assets/124707247/7c559abf-92f9-4930-bc4b-e884e22905f1" width="400" height="auto" alt="Promise .then()">

## 2. Use callbacks to access values that aren’t available synchronously

**Callback Functions**: Callback functions are JavaScript functions that are passed as arguments to other functions and are executed when those functions complete their tasks. They play a vital role in handling asynchronous operations by allowing us to specify what should happen once an asynchronous task finishes.

**Data Retrieval**: Callbacks are crucial for handling data retrieval from sources like APIs or databases, where response times are unpredictable. They enable your code to continue executing other tasks while waiting for the data to be fetched and processed.

**Example 1 - Fetch API**: The Fetch API example demonstrates how you can use a callback function to handle data retrieved from a remote server. This is a common scenario in web development when you need to fetch data from an API and perform actions with that data once it's available.

**Example 2 - Event Listeners**: Callback functions are also used with event listeners to respond to user interactions or other asynchronous events in web applications. When an event, such as a button click, occurs, the specified callback function is executed to handle the event.

**Callback Hell**: Callback hell refers to the problem of deeply nested callbacks, which can make code difficult to read and maintain. To address this issue, it's often recommended to use alternatives like Promises or async/await, which provide cleaner and more structured ways to work with asynchronous code.

**E.g.**
asyncFunction1((result1) => {
  // First asynchronous operation
  asyncFunction2(result1, (result2) => {
    // Second asynchronous operation
    asyncFunction3(result2, (result3) => {
      // Third asynchronous operation
      asyncFunction4(result3, (result4) => {
        // Fourth asynchronous operation
        asyncFunction5(result4, (result5) => {
          // Fifth asynchronous operation
          // ... and it can go on with even more nested callbacks
        });
      });
    });
  });
});

## 3. Use promises to access values that aren’t available synchronously
**Readable and Chained Syntax:** Promises offer a more readable and sequential syntax. Instead of nesting callback functions, you can chain promises together using then(). This makes the code more linear and easier to follow, reducing the problem of "callback hell."

<img src="https://github.com/FAC29A/Frans-portfolio-of-learning/assets/124707247/8d7a7f44-3c5a-4772-b70a-6d9809d612a1" width="400" height="auto" alt="Example of fetch">

**Error Handling:** Promises have built-in error handling mechanisms through the .catch() method. With callbacks, you often need to manually handle errors within each callback function, making error handling less standardized and more error-prone.

## 4. Use the fetch method to make HTTP requests and receive responses
**// Define the URL for the Pokémon API**
const apiUrl = 'https://pokeapi.co/api/v2/pokemon/1'; // This example fetches data for Pokémon with ID 1 (Bulbasaur)

**// Use the Fetch API to make a GET request to the API**
fetch(apiUrl)
  .then((response) => {
**//Handle errors- e.g. network error/404/429 etc**
    if (!response.ok) {
      throw new Error('Network response was not ok');
    }
**// Parse the response as JSON**
    return response.json(); 
  })
  .then((data) => {
**// Data contains information about the Pokémon**
    console.log('Pokémon Name:', data.name);
    console.log('Abilities:', data.abilities.map((ability) => ability.ability.name).join(', '));
    console.log('Types:', data.types.map((type) => type.type.name).join(', '));
  })
**// Catch any errors so the rest of the code can still run**
  .catch((error) => {
    console.error('Error:', error);
  });

## 5. Configure the options argument of the fetch method to make GET and POST requests
**GET Requests:**
GET requests are used to retrieve data from a server. When using the fetch method for GET requests, the default behaviour is to make a GET request, so you don't need to specify the HTTP method explicitly. (See fetch above)

**POST Requests:**
POST requests are used to send data to a server, often for creating or updating resources. To make a POST request using the fetch method, you need to configure the options argument with the method set to 'POST', and include the data you want to send in the body property.

**E.g.**
**// POST request using fetch**
const postData = {
  title: 'New Post',
  body: 'This is the content of the new post',
  userId: 1,
};

fetch('https://jsonplaceholder.typicode.com/posts', {
method: 'POST',
  headers: {
    'Content-Type': 'application/json',
  },
  body: JSON.stringify(postData),
})
  .then((response) => {
    if (!response.ok) {
      throw new Error('Network response was not ok');
    }
    return response.json(); // Parse the response as JSON
  })
  .then((data) => {
    console.log('New Post Data:', data);
  })
  .catch((error) => {
    console.error('Error:', error);
  });

## 6. Use the map array method to create a new array containing new values
**// Create a new array by doubling each element of the original array**
const originalArray = [1, 2, 3, 4, 5];
const doubledArray = originalArray.map((value) => value * 2);
console.log(doubledArray); 
**// Output: [2, 4, 6, 8, 10]**


## 7. Use the filter array method to create a new array with certain values removed
**// Create a new array by removing even numbers from the original array**
const originalArray = [1, 2, 3, 4, 5, 6];
const filteredArray = originalArray.filter((value) => value % 2 !== 0);
console.log(filteredArray); 
**// Output: [1, 3, 5]**


## 8. Access DOM nodes using a variety of selectors
A DOM node, is an individual element or part of a web page's structure as represented in the Document Object Model. The DOM is a programming interface for web documents that represents the page's structure and content so that it can be easily manipulated using programming languages like JavaScript.

**In the context of the DOM:**

**Element Nodes:** DOM nodes can represent HTML elements like headings (<h1>, <div>), paragraphs (<p>), lists (<ul>, <li>), forms (<form>, <input>), and more. Each of these elements is considered a DOM node.

**Attribute Nodes:** The attributes of HTML elements (e.g., id, class, src, href) are also represented as nodes in the DOM. They are typically accessible through the element nodes.

**Text Nodes:** The text content within HTML elements is represented by text nodes. For example, if you have a paragraph <p>Hello, World!</p>, the text "Hello, World!" is a text node.

**Document Node:** The top-level node in the DOM hierarchy is the document node, representing the entire HTML document. It serves as the entry point for accessing and manipulating the content of the web page.

**E.g.**
<!DOCTYPE html>
<html>
<head>
  <title>DOM Selectors Example</title>
</head>
<body>
  <h1 id="title">Hello, World!</h1>
  <ul>
    <li class="item">Item 1</li>
    <li class="item">Item 2</li>
    <li class="item">Item 3</li>
  </ul>
  <div data-role="content">This is a div with custom data attribute</div>
</body>
</html>

**Selecting by ID:**
const titleElement = document.getElementById('title');
console.log(titleElement.textContent); // Output: "Hello, World!"

**Selecting by Class:**
const items = document.getElementsByClassName('item');
for (const item of items) {
  console.log(item.textContent); // Output: "Item 1", "Item 2", "Item 3"
}

**Selecting by Tag Name:**
const listItems = document.getElementsByTagName('li');
for (const listItem of listItems) {
  console.log(listItem.textContent); // Output: "Item 1", "Item 2", "Item 3"
}

**Selecting by Custom Data Attribute:**
const contentElement = document.querySelector('[data-role="content"]');
console.log(contentElement.textContent); // Output: "This is a div with custom data attribute"

## 9. Add and remove DOM nodes to change the content on the page
**Adding DOM Nodes:**

**Adding a New Paragraph:**
// Create a new paragraph element
const newParagraph = document.createElement('p');
newParagraph.textContent = 'This is a new paragraph.';

// Add the new paragraph to the document
document.body.appendChild(newParagraph);
_This code creates a new <p> element, sets its text content, and appends it to the document's <body>, adding a new paragraph to the page._

**Inserting an Element Before Another:**
// Create a new div element
const newDiv = document.createElement('div');
newDiv.textContent = 'I come before the existing div.';

// Reference the existing div
const existingDiv = document.querySelector('.existing-div');

// Insert the new div before the existing div
existingDiv.parentNode.insertBefore(newDiv, existingDiv);
In this example, a new <div> is created and inserted before an existing <div> on the page.

**Removing DOM Nodes:**

**Removing an Element:**
// Reference the element to remove
const elementToRemove = document.getElementById('element-to-remove');

// Remove the element from its parent
elementToRemove.parentNode.removeChild(elementToRemove);
This code finds an element by its ID and removes it from the DOM.

Removing All Children of an Element:
// Reference the parent element
const parentElement = document.querySelector('.parent-element');

// Remove all child elements
while (parentElement.firstChild) {
  parentElement.removeChild(parentElement.firstChild);
}
_This example removes all child elements from a specified parent element._

## 10. Toggle the classes applied to DOM nodes to change their CSS properties
Certainly! Here are examples of toggling classes applied to DOM nodes to change their CSS properties:

**Toggling Classes**:

1. **Toggle Class with JavaScript**:
   // Find the element you want to toggle a class on
   const element = document.getElementById('my-element');

   // Toggle a class on the element
   element.classList.toggle('active');
   ```
   In this example, we find an element by its ID and toggle the class "active" on that element. This can be used, for example, to change the appearance of an element when a button is clicked.

2. **Toggle Class with Event Listeners**:
   html:
   <button id="toggle-button">Toggle Class</button>
   <div id="element-to-toggle">This is a div element.</div>

   javascript:
   // Add a click event listener to the button
   const toggleButton = document.getElementById('toggle-button');
   const elementToToggle = document.getElementById('element-to-toggle');

   **toggleButton.addEventListener('click', () => {
     elementToToggle.classList.toggle('highlight');
   });**
   
In this example, a button and a div element are defined in the HTML. When the button is clicked, it adds or removes the "highlight" class from the div, toggling its appearance.

_**Can use this instead of elementToToggle.classList.add('highlight')/remove('highlight')**_

**CSS Styles Affected by Toggled Classes**:

Here's an example of how you can use toggled classes to change CSS properties, such as background color:
css:
/* CSS */
.highlight {
  background-color: yellow;
}

By toggling the "highlight" class on an element, you can dynamically change its background color to yellow. You can apply this principle to various CSS properties, creating interactive and responsive web designs.

## 11. Use consistent layout and spacing
Use same stylesheet and layout across site.
**CSS variables:**
:root {
  --primary-color: #007bff;
  --font-family: 'Arial', sans-serif;
  --spacing-unit: 8px;
}

button {
  background-color: var(--primary-color);
  font-family: var(--font-family);
  margin: var(--spacing-unit);
  padding: var(--spacing-unit * 2);
}


**Stacking:**
.stack-sm > * + * {
  margin-top: 0.5rem;
}
.stack-md > * + * {
  margin-top: 1rem;
}
.stack-lg > * + * {
  margin-top: 2rem;
}
.stack-xl > * + * {
  margin-top: 4rem;
}

**Modifier Classes:**
.center {
  max-width: 30rem;
  margin-left: auto;
  margin-right: auto;
}
.width-sm {
  max-width: 20rem;
}
.width-lg {
  max-width: 40rem;
}
.width-xl {
  max-width: 60rem;
}

## 12. Follow a spacing guideline to give our app a consistent feel
Consistency in spacing is a fundamental aspect of web design, ensuring that your app or website looks polished and professional. Spacing guidelines help maintain a uniform layout. Here's an example of a simple spacing guideline in CSS:

**Defining spacing variables**
:root {
  --spacing-unit: 1rem;
}

**Applying the guideline**
.container {
  margin: var(--spacing-unit);
  padding: var(--spacing-unit * 2);
}

.button {
  margin: 0 var(--spacing-unit);
}
In this example, we define a CSS variable --spacing-unit that represents a base spacing unit. We then apply this spacing unit consistently across the design to ensure that margins and padding are uniform. 

## 13. Debug client side JS in our web browser
**Example using the Chrome DevTools:**
Open DevTools: Press F12 or Ctrl + Shift + I on Windows/Linux (or Cmd + Option + I on Mac) to open Chrome DevTools.
Debugging Breakpoints: Set breakpoints in your JavaScript code by clicking on the line number where you want to pause execution.
Inspect Variables: Inspect and monitor variables, objects, and network requests in the DevTools panel to understand your code's behavior.
Console Errors: Check the Console tab for error messages and use console.log() to log information that helps in debugging.

## 14. Use console.log() to help us debug our code
The console.log() method is a developer's best friend when it comes to debugging JavaScript. It allows you to print information and variables to the browser console for analysis. 

**E.g.**
function divide(a, b) {
  if (b === 0) {
    console.error("Division by zero is not allowed.");
    return;
  }
  console.log(`Dividing ${a} by ${b}`);
  return a / b;
}

const result = divide(10, 2);
console.log(`Result: ${result}`);

In this example, we use console.log() to print messages and variable values, which helps us track the code's flow and identify potential issues. Additionally, we use console.error() to report errors, making debugging more efficient.
