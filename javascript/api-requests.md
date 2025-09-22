---
description: How to make API requests in JavaScript.
---

# API Requests

## GET request

Perform API requests using the standard JavaScript approach of Fetch.&#x20;

```javascript
// API for get requests
let res = await fetch("https://jsonplaceholder.typicode.com/todos/1");
let json = await res.json();

console.log(json);

return [Object.keys(json), Object.values(json)];
```

## GET request with error handling&#x20;

```javascript
async function getData() {
  const url = "https://jsonplaceholder.typicode.com/todos/1";
  try {
    const response = await fetch(url);
    if (!response.ok) {
      throw new Error(`Response status: ${response.status}`);
    }

    const json = await response.json();
    // Return the JSON object as a 2D array
    return [Object.keys(json), Object.values(json)];
  } catch (error) {
    console.error(error.message);
    // Return the error message to the sheet
    return `Error: ${error.message}`;
  }
}

// Call the function and return its result to the sheet
return await getData();
```

## POST request with body

```javascript
async function getData() {
  // replace with your API URL and body parameters 
  const url = "https://example.org/products.json";
  const requestBody = {
    key1: "value1",
    key2: "value2"
  };

  try {
    const response = await fetch(url, {
      method: "POST",
      headers: {
        "Content-Type": "application/json"
      },
      body: JSON.stringify(requestBody)
    });

    if (!response.ok) {
      throw new Error(`Response status: ${response.status}`);
    }

    const json = await response.json();
    // Return the JSON object as a 2D array
    return [Object.keys(json), Object.values(json)];
  } catch (error) {
    console.error(error.message);
    // Return the error message to the sheet
    return `Error: ${error.message}`;
  }
}

// Call the function and return its result to the sheet
return await getData();
```

If you ever get stuck with JavaScript code (especially requests) that doesn't seem to be working but is showing no error, you may be missing an `Await` somewhere that it is needed.&#x20;
