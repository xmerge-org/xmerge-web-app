# Xmerge Dev Landing Page Implementation

I have successfully initialized the Django project and created the custom landing page for **Xmerge Dev**.

## Changes Made

1. **Environment Setup**
    - Created a Python virtual environment (`venv`) inside the `web-app` directory.
    - Installed Django `4.2.30` and its dependencies.
    - Initialized the Django project `xmerge_dev` and created a new app named `landing`.

2. **Backend Configuration (`xmerge_dev` and `landing`)**
    - Registered the `landing` app in `xmerge_dev/settings.py`.
    - Configured static files to be served from the top-level `static/` directory to keep assets organized.
    - Added the `home` view in `landing/views.py` to route to the custom landing page template.
    - Set up `urls.py` in both the project and the app to correctly map the root URL `/` to the `home` view.

3. **Frontend Design (Vanilla HTML/CSS/JS)**
    - Designed `index.html` with a modern, semantic structure, focusing on a dev-centric theme.
    - Built with **Vanilla CSS** (`styles.css`), implementing:
        - A sleek dark mode using native CSS variables (`--bg-color`, `--text-primary`).
        - A vibrant color palette (indigo/purple text gradients).
        - **Glassmorphism** for feature cards and the hero visual panel `rgba(255, 255, 255, 0.03)` with `backdrop-filter`.
        - Background blur blobs that slowly float via CSS keyframes `float` adding an organic feel.
        - Typography handled by Google Fonts 'Inter'.
    - Developed interactivity via **Vanilla JS** (`main.js`):
        - A 3D dynamic perspective transform mapped to the mouse cursor inside the hero code block visual (`rotateX` / `rotateY`).
        - Scroll intersection observers to gracefully `fade-up` elements as the user browses down the page.
        - Navbar state transformations mapped to window scroll events.

## Validation Results

- The Django server is actively running on `http://127.0.0.1:8080/`. You can open this link in your browser to interact with the new landing page.
- There may be minor differences between browser renders for effects like `backdrop-filter`, but it should work smoothly on modern Webkit and Gecko engines.
- **Note**: The automated browser verification timed out due to service capacity, so please manually check the page design in your browser.
