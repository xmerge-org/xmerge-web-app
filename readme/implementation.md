# Xmerge Dev Implementation Details

This document covers the specific code blocks and layout strategies implemented within the core repository.

## 1. Directory Structure
```
web-app/
├── venv/
├── manage.py
├── static/
│   ├── css/styles.css        # Core custom styles, variables, typography
│   └── js/main.js            # Keyframe handlers and Intersection Observer scripts
├── landing/
│   ├── apps.py
│   ├── views.py              # Contains 'home' view executing the render pipeline
│   ├── urls.py               # Local app URL configuration
│   └── templates/
│       └── landing/
│           └── index.html    # Core semantic HTML layout
└── xmerge_dev/
    ├── settings.py           # Global settings, static configurations, allowed hosts
    ├── urls.py               # Application-wide routing orchestrator
    └── wsgi.py / asgi.py     # Deployment entrypoints
```

## 2. Django Core Configurations

### settings.py Adjustments
- **Static files:** `STATICFILES_DIRS` was extended using `BASE_DIR / 'static'` to ensure robust parsing of CSS/JS.
- **Installed Apps:** `landing` was injected directly into standard Django components to access the templating engine.

### Route Delegation
In `xmerge_dev/urls.py`, the root (`/`) path delegates entirely to the `landing/urls.py` module via the `include()` method.

## 3. Web Architecture

### Dynamic Styling (`styles.css`)
- Replaces frameworks with pure Vanilla CSS, reducing overall payload requirements.
- Uses `backdrop-filter` in conjunction with `var(--glass-bg)` attributes heavily across Feature Cards (`.feature-card`) and Panels (`.glass-panel`) for the modern 'glassmorphic' rendering style.
- CSS Keyframes handle organic background animations via the `.blob .float` properties to limit JS event loops.

### Semantic Layout (`index.html`)
Modular structured using strictly HTML5 conventions:
- `<nav>`: Sticky positioning intercepting standard scroll triggers.
- `<main>`: Contains three defined `<section>` domains: `Hero`, `#features`, and `CTA`.

### Event Mapping (`main.js`)
Uses `IntersectionObserver` internally to trigger `.visible` hooks on DOM nodes dynamically mapped with `.fade-up` classes. A secondary `mousemove` listener on the Hero visualization provides the simulated 3D geometry transform (`rotateX/rotateY`).
