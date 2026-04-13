# Xmerge Dev Planning

## Objective
To build a developer-centric landing page for **Xmerge Dev**. The site aims to help clients create modern and realistic applications while offering tools and packages tailored specifically to developers.

## Design Identity
The visual identity of Xmerge Dev is focused on a premium developer aesthetic:
- **Theme:** Comprehensive dark mode base (`#050505`).
- **Typography:** 'Inter' via Google Fonts for sleek readability matching modern dev tools.
- **Accents:** Indigo (`#6366f1`) and Purple (`#a855f7`) combinations providing energetic, contrasting gradients.
- **Effects:** Heavy use of Glassmorphism (blur filters), glowing background elements, and smooth dynamic transitions to evoke a "state-of-the-art" feel.

## Architecture
- **Backend Framework:** Django (Python), utilizing minimal overhead template rendering for instant Time-To-Interactive.
- **Project Structure:** A central `xmerge_dev` router and an isolated `landing` application scaling horizontally if new services are later introduced.
- **Frontend Stack:** Vanilla HTML/CSS/JS allowing absolute structural control over animations and styles without heavy framework payloads (React, SCSS, etc.).

## Checkpoints
1. Setting up the virtual environment & Django scaffolding.
2. Creating backend routes and the core view for the root index.
3. Assembling the structure and layout (HTML).
4. Injecting design principles and custom variables (CSS).
5. Binding visual interactivity and data-independent animations (JavaScript).
