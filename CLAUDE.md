# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is the Pickles Zero Touch Transport (ZT2) platform demo - a comprehensive static HTML prototype for an AI-driven logistics solution that integrates Pickles Auctions with Loadshift's crowdsourced transport network. The demo features a multi-page orchestrated experience with both mobile and desktop layouts.

## Commands

**This is a static HTML project with no build system.** To view the project:
- Open `index.html` directly in a web browser (main entry point)
- Use a local web server for development (e.g., `python -m http.server` or VS Code Live Server extension)
- Individual demo pages can be accessed at `pickles-zt2-demo/pages/*.html`

No build, lint, or test commands are available.

## Code Architecture

### Technology Stack
- **Frontend**: Vanilla HTML5, CSS3, JavaScript (ES6+)
- **Styling**: Tailwind CSS (loaded via CDN)
- **Icons**: Lucide icons (loaded via CDN)
- **Layout**: Responsive design with mobile-first approach (430px max-width) and desktop layouts

### Key Files Structure
```
├── index.html - Main demo orchestration controller
└── pickles-zt2-demo/
    ├── pages/
    │   ├── client_quote.html - AI quote generation (mobile)
    │   ├── phonecall_confirm.html - AI agent confirmation (mobile)
    │   ├── order_confirmation.html - Automated processing (mobile)
    │   ├── pickup_auth.html - Digital authorization (mobile)
    │   ├── god_mode.html - Operations dashboard (desktop)
    │   └── delivery_complete.html - Completion tracking (mobile)
    └── assets/
        ├── icons/
        └── images/
```

### Demo Orchestration Architecture

The `index.html` serves as the main controller using the `ZT2DemoController` class that manages:

**6-Step Demo Flow:**
1. AI-Powered Quote Generation (mobile)
2. AI Agent Confirmation (mobile) 
3. Automated Order Processing (mobile)
4. Digital Pickup Authorization (mobile)
5. Operations Command Center - "God Mode" (desktop)
6. Delivery Completion (mobile)

**Key Controller Methods:**
- `ZT2DemoController.navigateToStep(stepIndex)` - Core navigation
- `loadDemoPage()` - Handles mobile/desktop layout switching
- `updateUI()` - Synchronizes progress bar and info panel

### Layout System

**Mobile Layout (Steps 1-4, 6):**
- iPhone shell design with dynamic island and physical buttons
- 430px maximum width container
- Embedded iframe with mobile-optimized content

**Desktop Layout (Step 5 - God Mode):**
- Full-width responsive layout (95vw)
- Side-by-side iframe and information panel
- Special layout classes: `desktop-layout`, `desktop-mode`, `desktop-layout-container`

**Critical Layout Switching Logic:**
When switching from desktop back to mobile, the system must clear all inline styles set during desktop mode to prevent layout persistence issues.

### Individual Demo Pages

Each page in `pickles-zt2-demo/pages/` is a self-contained HTML file with:
- Multi-state user interface (typically 4 states per page)
- State management via `switchToState(state)` functions
- AI simulation timing and animations
- Inline styles and JavaScript for portability

### Styling Conventions
- Tailwind CSS utility classes throughout
- Custom CSS animations (ai-pulse, progress bars, fade transitions)
- Gradient backgrounds: `linear-gradient(135deg, #667eea 0%, #764ba2 100%)`
- iPhone shell styling with realistic hardware elements
- Mobile-first responsive breakpoints

### Code Style
- 4-space indentation for HTML, CSS, and JavaScript
- `camelCase` for JavaScript functions and properties
- `kebab-case` for HTML element IDs
- English/Chinese bilingual content and comments
- All styles and scripts inline for self-contained demos

## Development Notes

- Demo orchestration uses iframe embedding for seamless page transitions
- Layout switching between mobile and desktop requires careful style management
- Each demo page simulates realistic AI processing timing (8-15 seconds)
- Icons require `lucide.createIcons()` initialization after DOM changes
- The system is designed for demonstration purposes with simulated backend responses