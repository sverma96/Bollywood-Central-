# 🎬 Bollywood Central

> A responsive, client-side entertainment web application delivering real-time Bollywood news, upcoming film releases, celebrity profiles, and audience engagement — built entirely with vanilla web technologies.

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Responsive](https://img.shields.io/badge/Responsive-Design-green?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)

---

## 📖 Overview

**Bollywood Central** is a fully client-side, zero-dependency web application designed as a centralized hub for Bollywood entertainment content. It implements a Single Page Application (SPA) navigation pattern using vanilla JavaScript — eliminating full page reloads while maintaining clean section-based URL routing.

The project demonstrates proficiency in semantic HTML5 markup, advanced CSS3 layout systems (Flexbox + CSS Grid), dynamic DOM manipulation, and mobile-first responsive design principles.

---

## ✨ Features

| Feature | Description |
|---|---|
| SPA Navigation | Seamless section switching via DOM manipulation without page reloads |
| News Feed | Curated grid of latest Bollywood news cards with hover animations |
| Upcoming Movies | Movie showcase with poster images, release dates, and synopses |
| Starcast Profiles | Celebrity cards with circular avatar images and biographical info |
| Lead Roles | Detailed cast breakdowns for major 2025 productions |
| Contact Form | Client-side validated contact form with categorized subject options |
| Responsive Layout | Fully adaptive UI across mobile, tablet, and desktop viewports |
| CSS Animations | Bounce, pulse, shimmer, and fade-in keyframe animations |
| Glassmorphism Navbar | Fixed header with `backdrop-filter: blur()` and scroll persistence |

---

## 📁 Project Structure

```
bollywood-central/
│
├── index.html          # Application shell — all sections, nav, and form markup
├── style.css           # Global styles, component styles, animations, breakpoints
├── script.js           # SPA navigation controller, form validation handler
│
└── images/             # Local movie poster assets
    ├── war2.jpg
    ├── baaghi4.jpg
    ├── lahore-1947.jpg
    ├── mahavatar-narsimha.jpg
    ├── sitaare-zameen-par.jpg
    └── ...
```

---

## ⚙️ Getting Started

### Prerequisites

No runtime dependencies or package managers required. Any modern browser suffices.

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/your-username/bollywood-central.git

# 2. Navigate into the project directory
cd bollywood-central

# 3. Open in browser
# Option A — Direct file open
open index.html

# Option B — Serve via local dev server (recommended for image loading)
npx serve .
# or
python -m http.server 8000
```

Then visit `http://localhost:8000` in your browser.

---

## 📱 Responsive Breakpoints

The layout is engineered across four adaptive tiers:

| Breakpoint | Viewport Width | Layout Behavior |
|---|---|---|
| Mobile S | `< 480px` | Single-column, stacked nav, reduced typography |
| Mobile L / Tablet | `< 768px` | Two-column star grid, vertical nav, compressed cards |
| Default | `768px – 1199px` | Auto-fit CSS Grid with `minmax()` columns |
| Desktop | `≥ 1200px` | Fixed-column grids: 2-col news, 3-col movies, 3-col stars |
| Large Desktop | `≥ 1400px` | Expanded container width up to 1300px |

---

## 🧱 UI Architecture

### SPA Navigation Pattern

```javascript
// Section visibility is controlled entirely via CSS class toggling
function showSection(sectionId) {
    document.querySelectorAll('.section').forEach(s => s.classList.remove('active'));
    document.getElementById(sectionId).classList.add('active');
}
```

Active sections use `display: flex` with a `fadeIn` keyframe animation for smooth transitions.

### Component Hierarchy

```
App
├── Header (fixed, z-index: 1000)
│   └── Nav (logo + nav-menu)
└── Main
    ├── #home        → NewsCard[]
    ├── #upcoming    → MovieCard[]
    ├── #starcast    → StarCard[]
    ├── #leadroles   → NewsCard[] (cast detail variant)
    ├── #about       → AboutContent
    └── #contact     → ContactForm + ContactInfo
```

