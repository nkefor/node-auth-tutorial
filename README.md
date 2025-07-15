
# Node.js & Express User Authentication Tutorial

This repository contains the source code for a tutorial on implementing user authentication in a Node.js and Express application. It provides a basic framework for user registration, login, and logout functionality.

## Features

-   User registration with password hashing
-   User login with session management
-   User logout
-   Protected routes

## Technologies Used

-   **Node.js:** A JavaScript runtime built on Chrome's V8 JavaScript engine.
-   **Express.js:** A fast, unopinionated, minimalist web framework for Node.js.
-   **Passport.js:** Simple, unobtrusive authentication for Node.js.
    -   `passport-local`: Passport strategy for authenticating with a username and password.
-   **bcrypt:** A library for hashing passwords.
-   **express-session:** Simple session middleware for Express.
-   **Jade (Pug):** A high-performance template engine.

## Getting Started

### Prerequisites

-   Node.js and npm installed on your machine.
-   Git for cloning the repository.

### Installation

1.  Clone the repository to your local machine:

    ```bash
    git clone https://github.com/nkefor/node-auth-tutorial.git
    ```

2.  Navigate into the project directory:

    ```bash
    cd node-auth-tutorial
    ```

3.  Install the dependencies:

    ```bash
    npm install
    ```

### Running the Application

To start the development server, run the following command:

```bash
SET DEBUG=node-auth-tutorial:* & npm start
```

Open your browser and navigate to `http://localhost:3000` to see the application in action.

## How It Works

The application uses an in-memory array to store user data for simplicity. In a production environment, you should replace this with a persistent database like MongoDB or PostgreSQL.

-   **Registration (`/register`):** New users can sign up. Their password is encrypted using `bcrypt` before being stored.
-   **Login (`/login`):** Registered users can log in. `Passport.js` handles the authentication process by comparing the provided password with the stored hash.
-   **Logout (`/logout`):** Destroys the user session.

This project serves as a starting point. For production use, consider adding features like password complexity rules, account lockout mechanisms, and a proper database integration.
