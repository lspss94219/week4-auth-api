# Week 4 Authentication API

A simple FastAPI authentication service featuring user registration, Argon2 password hashing, JWT token issue/verification, and protected profile endpoints.

## Installation & Setup

1. **Clone the repository:**
   ```bash
   git clone <YOUR_GITHUB_REPO_URL>
   cd week4-auth-api
   ```

2. Virtual environment
   ```
   python3 -m venv venv
   source venv/bin/activate
   ```

3. Install requirements
   ```
   pip install -r requirements.txt
   ```

4. Set the JWT Secret'
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

   test_password_hash: Passed (Verifies password hashing & checking via Argon2)
   test_login_and_profile: Passed (Tests registration, login, and token-based profile retrieval)
   test_profile_requires_token: Passed (Rejects unauthenticated requests with 401)
   test_duplicate_registration: Passed (Prevents duplicate email registration with 409)
   test_wrong_password_login: Passed (Rejects wrong credentials with 401)
   test_invalid_registration_data: Passed (Validates request bodies with 422)
   
