# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is the Pickles Zero Touch Transport (ZT2) platform demo - a static HTML prototype for an AI-driven logistics solution that integrates Pickles Auctions with Loadshift's crowdsourced transport network. The demo showcases a mobile-first client quote interface with multi-state user flow and AI analysis simulation.

## Commands

**This is a static HTML project with no build system.** To view the project:
- Open `pickles-zt2-demo/pages/client_quote.html` directly in a web browser
- Use a local web server for development (e.g., `python -m http.server` or VS Code Live Server extension)

No build, lint, or test commands are available.

## Code Architecture

### Technology Stack
- **Frontend**: Vanilla HTML5, CSS3, JavaScript (ES6+)
- **Styling**: Tailwind CSS (loaded via CDN)
- **Icons**: Lucide icons (loaded via CDN)
- **Layout**: Mobile-first responsive design with a maximum width of 430px

### Key Files Structure
```
pickles-zt2-demo/
├── pages/
│   └── client_quote.html - Main demo page with complete UI flow
├── css/ - (empty, styles are inline)
├── js/ - (empty, JavaScript is inline) 
└── assets/
    ├── icons/
    └── images/
```

### Application Flow States
The demo implements a 4-state user journey:
1. **State 1**: Delivery information input form
2. **State 2**: AI analysis simulation with progress bar and animated steps
3. **State 3**: Analysis results with pricing estimates and carrier mapping
4. **State 4**: Completion status with SLA promises

### Key JavaScript Functions
- `switchToState(state)` - Core state management function
- `startAnalysis()` - Orchestrates AI analysis animation with realistic timing
- `setupNextStepButton()` / `setupQuoteButton()` - Event handlers for user flow

### Styling Conventions
- Uses Tailwind CSS utility classes throughout
- Custom CSS animations for AI pulse effects, progress bars, and fade transitions
- Gradient backgrounds and card shadows for visual hierarchy
- Mobile-optimized containers with responsive breakpoints

### Code Style
- 4-space indentation for HTML, CSS, and JavaScript
- `camelCase` for JavaScript functions
- `kebab-case` for HTML element IDs  
- English/Chinese bilingual comments and content
- Inline styles and scripts (not separated into files)

## Development Notes

- The project simulates AI analysis with realistic timing (12+ seconds total)
- Form validation uses basic JavaScript `alert()` for user feedback
- Icons are initialized with `lucide.createIcons()` on page load
- State transitions use CSS classes for smooth animations
- The demo is fully self-contained in a single HTML file