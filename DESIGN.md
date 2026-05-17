# Design System Specification: The Kinetic Catalyst

## 1. Overview & Creative North Star
This design system is built upon the "Kinetic Catalyst" philosophy. It rejects the static nature of traditional white-label dashboards in favor of an interface that feels alive, efficient, and high-velocity. We are moving beyond "clean" into the realm of "clinical precision with a soul."

The Creative North Star is **Active Minimalism**. While the foundation is rooted in a pristine white-label aesthetic, the soul of the experience lies in the vibrant Emerald and Electric Blue accents that act as visual energy conductors. We break the "template" look through intentional asymmetry—placing oversized typography against tight, functional data and allowing elements to overlap, creating a sense of forward momentum.

## 2. Colors
Our palette is a high-contrast interplay between surgical surfaces and electric accents. The goal is to use color as a functional tool for orientation, not just decoration.

*   **Primary & Energy Tokens:** Use `primary` (#006947) for core actions. Use the `primary_container` (#69f6b8) for large decorative surfaces or high-visibility background states.
*   **Tertiary Accents:** The Electric Blue vibe is captured in the `tertiary` (#006575) and `tertiary_container` (#00dcfd) tokens. Use these for secondary data streams or "smart" features to differentiate them from core emerald tasks.
*   **The "No-Line" Rule:** We do not use 1px solid borders to define sections. Layout boundaries must be defined through background shifts. A `surface_container_low` area sitting on a `surface` background is the standard for sectioning. 
*   **Surface Hierarchy & Nesting:** Treat the UI as a physical stack.
    *   **Base:** `surface` (#f5f6f7).
    *   **Sectioning:** `surface_container_low` (#eff1f2).
    *   **Interactive Cards:** `surface_container_lowest` (#ffffff).
*   **The Glass & Gradient Rule:** For floating navigation or modal overlays, use `surface_container_lowest` at 80% opacity with a `24px` backdrop blur. For Hero CTAs, apply a subtle linear gradient from `primary` to `primary_dim` to add "soul" and depth that prevents the Emerald from looking flat.

## 3. Typography
We utilize **Work Sans** across the entire system. Its optimized legibility and friendly geometry provide a professional yet approachable tone.

*   **The Editorial Scale:** We use extreme scale variance to create hierarchy. 
    *   **Display-LG (3.5rem):** Use for "Hero Moments" or key data points. Set with a tight letter-spacing (-0.02em).
    *   **Headline-SM (1.5rem):** For standard section headers.
    *   **Body-MD (0.875rem):** The workhorse for all data and descriptions.
*   **Visual Identity through Type:** Headlines should never be lonely. Always pair a `headline-md` with a `label-md` "kicker" above it in `primary` color and all-caps to reinforce the high-efficiency, organized feel.

## 4. Elevation & Depth
In this system, depth is a product of light and layering, not heavy shadows.

*   **The Layering Principle:** Avoid traditional shadows. Instead, stack `surface_container_lowest` cards on `surface_container_low` backgrounds. The subtle delta in hex values creates a sophisticated, "paper-on-paper" lift.
*   **Ambient Shadows:** If an element must float (e.g., a dropdown or a floating action button), use an extra-diffused shadow: `box-shadow: 0 12px 40px rgba(0, 105, 71, 0.08)`. Note the use of the `primary` color tint in the shadow to make it feel integrated with the brand.
*   **The "Ghost Border" Fallback:** Where accessibility requires a container edge, use a "Ghost Border": `outline_variant` (#abadae) at 15% opacity. High-contrast, 100% opaque borders are strictly forbidden.
*   **Glassmorphism:** Use for persistent elements like sidebars. `surface_container_low` with a 60% alpha and high blur allows the vibrant accents of the content to peak through, keeping the user grounded in the "vibrant" environment.

## 5. Components

### Buttons
*   **Primary:** Background: `primary`. Text: `on_primary`. Corner Radius: `ROUND_EIGHT` (0.5rem). 
*   **Secondary:** Background: `primary_container`. Text: `on_primary_container`. No border.
*   **Tertiary:** Text: `primary`. No background. Use for low-emphasis actions.

### Cards & Lists
*   **Containers:** Use `surface_container_lowest`. Forbid the use of divider lines.
*   **Separation:** Content must be separated by vertical whitespace (refer to the `1.5rem` spacing scale) or subtle tonal shifts between list items using `surface_container_low` on hover.
*   **Interactive State:** On hover, a card should not move; it should shift its background color slightly toward `surface_bright`.

### Input Fields
*   **Structure:** Minimalist. No heavy borders. Use `surface_container_high` as the background.
*   **Focus State:** A 2px solid `primary` bottom-border only, or a subtle `primary` glow using the Ambient Shadow rule.

### Chips
*   **Action Chips:** Use `secondary_container` with `on_secondary_container` text. These should feel like "pills" of information—highly efficient and compact.

### Dynamic Progress Indicators (Signature Component)
*   To emphasize "High-Efficiency," use a dual-tone progress bar using a gradient from `tertiary` (Electric Blue) to `primary` (Emerald). This visualizes the "catalyst" effect of the system.

## 6. Do's and Don'ts

### Do
*   **Use Asymmetry:** Place a large `display-md` value off-center to create a modern, editorial layout.
*   **Leverage White Space:** Allow at least `48px` (xl) of breathing room between major sections to maintain the premium feel.
*   **Color as Data:** Use `tertiary` (#006575) exclusively for "Insights" or "AI" features to create a mental shortcut for the user.

### Don't
*   **No Dividers:** Never use a line where a gap or a color shift could work.
*   **No Sharp Corners:** All interactive elements must adhere to `ROUND_EIGHT` (0.5rem) to maintain the "friendly but professional" balance.
*   **No Pure Black:** Never use #000000. Use `on_surface` (#2c2f30) for all primary text to keep the contrast high-end rather than harsh.
*   **No Over-Saturation:** Do not fill large screens with `primary` Emerald. It is a "vibrant accent." Use it for CTAs, highlights, and icons—let the `surface` tokens do the heavy lifting for the layout.