# Week 4 Authentication API

A simple FastAPI authentication service featuring user registration, Argon2 password hashing, JWT token issue/verification, and protected profile endpoints.

## Installation & Setup

1. Virtual environment
   ```
   python3 -m venv venv
   source venv/bin/activate
   ```

2. Install requirements
   ```
   pip install -r requirements.txt
   ```

3. Set the JWT Secret'
   Generate a safe random 32 character token
   ```
   python -c "import secrets; print(secrets.token_hex(32))"
   ```
   Set it as an environment variable
   ```
   export JWT_SECRET="put_your_generated_secret_here"
   ```

## Running the Application
   ```
   uvicorn main:app --reload
   ```
   Visit http://127.0.0.1:8000/docs and test

## Tests
   ```
   python -m purest -v
   ```

## Test Summary
```
   tests/test_auth.py::test_password_hash PASSED
   tests/test_auth.py::test_login_and_profile PASSED
   tests/test_auth.py::test_profile_requires_token PASSED
   tests/test_auth.py::test_duplicate_registration PASSED
   tests/test_auth.py::test_wrong_password_login PASSED
   tests/test_auth.py::test_invalid_registration_data PASSED

6 passed in 0.43s
   
