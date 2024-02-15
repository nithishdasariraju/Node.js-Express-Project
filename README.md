**README.md**

# Creating a Node.js Express Project to Build Fake REST CRUD API From JSON Using JSON Server Library

## Introduction
This guide will walk you through the steps to create a Node.js Express project for building a fake REST CRUD API directly from JSON data using the JSON Server library. With this setup, you can quickly prototype or test client-side applications without needing a backend server.

## Prerequisites
- Node.js installed on your machine. You can download and install Node.js from [here](https://nodejs.org/).

## Step-by-Step Procedure

### 1. Initialize Node.js Project
Create a new directory for your project and navigate into it using your terminal or command prompt. Then, initialize a new Node.js project by running the following command:

```bash
npm init -y
```

### 2. Install Required Dependencies
Install the necessary dependencies for the project, including Express and JSON Server, by running the following command:

```bash
npm install express json-server
```

### 3. Create JSON Data File
Create a JSON file containing the data you want to serve as your API endpoints. For example, you can create a file named `data.json` with sample JSON data:

```json
{
  "posts": [
    { "id": 1, "title": "First Post", "body": "This is the first post." },
    { "id": 2, "title": "Second Post", "body": "This is the second post." }
  ]
}
```

### 4. Create Express Server
Create a new JavaScript file, e.g., `server.js`, and set up an Express server to serve your JSON data and act as a proxy to JSON Server. Here's a basic example:

```javascript
const express = require('express');
const jsonServer = require('json-server');
const path = require('path');

const app = express();
const router = jsonServer.router(path.join(__dirname, 'data.json'));
const middlewares = jsonServer.defaults();

app.use('/api', middlewares, router);

const PORT = process.env.PORT || 3000;
app.listen(PORT, () => {
  console.log(`Server running on port ${PORT}`);
});
```

### 5. Start the Server
Run the Express server by executing the following command:

```bash
node server.js
```

Your fake REST CRUD API server is now running locally. You can access your API endpoints at `http://localhost:3000/api/posts`, where `posts` is the resource defined in your JSON data file.

### 6. Test API Endpoints
You can now test your API endpoints using tools like Postman, cURL, or by making HTTP requests from your client-side application.

## Conclusion
Congratulations! You have successfully created a Node.js Express project for building a fake REST CRUD API from JSON using the JSON Server library. Feel free to customize and extend this setup according to your project requirements.

## Resources
- [Express.js Documentation](https://expressjs.com/)
- [JSON Server Documentation](https://github.com/typicode/json-server)

Happy coding! 🚀
