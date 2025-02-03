# Persisting User Data

When building web applications, it's important to save user data so that it stays available even after the page is refreshed or the browser is closed. There are several ways to do this on the client side, including **localStorage**, **cookies**, and even sending data to a server using the **Fetch API**. In this guide, we'll introduce these methods in simple language with clear examples.

- [Persisting User Data](#persisting-user-data)
  - [What Does It Mean to Persist Data?](#what-does-it-mean-to-persist-data)
  - [Using localStorage](#using-localstorage)
    - [Key Points](#key-points)
    - [Example: Saving and Retrieving Data](#example-saving-and-retrieving-data)
  - [Using Cookies](#using-cookies)
    - [Key Points](#key-points-1)
    - [Example: Setting a Cookie](#example-setting-a-cookie)
  - [Using the Fetch API to Persist Data Remotely](#using-the-fetch-api-to-persist-data-remotely)
    - [Key Points](#key-points-2)
    - [Example: Sending Data with Fetch](#example-sending-data-with-fetch)
  - [Comparing localStorage and Cookies](#comparing-localstorage-and-cookies)
  - [Security Considerations](#security-considerations)
  - [Key Takeaways](#key-takeaways)


## What Does It Mean to Persist Data?

Persisting data means storing information so that it remains available across different sessions or page loads. For example, a user’s preferences (like a dark or light theme) or items in a shopping cart can be saved and retrieved later.

## Using localStorage

**localStorage** is a built-in feature in modern web browsers that allows you to store key-value pairs. Data stored in localStorage remains available even after you close and reopen your browser, until it’s manually removed.

### Key Points

- **Persistence:** Data stays until explicitly deleted.
- **Capacity:** Can typically store around 5–10 MB per domain.
- **Data Type:** Only strings are stored; other data types must be converted using `JSON.stringify()` and `JSON.parse()`.

### Example: Saving and Retrieving Data

```js
// Saving data in localStorage
localStorage.setItem('username', 'Alice');

// Retrieving data from localStorage
const username = localStorage.getItem('username');
console.log(username); // Outputs: Alice

// Storing an object (must stringify)
const userPrefs = { theme: 'dark', fontSize: '16px' };
localStorage.setItem('prefs', JSON.stringify(userPrefs));

// Retrieving and parsing the object
const prefs = JSON.parse(localStorage.getItem('prefs'));
console.log(prefs.theme); // Outputs: dark
```

Using localStorage is great for non-sensitive data like user preferences or caching small amounts of data.  

## Using Cookies

**Cookies** are another way to store data in the browser. Unlike localStorage, cookies are automatically sent with every HTTP request, making them useful for session data and authentication. However, they are much smaller (around 4 KB per cookie) and can be set with an expiration date.

### Key Points

- **Automatic Transmission:** Cookies are sent to the server with each request.
- **Size Limitation:** Typically limited to about 4 KB.
- **Expiration:** Can have a set expiration time (or session-only if no expiration is set).
- **Security Options:** Cookies can be marked as `HttpOnly` (to prevent JavaScript access) or `Secure` (to allow only HTTPS).

### Example: Setting a Cookie

```typescript
// Setting a cookie that expires in 7 days
function setCookie(name, value, days) {
  const expires = new Date(Date.now() + days * 864e5).toUTCString();
  document.cookie = `${name}=${encodeURIComponent(value)}; expires=${expires}; path=/`;
}

// Get a cookie by name
function getCookie(name) {
  return document.cookie.split('; ').reduce((r, v) => {
    const parts = v.split('=');
    return parts[0] === name ? decodeURIComponent(parts[1]) : r;
  }, '');
}

setCookie('sessionId', 'abc123', 7);
console.log(getCookie('sessionId')); // Outputs: abc123
```

Cookies are ideal for small pieces of data that need to be communicated with the server, like session identifiers.

## Using the Fetch API to Persist Data Remotely

While localStorage and cookies are used for client-side storage, sometimes you need to save data on a server. The **Fetch API** provides a modern way to make HTTP requests from the browser. You can send user data to your server, where it can be saved in a database.

### Key Points

- **Promise-based:** Makes asynchronous requests with a cleaner syntax.
- **Flexible:** Supports various HTTP methods like GET, POST, PUT, and DELETE.
- **Usage Scenario:** Ideal for when you need to store data remotely (e.g., user profiles, shopping cart contents).

### Example: Sending Data with Fetch

```js
async function saveUserData(data) {
  try {
    const response = await fetch('https://example.com/api/save', {
      method: 'POST',
      headers: {
        'Content-Type': 'application/json'
      },
      body: JSON.stringify(data)
    });

    if (!response.ok) {
      throw new Error(`Error: ${response.status}`);
    }

    const result = await response.json();
    console.log('Data saved successfully:', result);
  } catch (error) {
    console.error('Failed to save data:', error);
  }
}

const userData = { username: 'Alice', theme: 'dark' };
saveUserData(userData);
```

This example shows how to send a POST request to save data on a server. We set the `Content-Type` header to indicate we are sending JSON data, and we handle errors if the request fails.  

## Comparing localStorage and Cookies

Both localStorage and cookies have their uses, and choosing between them depends on your needs:

| Feature              | localStorage                          | Cookies                                  |
|----------------------:|:---------------------------------------:|:------------------------------------------:|
| **Capacity**         | ~5–10 MB per domain                   | ~4 KB per cookie                         |
| **Data Persistence** | Remains until explicitly deleted      | Expires based on set expiration date     |
| **Transmission**     | Not sent with HTTP requests           | Automatically sent with each request     |
| **Usage**            | Caching, user preferences, non-sensitive data | Session data, authentication tokens       |

Cookies can be secured using flags like `HttpOnly` and `SameSite` to reduce vulnerabilities such as XSS (Cross-Site Scripting) and CSRF (Cross-site request forgery) attacks.  

## Security Considerations

- **Sensitive Data:** Avoid storing sensitive information in localStorage since it can be accessed by any script running on your page.
- **XSS Vulnerabilities:** Cookies can be marked as `HttpOnly` so that JavaScript cannot access them, reducing the risk of cross-site scripting attacks.
- **CSRF Risks:** Since cookies are sent automatically with each HTTP request, ensure you use strategies like the `SameSite` attribute or CSRF tokens to protect against cross-site request forgery.

Understanding these trade-offs helps you decide the best approach for your application's data persistence needs.

## Key Takeaways

- **localStorage** is great for storing larger amounts of non-sensitive data that should persist between sessions.
- **Cookies** are better suited for small pieces of data that need to be automatically transmitted to the server.
- **Fetch API** enables you to send and receive data from a server, which is essential for persisting data remotely.
- **Always consider security**: choose the appropriate method and security measures based on the type of data you're storing.
