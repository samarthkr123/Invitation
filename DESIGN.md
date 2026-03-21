# Design System: Celestial Invitation & Event Experience

## 1. Overview & Creative North Star
**The Creative North Star: "The Ethereal Observer"**

This design system moves away from the rigid, boxed-in layouts of traditional event platforms. Instead, it treats the screen as a limitless midnight canopy. The goal is to evoke the feeling of looking through a high-end telescope: focused, layered, and profoundly deep. 

We break the "template" look by using **intentional asymmetry**—large, high-contrast Display typography offset by generous negative space—and **overlapping glass planes**. Elements should never feel like they are sitting "on" a background; they should feel like they are floating "within" an atmosphere. We achieve this through the careful application of backdrop blurs and light-based depth rather than structural lines.

## 2. Colors & Atmospheric Depth
The palette is rooted in the transition from deep cosmic indigo to the absolute void of space, punctuated by the "ion glow" of distant nebulae.

*   **Primary (#c9bfff):** Our "Starlight" violet. Used for high-impact accents and primary actions.
*   **Secondary (#a6e6ff):** Our "Cyan Nebula." Used for interactive elements and subtle highlights.
*   **Surface Tiers:** We use the `surface-container` scale to simulate density.
    *   `surface-container-lowest (#0c0e12)` is the "Deep Space" foundation.
    *   `surface-container-highest (#323539)` is our "Frosted Lens" layer.

### The "No-Line" Rule
**Explicit Instruction:** Designers are prohibited from using 1px solid borders for sectioning or containment. Boundaries must be defined solely through background color shifts or the "Glow Border" technique. If you feel a section needs a line, you actually need a change in `surface-container` depth or a `3.5 (1.2rem)` increase in vertical spacing.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. A "Card" is not a box; it is a pocket of mist. 
*   **Base:** `background` (#111417).
*   **Section:** `surface-container-low` (#191c1f).
*   **Component:** `surface-container-high` (#282a2e) with a 20px backdrop blur.

### The Glass & Gradient Rule
To provide "visual soul," all primary CTAs must use a linear gradient from `primary` (#c9bfff) to `on_primary_container` (#7f66ff) at a 135-degree angle. This mimics the refraction of light through a prism.

## 3. Typography
The typographic pairing creates a tension between the futuristic precision of the cosmos and the human warmth of the event.

*   **Display & Headlines (Space Grotesk):** This is our "Futuristic Elegant" voice. Use `display-lg` for HJB Hall Day titles. These should be set with tight letter-spacing (-0.02em) to feel like a high-end editorial masthead.
*   **Body & Titles (Manrope):** This is our "Minimalist Clarity" voice. Manrope provides a clean, technical counter-balance to the expressive headings.
*   **Hierarchy Note:** Use `label-md` in all-caps with `0.1rem` letter-spacing for date/time metadata to create a "technical readout" aesthetic that feels high-end and intentional.

## 4. Elevation & Depth
In this system, light is the architect. We do not use "shadows" in the traditional sense; we use "glows."

*   **The Layering Principle:** Stacking is mandatory. Place a `surface-container-highest` element over a `surface-container-low` background. The contrast in luminance provides all the separation needed.
*   **Ambient Shadows:** If an element must float (like a modal), use a shadow tinted with `primary` at 8% opacity. Blur radius must be at least `40px` to ensure the light feels ambient, not localized.
*   **The "Ghost Border" Fallback:** For buttons or cards that require definition against complex backgrounds, use `outline-variant` (#46464c) at **15% opacity**. This creates a "specular highlight" on the edge of the glass rather than a physical containment line.
*   **Glassmorphism:** All floating containers must utilize `backdrop-filter: blur(12px)`. This allows the "galaxy" background effects to bleed through, softening the layout.

## 5. Components

### Buttons
*   **Primary:** Gradient fill (`primary` to `on_primary_container`). Roundedness: `full`. No border. Text color: `on_primary`.
*   **Secondary:** Glass-filled (`surface-container-highest` at 40% opacity). Ghost border (15% opacity).
*   **Tertiary:** Text-only using `primary` color. High-end editorial feel.

### Cards & Event Modules
*   **Rule:** Forbid the use of divider lines.
*   **Execution:** Use `spacing-6` (2rem) to separate content blocks. Use a `surface-container-low` background for the "Content" area and `surface-container-high` for the "Action" area (like an RSVP button footer) to create a natural visual break.

### Inputs & Fields
*   **Style:** Minimalist under-lines or subtle glass troughs.
*   **States:** On focus, the bottom border should transition from `outline-variant` to a `primary` glow with a soft 4px outer blur.

### Additional Signature Components
*   **The "Nebula" Chip:** Use `secondary_container` with a high blur and 20% opacity as a background for tags (e.g., "VIP," "Dress Code"). It should look like a localized gas cloud.
*   **The Countdown Clock:** Set in `display-md`, utilizing `primary` color with a subtle `text-shadow` glow to make the numbers feel like they are projected into the room.

## 6. Do's and Don'ts

### Do
*   **DO** use asymmetrical margins. If the left margin is `spacing-8`, consider a `spacing-12` right margin for a custom, editorial feel.
*   **DO** overlap elements. Let a glass card partially cover a background star-field graphic.
*   **DO** use `surface_bright` sparingly for "active" or "hovered" states to simulate a light being turned on behind the glass.

### Don't
*   **DON'T** use pure white (#FFFFFF). Always use `on_surface` (#e1e2e7) to keep the "calm, dreamy" vibe intact. Pure white is too harsh for this night-sky aesthetic.
*   **DON'T** use 90-degree corners. Always adhere to the Roundedness Scale, favoring `lg` (1rem) for cards and `full` for interactive triggers.
*   **DON'T** crowd the interface. If the content feels tight, increase the spacing by two steps on the scale. High-end design requires room to breathe.

### Accessibility Note
While we prioritize "Glassmorphism," ensure that text over blurred backgrounds meets a contrast ratio of at least 4.5:1. Use `surface-container-highest` as the backing for any critical body text to ensure legibility against the galaxy gradients.