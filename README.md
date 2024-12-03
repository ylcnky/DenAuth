# DenAuth

A Rust based, fully functional backend using the [Axum](https://github.com/tokio-rs/axum]) framework. It includes user authentication, email verification, and a connection to a PostgreSQL database.

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
1. Clone the repository
```bash
git clone git@github.com:ylcnky/DenAuth.git
cd DenAuth
```
2. Install dependencies:
```bash
cargo install --path .
```
3. Setup PostgreSQL
```bash
sqlx migrate run
```
4. Start the server
```bash
cargo run
```
