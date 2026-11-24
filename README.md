# Secure Login System (Friend Copy)

A Flask + SQLite authentication project demonstrating account registration, password hashing, CSRF protection, parameterized SQL queries, session-based authentication, a protected dashboard, and logout.

## Requirements
- Python 3.10 or newer
- VS Code (recommended)

## Run locally

### Windows PowerShell

```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
pip install -r requirements.txt
python app.py
```

Open http://127.0.0.1:5000 in your browser.

Register an account, sign in, visit the protected dashboard, and log out.

## Security notes
- Passwords are stored using Werkzeug's password hashing utilities, not as plain text.
- Database operations use SQLite parameter placeholders.
- Flask-WTF CSRF protection is enabled for form submissions.
- Session cookies are HTTP-only and use SameSite=Lax.
- `SECRET_KEY` must be set to a long random value outside local development.
- For HTTPS deployment set `COOKIE_SECURE=1`.
- The built-in Flask development server is for local testing only. Use a production WSGI server for deployment.
- This starter does not include 2FA, email verification, password reset, rate limiting, or account lockout. Add and test these before treating it as a production authentication service.
- Do not commit `.env`, `users.db`, or real secrets.

## Set a secret key (PowerShell)

```powershell
$env:SECRET_KEY = "paste-a-long-random-secret-here"
python app.py
```
