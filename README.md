# Chatbot Using HTML, CSS, and Java with Gemini API

## Overview

This project is a web-based chatbot that utilizes the Gemini API for natural language processing. The front-end is built with HTML and CSS, while the back-end is powered by Java to handle API requests and responses.

## Features

- Interactive chatbot interface
- AI-powered responses using the Gemini API
- User-friendly and responsive UI
- Secure API integration

## Technologies Used

- **Front-end:** HTML, CSS
- **Back-end:** Java
- **API:** Gemini API

## Installation and Setup

### Prerequisites

Ensure you have the following installed on your system:

- Java Development Kit (JDK) 11+
- Apache Tomcat or any Java web server
- A Gemini API key
- Basic knowledge of HTML, CSS, and Java

### Steps to Set Up the Project

1. **Clone the Repository**
   ```sh
   git clone https://github.com/your-repo/chatbot.git
   cd chatbot
   ```
2. **Set Up the Front-End**
   - Place `index.html` and `styles.css` in the `webapp` directory.
3. **Configure the Back-End**
   - Create a Java Servlet to handle API requests.
   - Add dependencies for HTTP requests (e.g., `org.apache.httpcomponents` for handling API calls).
4. **Obtain a Gemini API Key**
   - Sign up at Gemini API's official website.
   - Store the key securely in your Java application.
5. **Run the Application**
   - Deploy the Java servlet to Tomcat or another Java web server.
   - Open `index.html` in your browser and start chatting!

## Sample Code

### HTML (`index.html`)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Chatbot</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="chat-container">
        <div id="chat-box"></div>
        <input type="text" id="user-input" placeholder="Type a message...">
        <button onclick="sendMessage()">Send</button>
    </div>
    <script src="script.js"></script>
</body>
</html>
```

### CSS (`styles.css`)

```css
body {
    font-family: Arial, sans-serif;
    text-align: center;
}
.chat-container {
    width: 300px;
    margin: auto;
    padding: 10px;
    border: 1px solid #ccc;
}
```

### Java Servlet (`ChatbotServlet.java`)

```java
import java.io.*;
import javax.servlet.*;
import javax.servlet.http.*;
import java.net.*;
import java.nio.charset.StandardCharsets;

public class ChatbotServlet extends HttpServlet {
    private static final String GEMINI_API_KEY = "your_api_key_here";

    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        String userMessage = request.getParameter("message");
        String botResponse = callGeminiAPI(userMessage);
        response.setContentType("application/json");
        response.getWriter().write("{\"response\": \"" + botResponse + "\"}");
    }

    private String callGeminiAPI(String message) {
        // Implement API call logic here
        return "Hello! How can I assist you?"; // Placeholder response
    }
}



