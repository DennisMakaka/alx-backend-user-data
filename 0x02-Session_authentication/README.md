# Session Authentication

## Project Overview
This project focuses on implementing Session Authentication for a web application. Session authentication is a mechanism that maintains user sessions after successful login, allowing users to access protected resources without re-authenticating for each request. This is a fundamental concept in web development, ensuring secure, stateful communication between the client and server.

## Learning Objectives
By the end of this project, you will be able to:
- Understand the difference between Session Authentication and other authentication methods (e.g., Basic Authentication, Token-based Authentication).
- Implement session management in a web application.
- Use cookies to securely maintain user sessions.
- Build and manage session storage for tracking active sessions.
- Understand security measures to mitigate session-related vulnerabilities (e.g., session hijacking, CSRF).

## Requirements
- All code should be written in Python 3.
- The project must follow PEP 8 guidelines.
- The back-end should handle session creation, validation, and destruction.
- Secure cookies must be used for session management.
- Ensure proper error handling and edge case management.

## Project Setup
1. Clone the repository and navigate to the project directory.
2. Create a virtual environment and activate it.
3. Install project dependencies from the requirements file.
4. Run the server to start the application.

## Features
- **Session Login**: Users authenticate by sending login credentials. A session ID is generated and stored in cookies for subsequent requests.
- **Session Validation**: Middleware checks for valid session IDs in incoming requests. Users without a valid session are redirected or denied access.
- **Session Logout**: Users can log out, destroying their session in the back-end.

## Security Measures
The application implements several security measures:
- Secure and HTTP-only cookies to prevent unauthorized access.
- Short session lifetimes to minimize risk exposure.
- CSRF protection to guard against cross-site request forgery attacks.
- Prevention of session fixation attacks.

## Endpoints
- **POST /auth/login**: Log in and create a session.
- **GET /auth/status**: Check session validity.
- **POST /auth/logout**: Log out and destroy the session.
- **GET /protected**: Access a protected resource.

## How It Works
### Login Process
1. A user provides valid credentials to the login endpoint.
2. The server verifies the credentials and generates a unique session ID.
3. The session ID is stored on the server and sent to the client as a cookie.

### Session Validation
1. Each subsequent request includes the session ID in the cookies.
2. Middleware validates the session ID against the server's session store.
3. If valid, the request proceeds; otherwise, access is denied.

### Logout Process
1. The session ID is invalidated on the server when the user logs out.
2. The client is instructed to delete the session cookie.

## Usage
You can use tools like Postman or cURL to test the endpoints. Once authenticated, include the session cookie in subsequent requests to access protected resources.

## Security Considerations
- Always use Secure and HttpOnly attributes for cookies.
- Implement CSRF protection using tokens.
- Ensure sessions expire after a reasonable timeout.
- Use HTTPS to encrypt communication between the client and server.

