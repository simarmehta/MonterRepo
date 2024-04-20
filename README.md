Below is a comprehensive README file for your project that outlines the setup, usage, and functionality of your Express.js application integrated with MongoDB. This documentation will guide other developers or users through setting up and using the application effectively.

### README.md
```markdown
# Express Authentication API

This project implements a complete authentication system using Express.js and MongoDB. It supports user registration, OTP (One-Time Password) email verification, login, and access to protected routes using JWT (JSON Web Tokens).

## Features

- User registration with email and password.
- OTP generation and verification via email.
- Password hashing and secure storage.
- JWT-based authentication for protected routes.
- Retrieval of user information via JWT.

## Prerequisites

Before running this project, you will need the following installed:
- Node.js
- MongoDB
- A mail service account (e.g., Gmail for nodemailer)

## Getting Started

Follow these steps to get your application up and running on your local machine for development and testing purposes.

### Step 1: Clone the Repository

Clone this repository to your local machine using:

```bash
git clone https://your-repository-url.git
cd your-project-directory
```

### Step 2: Install Dependencies

Install the necessary Node.js dependencies by running:

```bash
npm install
```

### Step 3: Set Up Environment Variables

Create a `.env` file in the root directory of your project and add the following variables:

```plaintext
PORT=3000
MONGODB_URI=mongodb://localhost:27017/yourdbname
JWT_SECRET=your_jwt_secret
EMAIL_USERNAME=your_email@example.com
EMAIL_PASSWORD=your_email_password
```

Make sure to replace `your_jwt_secret`, `yourdbname`, `your_email@example.com`, and `your_email_password` with your actual data.

### Step 4: Start MongoDB

Ensure that MongoDB is running on your machine. If you have MongoDB installed locally, you can start it with:

```bash
mongod
```

### Step 5: Run the Server

Start the server with the following command:

```bash
npm start
```

This command will launch the server on `http://localhost:3000`.

## API Endpoints

The following endpoints are available in this API:

### POST /register

- Description: Register a new user.
- Payload: `{ "email": "user@example.com", "password": "password123" }`
- Response: Success message and OTP sent to email.

### POST /verify-otp

- Description: Verify OTP sent to email.
- Payload: `{ "email": "user@example.com", "otp": "123456" }`
- Response: Success or error message.

### POST /login

- Description: Login a user.
- Payload: `{ "email": "user@example.com", "password": "password123" }`
- Response: JWT token on successful login.

### GET /user

- Description: Retrieve user information.
- Headers: `Authorization: Bearer <jwt_token>`
- Response: User details.

## Security

This project uses bcrypt for password hashing, JWT for session management, and nodemailer for email operations, ensuring a secure and functional authentication system.

## Testing

You can test the API endpoints using Postman or any other API testing tool by sending requests to `http://localhost:3000` followed by the specific endpoint.

## Conclusion

This Express.js application provides a robust authentication system suitable for integrating into more complex applications requiring user management and secure access control.

```

This README provides a clear and thorough guide for setting up and interacting with your project. It covers the key components and offers detailed instructions to ensure anyone checking out the repository can get it running without prior knowledge of the project's specifics.