# RBAC with JWT and Pagination in Node.js and MongoDB

This project demonstrates **Role-Based Access Control (RBAC)** using **JSON Web Tokens (JWT)** for secure authentication and authorization.

---

## Features

- **Authentication:** Secure login and signup.
- **Validation:** Ensures user input is accurate and valid.
- **Authorization:** Enforces role-based access for endpoints.
- **Role-Based Access Control:** Users' roles determine their permitted actions.
- **CRUD Operations:** Manage posts with Create, Read, Update, and Delete functionalities.
- **Pagination:** Efficient handling of large datasets.

---

## Setup and Usage

1. Clone the repository:
2. Install dependencies:
    npm install
3. Start the server:
    npm start

## Data Models
User Model: Handles user authentication, authorization, and validation.
Post Model: Manages CRUD operations for posts in the MongoDB database.

## API Flows
Use the Postman Collection to explore all endpoints.

## Key Endpoints:
* Public Endpoints:

    * POST /api/auth/login: User login.
    * POST /api/auth/signup: User registration.
* Protected Endpoints: Require JWT authentication and role-based authorization.

    * Normal User: Can only view posts (with optional pagination for large datasets).
    * Admin User: Can perform all CRUD operations on posts.
## Default Admin Credentials:
When the server initializes and the User collection is empty, an Admin account is created automatically:

* Name: admin
* Email: admin@admin.com
* Password: admin

## Folder Structure
* validator: Contains logic for validating user inputs.
* routes: Defines API endpoints and associates them with middlewares.
* models: Database schemas used across the project.
* middleware: Contains authorization and authentication logic.
* controller: Manages business logic and database operations.
* config: Stores configuration details like JWT secrets.

## Authorization and RBAC Details
JWT is used to authenticate users and embed their roles within the token payload. Each API endpoint enforces role-specific permissions:

* Authentication: Validates the JWT token in request headers.
* Authorization: Ensures users have the necessary roles for accessing specific resources.

## Role Permissions:
* Normal User:
    * Access limited to reading posts.
    * Supports paginated views for efficient data handling.
* Admin User:
    * Full control over the posts, including create, update, and delete operations.
* Security Note:
    * All CRUD operations require JWT-based authentication, and only authorized users with appropriate roles can perform certain actions.

## Security Note:
All CRUD operations require JWT-based authentication, and only authorized users with appropriate roles can perform certain actions.
