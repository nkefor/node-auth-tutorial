# Node.js & Express User Authentication Tutorial

This repository contains the source code for a tutorial on implementing user authentication in a Node.js and Express application. It provides a basic framework for user registration, login, and logout functionality.

## Features

*   **User Registration:** New users can create an account. Passwords are encrypted using `bcrypt` to ensure security.
*   **User Login:** Registered users can log in to access protected content. The application uses `Passport.js` for authentication.
*   **Session Management:** `express-session` is used to maintain user sessions, allowing users to stay logged in across multiple requests.
*   **Protected Routes:** Certain routes are protected, meaning they can only be accessed by authenticated users.
*   **Password Hashing:** Passwords are not stored in plain text. Instead, they are hashed using `bcrypt` to prevent unauthorized access.

## Technologies Used

*   **Node.js:** A JavaScript runtime built on Chrome's V8 JavaScript engine.
*   **Express.js:** A fast, unopinionated, minimalist web framework for Node.js.
*   **Passport.js:** Simple, unobtrusive authentication for Node.js.
    *   `passport-local`: A Passport strategy for authenticating with a username and password.
*   **bcrypt:** A library for hashing passwords.
*   **express-session:** Simple session middleware for Express.
*   **Jade (Pug):** A high-performance template engine for writing clean, readable HTML.

## Getting Started

### Prerequisites

*   **Node.js and npm:** Ensure you have Node.js and npm installed on your machine. You can download them from [https://nodejs.org/](https://nodejs.org/).
*   **Git:** You will need Git to clone the repository. You can download it from [https://git-scm.com/](https://git-scm.com/).

### Installation

1.  **Clone the repository:**

    ```bash
    git clone https://github.com/nkefor/node-auth-tutorial.git
    ```

2.  **Navigate to the project directory:**

    ```bash
    cd node-auth-tutorial
    ```

3.  **Install the dependencies:**

    ```bash
    npm install
    ```

### Running the Application

To start the development server, run the following command:

```bash
SET DEBUG=node-auth-tutorial:* & npm start
```

This will start the application on `http://localhost:3000`. You can open your browser and navigate to this address to see the application in action.

## How It Works

This application uses an in-memory array to store user data. This is for demonstration purposes only. In a production environment, you should use a persistent database such as MongoDB, PostgreSQL, or MySQL.

### File Structure

*   **`app.js`:** The main application file. It contains the Express configuration, middleware, and Passport.js setup.
*   **`bin/www`:** The entry point of the application. It creates the HTTP server and listens for incoming requests.
*   **`public/`:** Contains static assets such as stylesheets, images, and client-side JavaScript.
*   **`routes/`:** Contains the route handlers for the application.
    *   `index.js`: Handles the main routes, including registration, login, and logout.
    *   `users.js`: An example of a protected route that can only be accessed by authenticated users.
*   **`views/`:** Contains the Jade (Pug) templates for the application.
    *   `layout.jade`: The main layout file.
    *   `index.jade`: The home page.
    *   `login.jade`: The login page.
    *   `register.jade`: The registration page.

### Authentication Flow

1.  **Registration:** When a user registers, their password is encrypted using `bcrypt` and stored in the `users` array.
2.  **Login:** When a user logs in, `Passport.js` authenticates them by comparing the provided password with the stored hash.
3.  **Session:** If the authentication is successful, a session is created for the user, and they are redirected to the home page.
4.  **Protected Routes:** For each subsequent request, the application checks if the user is authenticated before granting access to protected routes.

## Future Improvements

This project is a basic implementation of user authentication. For a production-ready application, you should consider the following improvements:

*   **Database Integration:** Replace the in-memory user store with a persistent database.
*   **Password Complexity:** Enforce password complexity rules to ensure that users choose strong passwords.
*   **Account Lockout:** Implement an account lockout mechanism to prevent brute-force attacks.
*   **Flash Messages:** Use flash messages to display success and error messages to the user.
*   **Third-Party Authentication:** Add support for third-party authentication providers such as Google, Facebook, and Twitter.