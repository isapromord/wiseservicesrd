# BRAIN - Wise Services RD Landing Page Architecture & Rules

## Project Identity
- **Project:** Wise Services RD (`wiseservicesrd`)
- **Repo:** `https://github.com/isapromord/wiseservicesrd`
- **Live URL:** `https://isapromord.github.io/wiseservicesrd/`
- **Domain:** `wiseservicesrd.com` (Target production domain on Hostinger)

## Core Architectural Rules
1. **Design System & Aesthetics:**
   - Visual Style: Ultra-high-end Corporate & Luxury Glassmorphism (`backdrop-blur-md`, subtle translucent borders `border-white/10`).
   - Color Palette: Deep Navy (`#001229`), Primary Accents (`#e05305`), Surface tones.
   - Typography & Icons: Google Fonts (Epilogue / Plus Jakarta Sans) + Material Symbols Outlined (with ligature support enabled via CSS: `-webkit-font-feature-settings: 'liga'; font-feature-settings: 'liga';`).
2. **Hero Section Architecture:**
   - Full-bleed background video (`assets/videos/hero-drone-video.mp4`) with 720p fallback.
   - Dual-layer gradient overlays (`from-[#001229]/90 via-[#001229]/65 to-transparent`) to ensure left-aligned text legibility without obscuring right-side visual action (pool/tower).
   - Stacking Context: Video container must sit at `z-0` (never negative z-index) with overlays at `z-[1] pointer-events-none` and content at `z-10`.
3. **Decoupled Backend & Lead Capture:**
   - Forms and WhatsApp triggers configured for lead routing without monolithic backend dependencies.
