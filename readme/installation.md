# Installation & Setup

Follow these steps to set up the Xmerge Dev development environment locally.

## Prerequisites
- macOS/Linux/Windows operating system.
- Python 3.8+ installed on your system.

## 1. Environment Setup

Locate your root web application directory and initialize a virtual environment:

```bash
cd /path/to/Xmerge/web-app
python3 -m venv venv
```

Activate the virtual environment:
- On macOS/Linux: `source venv/bin/activate`
- On Windows: `.\venv\Scripts\activate`

## 2. Dependencies

Install Django and any other dependencies inside your activated virtual environment:

```bash
pip install django
```

*(Optional: Freeze requirements for portability)*
```bash
pip freeze > requirements.txt
```

## 3. Database Initialization

Django requires an initial migration to set up the built-in SQLite database correctly for its core features (admin, auth, etc.):

```bash
python manage.py migrate
```

## 4. Running the Application

To launch your development server and view the Xmerge Dev platform locally:

```bash
python manage.py runserver 8080
```

Open a web browser and navigate to exactly:
[http://127.0.0.1:8080](http://127.0.0.1:8080)
