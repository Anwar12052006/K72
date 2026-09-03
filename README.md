# ⚡ K72 Agency — Creative Portfolio & Web Experience

<div align="center">

[![React](https://img.shields.io/badge/React-18.2.0-61DAFB?style=for-the-badge&logo=react&logoColor=black)](https://reactjs.org/)
[![Vite](https://img.shields.io/badge/Vite-5.2.0-646CFF?style=for-the-badge&logo=vite&logoColor=white)](https://vitejs.dev/)
[![GSAP](https://img.shields.io/badge/GSAP-3.13.0-88CE02?style=for-the-badge&logo=greensock&logoColor=white)](https://greensock.com/gsap/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-v4.1-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)](https://tailwindcss.com/)
[![React Router](https://img.shields.io/badge/React_Router-v7.8-CA4245?style=for-the-badge&logo=react-router&logoColor=white)](https://reactrouter.com/)

<p align="center">
  <strong>An Awwwards-inspired, high-performance creative agency portfolio clone built with React, GSAP ScrollTrigger, Tailwind CSS v4, and Vite.</strong>
</p>

[Key Features](#-key-features) • [Why This Project?](#-why-this-project) • [Tech Stack](#-tech-stack) • [Project Structure](#-project-structure) • [Getting Started](#-getting-started) • [Animations & GSAP](#-animations--interactive-highlights)

</div>

---

## 🎯 Overview & Purpose

### Why was this project built?
This project is an interactive, high-fidelity recreation of the award-winning digital experience of **[K72](https://k72.ca)** (Soixante-Douze), a multidisciplinary creative branding and communications agency based in Montreal, Canada.

The primary objectives of building this project:
1. **Awwwards-Level Creative Frontend Engineering**: Master modern web animation patterns, micro-interactions, dynamic cursor behaviors, and cinematic visual transitions.
2. **Advanced GSAP & ScrollTrigger Mastery**: Implement scroll-driven image sequence scrubbers, pinning animations, timeline sequencing, and 3D link rotation transforms.
3. **Seamless Page Transitions**: Engineer custom multi-column stair transition overlays that trigger synchronously across React Router page transitions.
4. **Modern Design System**: Replicate an agency-grade visual language using minimalist black/white palettes, electric lime (`#D3FD50`) accent highlights, fluid typography, and custom editorial fonts (*TWK Lausanne*).

---

## ✨ Key Features

- **🎥 Immersive Hero Showcase (`/`)**:
  - Full-screen looping background video with ambient editorial styling.
  - Interactive typographic hero headline featuring an embedded inline video pill capsule (*"L'étincelle qui [video] génère la créativité"*).
  - Responsive pill-shaped CTAs with neon highlight hover animations.

- **📜 Scroll-Driven Team Scrubber (`/agence`)**:
  - Pinned dynamic viewport element powered by GSAP ScrollTrigger.
  - Progressive image swapping through team member portraits synchronized to scroll depth.
  - Fluid large-scale typographic typography (*"SOIXAN7E DOUZE"*).

- **🗂️ Interactive Projects Gallery (`/projects`)**:
  - Dynamic scroll-staggered case study grid.
  - Smooth hover morphing effects (morphing from sharp corners to rounded cards with glassmorphism overlays and *"Voir le projet"* CTA).

- **🪜 Signature Staggered Stair Transitions**:
  - 5-column vertical curtain slide animation executed globally on every route change via `Stairs.jsx`.
  - Content scale and opacity staging on navigation completion.

- **🎛️ Fullscreen Accordion Navigation Menu**:
  - 3D perspective flip (`rotateX`) on menu links upon menu opening.
  - Infinite horizontal marquee ticker (*"Pour Tout voir"*) with project previews on link hover.
  - Kinetic hamburger icon with liquid fill transition.

- **🎨 Dynamic Adaptive Theme Context**:
  - React Context API (`NavContext`) dynamically tracks current routes and inverts navigation color schemes (white theme on dark hero, black theme on light pages).

---

## 🛠️ Tech Stack

| Category | Technology | Description |
| :--- | :--- | :--- |
| **Framework** | [React 18](https://react.dev/) | Component architecture, Hooks (`useRef`, `useContext`, `useEffect`), Context API |
| **Build Tool** | [Vite 5](https://vitejs.dev/) | Ultra-fast HMR (Hot Module Replacement) and optimized production bundle |
| **Animation** | [GSAP 3](https://greensock.com/gsap/) | GreenSock timeline sequencing, easing, and transform management |
| **Animation Plugin** | [ScrollTrigger](https://greensock.com/scrolltrigger/) | Scroll-linked pinning, image scrubbers, and stagger triggers |
| **GSAP React Integration** | [`@gsap/react`](https://www.npmjs.com/package/@gsap/react) | Safe animation lifecycle management with `useGSAP` hook |
| **Styling** | [Tailwind CSS v4](https://tailwindcss.com/) | Next-generation utility-first styling with `@tailwindcss/vite` |
| **Routing** | [React Router v7](https://reactrouter.com/) | Client-side routing with location-based transitions |
| **Typography** | Lausanne Font Family | Editorial grotesque typeface (*Lausanne-300* & *Lausanne-500*) |
| **Linting** | ESLint 8 | Code quality and React hooks rules enforcement |

---

## 📁 Project Structure

```plaintext
k72/
├── public/
│   ├── fonts/               # Custom TWK Lausanne WOFF2 font files
│   │   ├── Lausanne-300.woff2
│   │   └── Lausanne-500.woff2
│   ├── video.mp4            # Ambient video asset for hero & inline capsules
│   └── vite.svg             # Default Vite favicon
├── src/
│   ├── assets/              # Static assets and icons
│   ├── components/
│   │   ├── common/
│   │   │   └── Stairs.jsx          # Global 5-bar stair route transition wrapper
│   │   ├── home/
│   │   │   ├── HomeBottomText.jsx  # Hero footer CTA pills & agency description
│   │   │   ├── HomeHeroText.jsx    # Hero headline with embedded video pill
│   │   │   └── Video.jsx           # Reusable HTML5 autoplay video player
│   │   ├── Navigation/
│   │   │   ├── FullScreenNav.jsx   # Fullscreen overlay, 3D menu links & marquee
│   │   │   └── Navbar.jsx          # Persistent top nav, adaptive logo & animated burger
│   │   └── projects/
│   │       └── ProjectCard.jsx     # Dual-column case study card with hover morph
│   ├── context/
│   │   └── NavContext.jsx   # Context providers for navOpen & navColor state
│   ├── pages/
│   │   ├── Agence.jsx       # Agency story & scroll-scrubbed team gallery
│   │   ├── Home.jsx         # Landing page experience
│   │   └── Projects.jsx     # Project showcase with height-stagger animations
│   ├── App.jsx              # Route definitions & layout shell
│   ├── index.css            # Tailwind v4 import, font faces & keyframe animations
│   └── main.jsx             # React entry point with BrowserRouter & Providers
├── .eslintrc.cjs            # ESLint configuration
├── index.html               # HTML entry template
├── package.json             # Scripts & dependencies
└── vite.config.js           # Vite configuration with React & Tailwind plugins
```

---

## 🚀 Getting Started

### Prerequisites
Make sure you have [Node.js](https://nodejs.org/) (version 18+ recommended) and `npm` installed.

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/k72-clone.git
cd k72
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Start Development Server
```bash
npm run dev
```
Open [http://localhost:5173](http://localhost:5173) in your browser to view the application.

### 4. Build for Production
```bash
npm run build
```
The optimized production bundle will be generated in the `dist/` directory.

### 5. Preview Production Build
```bash
npm run preview
```

### 6. Code Linting
```bash
npm run lint
```

---

## 💫 Animations & Interactive Highlights

### 1. GSAP ScrollTrigger Team Scrubber (`Agence.jsx`)
Pins the image container in viewport and dynamically indexes through team images based on scroll progress:
```javascript
gsap.to(imageDivRef.current, {
  scrollTrigger: {
    trigger: imageDivRef.current,
    start: 'top 28%',
    end: 'top -70%',
    pin: true,
    scrub: 1,
    onUpdate: (elem) => {
      const imageIndex = elem.progress < 1 
        ? Math.floor(elem.progress * imageArray.length) 
        : imageArray.length - 1;
      imageRef.current.src = imageArray[imageIndex];
    }
  }
});
```

### 2. Infinite Marquee Hover Reveal (`FullScreenNav.jsx`)
Hovering any menu link reveals a lime banner with an infinite CSS keyframe ticker:
```css
@keyframes moveAnimation {
  from { transform: translateX(0); }
  to { transform: translateX(-100%); }
}
```

### 3. 5-Bar Curtain Page Transitions (`Stairs.jsx`)
Synchronized page transitions using GSAP timelines staggered horizontally across 5 vertical columns whenever `useLocation().pathname` changes.

---

## 🌐 Routes & Navigation

| Route | Page | Key Experience |
| :--- | :--- | :--- |
| `/` | **Home** | Background video, dynamic typography cutout, and navigation pills |
| `/agence` | **Agence** | Scroll-pinned team scrubber, agency manifesto, and brand story |
| `/projects` | **Projects** | Expanding project grid cards with border-radius morphing hover effects |

---

## 🎨 Color Palette & Typography

- **Background Dark**: `#000000` / `#0a0a0a`
- **Background Light**: `#FFFFFF` / `#f4f4f4`
- **Neon Accent**: `#D3FD50` (Electric Lime)
- **Primary Typography**: `Lausanne-300` (Light Swiss Grotesque)
- **Secondary Typography**: `Lausanne-500` (Medium Editorial)

---

## 📄 License & Credits

- **Original Design Inspiration**: [K72 Agency Montreal](https://k72.ca)
- **Disclaimer**: This project was built for educational and portfolio demonstration purposes to showcase modern creative web development and animation techniques.

---

<div align="center">
  Made with ⚡ by an engineering & design enthusiast.
</div>
