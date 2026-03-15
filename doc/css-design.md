## Tom's Asphalt Service - CSS Design System
This document outlines the visual language and CSS architecture for the Tom's Asphalt Service (TAS) website. The design is intended to project durability, professionalism, and a long-standing family legacy.
1. Color Palette
The color strategy is based on "High-Contrast Utility." It draws direct inspiration from road construction, asphalt, and safety equipment.

| Element | Hex Code | Purpose |
|---|---|---|
| Primary Yellow | #ffcc00 | Branding, Action Buttons, Icons, and Accents. Matched to the TAS logo stripe. |
| Asphalt Dark | #1a1a1a | Main Backgrounds, Navigation, and Footer. Represents fresh asphalt. |
| Asphalt Gray | #333333 | Borders and Input Backgrounds. |
| Pure White | #ffffff | Header background to provide maximum contrast for the logo. |
| Text Light | #ffffff | Typography on dark backgrounds. |
| Text Dark | #222222 | Main body copy on light backgrounds. |
2. Typography
The system utilizes a "Humanist Sans-Serif" stack for readability and a modern, clean feel.
 * Font Family: 'Segoe UI', Roboto, Helvetica, Arial, sans-serif.
 * Fluid Sizing: We use the clamp() function to ensure headers scale smoothly between mobile and desktop without manual media query overrides for every font size.
   * h1: clamp(2.2rem, 6vw, 3.8rem)
   * h2: clamp(1.6rem, 4vw, 2.6rem)
3. UI Components & Depth
Branding & Logo
The logos are treated with a heavy drop shadow (0 10px 25px rgba(0,0,0,0.18)) to create a 3D effect. This ensures the logo remains readable even on light backgrounds where the yellow/white edges might otherwise blend in.
Buttons
Buttons use a "Tactile Heavy" style:
 * Background: var(--primary-yellow)
 * Interactions: A subtle translateY(-3px) and increased shadow on hover to simulate the button lifting toward the user.
 * Text: Uppercase with letter-spacing: 1px for a bold, industrial look.
Cards
Services are displayed in cards with a 5px bottom border of Asphalt Dark. This "heavy bottom" anchoring provides a sense of structural stability.
4. Layout Architecture
Sticky Navigation
The site uses position: sticky for the header. To prevent the common "jump-to-content" bug where the header covers the section title, we implemented:
 * CSS Variable: --header-height: 115px.
 * Scroll Margin: scroll-margin-top: var(--header-height) on all section tags.
Responsive Strategy
The layout is built using Flexbox and CSS Grid.
 * The 850px Breakpoint: This is the primary shift where the desktop "Top Bar" disappears, and the navigation transforms into a mobile-friendly toggle menu.
 * Self-Centering Flex: The "50+ Years" badge in the About section uses flex-wrap: wrap combined with margin: 0 auto and justify-content: center to ensure that when it drops to a new line on smaller screens, it remains perfectly centered.
5. CSS Variables (The "Source of Truth")
The entire theme can be updated by modifying the :root variables:

```
:root {
    --primary-yellow: #ffcc00;
    --asphalt-dark: #1a1a1a;
    --header-height: 115px;
    --radius: 4px;
    --transition: all 0.3s ease;
}
```

