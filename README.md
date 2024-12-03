#  🔐  `</DenAuth>`

A [Rust](https://www.rust-lang.org/) based authentication backend solution using the [Axum](https://github.com/tokio-rs/axum]) framework. It includes user authentication, email verification, JWT authentication, and a connection to a PostgreSQL database.

## Features
* **User Authentication**: Register, login, password reset functionality,
* **Email Verification**: User receives an email to verify their accounts,
* **PostgreSQL Integration**: Store and manage user data securely,
* **JWT Authentication**: Secure API endpoints with JSON Web Tokens (JWT)
* **Middleware**: Implement custom middleware for authentication
* **Testing with Postman**: A full Postman collection is provided to test all API endpoints

## Prerequisites
To run this code base, you will need:
* [Rust](https://www.rust-lang.org/) installed on you machine,
* [PostgreSQL](https://www.postgresql.org/) installed and running locally or remotely,
* [SQLx-CLI](https://crates.io/crates/sqlx-cli) for database migrations,
* and [Postman](https://www.postman.com/) for testing API endpoints.

## Installation
1. **Clone the repository**
```bash
git clone git@github.com:ylcnky/DenAuth.git
cd DenAuth
```
2. **Install dependencies:**
```bash
cargo install --path .
```
3. **Setup PostgreSQL**
```bash
DATABASE_URL=postgres://user:password@localhost/dbname
```
4. **Run migrations**
```bash
sqlx migrate run
```
5. **Start the server**
```bash
cargo run
```

The server will be running on `http://127.0.0.1:800`

## Email Verification Setup
To enable email verification, you will need to configure an email service provider. Update the following environment variables in your `.env` file
```bash
SMTP_SERVER=smtp.your-email-provider.com
SMTP_PORT=587
SMTP_USER=your-email@example.com
SMTP_PASSWORD=your-email-password
```

## API Testing with Postman
You can test all the API endpoints using the provided Postman collection. Download the Postman collection [here](https://github.com/ylcnky/DenAuth/blob/master/postman_collection.json) and import it into Postman.

API Endpoints:

POST `/api/auth/register`: Register a new user

POST `/api/auth/login`: Login with an existing user

GET `/api/auth/forgot-password`: Request password reset

POST `/api/auth/reset-password`: Reset user password

GET `/api/auth/verify`: Verify email with token

GET `/api/users/me`: Get current user profile (JWT required)

## Configuration
The application requires a .env file for configuration. Below are the required environment variables:
```bash
# -----------------------------------------------------------------------------
# Database (PostgreSQL)
# -----------------------------------------------------------------------------
DATABASE_URL=postgresql://postgres:password@localhost:5432/axum_auth

# -----------------------------------------------------------------------------
# JSON Web Token Credentials
# -----------------------------------------------------------------------------
JWT_SECRET_KEY=my_ultra_secure_jwt_secret_key
JWT_MAXAGE=60

# -----------------------------------------------------------------------------
# SMTP Server Settings
# -----------------------------------------------------------------------------
SMTP_SERVER=smtp.your-email-provider.com
SMTP_PORT=587                     # Common ports: 587 (TLS), 465 (SSL), 25 (non-secure)
SMTP_USERNAME=your_email@example.com
SMTP_PASSWORD=your_email_password
SMTP_FROM_ADDRESS=no-reply@yourdomain.com
```