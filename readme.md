# Authentication Project

## Description

This is a Django-based authentication project that provides user registration, login, and password management functionalities.

## Installation

1. **Clone the repository:**

   ```bash
   git clone <repository-url>
   cd AuthenticationProject
   ```

2. **Create a virtual environment:**

   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```

3. **Install dependencies:**

   ```bash
   pip install -r requirements.txt
   ```

4. **Set up the database:**

   ```bash
   python manage.py migrate
   ```

5. **Create a superuser (optional):**

   ```bash
   python manage.py createsuperuser
   ```

6. **Run the server:**
   ```bash
   python manage.py runserver
   ```

## Usage

- Navigate to `http://127.0.0.1:8000/` to access the application.
- You can register a new user, log in, and manage your account.

## API Documentation

### User Registration

- **Endpoint:** `/register/`
- **Method:** `POST`
- **Parameters:**
  - `first_name`: User's first name (string)
  - `last_name`: User's last name (string)
  - `username`: Unique username (string)
  - `email`: User's email address (string)
  - `password`: User's password (string)
- **Response:**
  - Success: Redirects to login page with success message.
  - Error: Returns error messages for existing username/email or weak password.

### User Login

- **Endpoint:** `/login/`
- **Method:** `POST`
- **Parameters:**
  - `username`: User's username (string)
  - `password`: User's password (string)
- **Response:**
  - Success: Redirects to home page.
  - Error: Returns error message for invalid credentials.

### Password Management

- **Forgot Password:**

  - **Endpoint:** `/forgot-password/`
  - **Method:** `GET`
  - **Description:** Displays a form to request a password reset.

- **Reset Password:**
  - **Endpoint:** `/reset-password/<str:reset_id>/`
  - **Method:** `POST`
  - **Parameters:**
    - `reset_id`: Unique identifier for the password reset request.
    - `new_password`: New password (string)
  - **Response:**
    - Success: Redirects to login page with success message.
    - Error: Returns error message for weak password.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Django documentation for guidance on building web applications.
- Various online resources for learning and troubleshooting.
