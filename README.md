# FastAPI CMS API - A Lightweight Content Management System 🚀

![GitHub release](https://img.shields.io/github/release/MesafeN/fastapi-cms-api.svg) ![License](https://img.shields.io/badge/license-MIT-blue.svg)

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Installation](#installation)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)
- [Authentication](#authentication)
- [Testing](#testing)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## Overview
Welcome to the FastAPI CMS API repository! This project provides a lightweight content management system (CMS) API built with FastAPI. It features user authentication, blog management, and like/unlike functionality. The API is secured with JWT and supports versioning. You can find the latest releases [here](https://github.com/MesafeN/fastapi-cms-api/releases).

## Features
- **User Authentication**: Secure user login and registration using JWT.
- **Blog Management**: Create, read, update, and delete blog posts.
- **Like/Unlike Functionality**: Users can like or unlike blog posts.
- **API Versioning**: Easily manage different versions of the API.
- **100% Test Coverage**: All functionalities are covered with tests using pytest.

## Technologies Used
This project leverages a variety of technologies:
- **FastAPI**: A modern web framework for building APIs with Python 3.6+ based on standard Python type hints.
- **SQLAlchemy**: An ORM for managing database interactions.
- **Pydantic**: For data validation and settings management.
- **JWT**: For secure authentication.
- **pytest**: For testing the API functionalities.

## Installation
To set up the FastAPI CMS API on your local machine, follow these steps:

1. **Clone the repository**:
   ```bash
   git clone https://github.com/MesafeN/fastapi-cms-api.git
   cd fastapi-cms-api
   ```

2. **Create a virtual environment**:
   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```

3. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Run the application**:
   ```bash
   uvicorn app.main:app --reload
   ```

5. **Visit the API documentation**:
   Open your browser and go to `http://127.0.0.1:8000/docs` to view the interactive API documentation.

## Usage
Once the application is running, you can use the API endpoints to manage users and blog posts. 

### Example Requests
- **Register a new user**:
  ```bash
  curl -X POST "http://127.0.0.1:8000/users/register" -H "Content-Type: application/json" -d '{"username": "testuser", "password": "testpass"}'
  ```

- **Login**:
  ```bash
  curl -X POST "http://127.0.0.1:8000/users/login" -H "Content-Type: application/json" -d '{"username": "testuser", "password": "testpass"}'
  ```

- **Create a new blog post**:
  ```bash
  curl -X POST "http://127.0.0.1:8000/posts" -H "Authorization: Bearer <token>" -H "Content-Type: application/json" -d '{"title": "My First Post", "content": "Hello, world!"}'
  ```

## API Endpoints
Here’s a brief overview of the available API endpoints:

### User Endpoints
- **POST /users/register**: Register a new user.
- **POST /users/login**: Authenticate a user and receive a JWT.

### Blog Post Endpoints
- **GET /posts**: Retrieve all blog posts.
- **GET /posts/{id}**: Retrieve a specific blog post by ID.
- **POST /posts**: Create a new blog post.
- **PUT /posts/{id}**: Update an existing blog post.
- **DELETE /posts/{id}**: Delete a blog post.
- **POST /posts/{id}/like**: Like a blog post.
- **POST /posts/{id}/unlike**: Unlike a blog post.

## Authentication
The API uses JWT for authentication. After logging in, you will receive a token. Include this token in the `Authorization` header for protected routes.

### Example
```bash
Authorization: Bearer <your_jwt_token>
```

## Testing
The project includes tests to ensure all functionalities work as expected. To run the tests, use the following command:

```bash
pytest
```

Make sure your database is set up correctly before running the tests.

## Contributing
Contributions are welcome! If you have suggestions or improvements, please fork the repository and submit a pull request. Make sure to follow the coding standards and include tests for new features.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contact
For questions or feedback, feel free to reach out via GitHub or create an issue in the repository. You can find the latest releases [here](https://github.com/MesafeN/fastapi-cms-api/releases).