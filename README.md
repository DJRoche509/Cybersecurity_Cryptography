# Cybersecurity_Cryptography
The Hashing app implements a minimal user authentication system using Express server

Overview
The hashing app is a simple Express server that implements a minimal user authentication system. This section gives an overview of what you’ll be building and how the codebase works.

Note that we’ll only cover parts of the codebase that are relevant. Feel free to investigate and play around with the rest of the codebase on your own.

What you’ll be building
You’ll implement the POST /login and POST /register endpoints in server.js. We’ve left some pseudocode in TODO comments to give you an idea of what you’ll do:

server.js
// Handle user login.
app.post("/login", (req, res) => {
  // TODO: Get the username and password from form data
  // TODO: Attempt to retrieve the user from the database
  // TODO: If the user exists, check if the password matches the user's password
  // TODO: Log the user in by storing their username in the session
  // TODO: Display a success message and redirect to /login/success
  // TODO: If the user doesn't exist or the password doesn't match, display an error
  //       message and redirect to the homepage
});

// Handle user registration.
app.post("/register", (req, res) => {
  // TODO: Get the username and password from form data
  // TODO: Check if username already exists in the database
  // TODO: If it doesn't, create a new user and store it in the database
  // TODO: Display a success message to the user
  // TODO: If the user already exists, display an error message
  // TODO: Either way, redirect to the homepage so they can log in
});
At first, you’ll implement these route handlers without hashing passwords. Once you get everything working, you’ll add password hashing with the bcryptjs package.

The mock database
We’re using an object called db as a mock database. You’ll find it near the top of server.js. It contains two users: test and testhashed.

server.js
const db = {
  test: {
    username: "test",
    password: "test",
  },
  testhashed: {
    username: "testhashed",
    password: "$2a$10$7WK77kJZ0qzrcgOoE3MszOWuPz2bzPueuSCePScbQnkKwCUx2045q",
  },
};
