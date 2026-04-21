# Design System Document: Architectural Fluidity

## 1. Overview & Creative North Star
This design system is built on the tension between industrial permanence and the beauty of motion. We move beyond the rigid, "boxy" constraints of traditional construction software to embrace **Architectural Fluidity**. 

The goal is to evoke the feeling of a high-end architectural firm—where blueprints (structure) meet the organic flow of environmental design. We achieve this through "Dynamic Construction": using heavy, bold typographic weights juxtaposed against fluid, glass-like surfaces and asymmetrical layouts. This isn't just an interface; it’s a digital structure in a state of creative flux.

## 2. Colors & Surface Philosophy
The palette is a high-contrast interplay of deep industrial slates and high-energy electric accents.

### The "No-Line" Rule
To maintain a premium, editorial feel, **1px solid borders are strictly prohibited for sectioning.** Boundaries must be defined through:
*   **Background Shifts:** Distinguish sections by moving from `surface` (#0a0f13) to `surface_container_low` (#0f1419).
*   **Tonal Transitions:** Use a soft gradient transition to define where a header ends and a content area begins.

### Surface Hierarchy & Nesting
Treat the UI as a physical site plan with varying elevations. 
*   **Base:** `surface` is your ground level.
*   **Sub-surface:** Use `surface_container_lowest` for recessed areas like search bars or inactive deck areas.
*   **Elevated Containers:** Use `surface_container_high` (#1b2026) for cards that need to "pop" against the background. Nesting a `surface_container_highest` element inside a `surface_container` creates immediate focal depth without a single drop shadow.

### The "Glass & Gradient" Rule
For floating menus, navigation overlays, or modular modals, use **Glassmorphism**. Combine `surface_bright` at 60% opacity with a `backdrop-blur` of 20px. 
*   **Signature Gradients:** For primary actions, use a linear gradient from `primary` (#97a9ff) to `primary_container` (#859aff) at a 135-degree angle to simulate light hitting a metallic surface.

## 3. Typography: The Editorial Edge
The typography scale utilizes **Space Grotesk** for technical, avant-garde personality and **Manrope** for utilitarian legibility.

*   **Display (Space Grotesk Bold):** Used for "hero" moments. Use `display-lg` (3.5rem) with tight letter-spacing (-0.02em) to create a sense of industrial mass.
*   **Headlines (Space Grotesk Medium):** These should drive the hierarchy. Don't be afraid of asymmetry—place headlines off-center or overlapping organic background shapes.
*   **Body (Manrope Regular):** Use `body-lg` (1rem) for all primary reading. Manrope’s geometric nature complements the "construction" aesthetic while remaining highly readable.
*   **Labels (Space Grotesk Bold, All Caps):** Use `label-md` for technical data or categories. This mimics the labels found on architectural blueprints.

## 4. Elevation & Depth
In this system, depth is a tool for storytelling, not just hierarchy.

### The Layering Principle
Stacking is preferred over spacing. Overlap a `surface_container` card 20px onto a header image to create a "built" environment. Use the Roundedness Scale (`md`: 1.5rem or `lg`: 2rem) to soften these heavy layers, making them feel like molded architectural components.

### Ambient Shadows
Shadows should feel like ambient light in a studio, not a computer-generated effect.
*   **Color-Tinted Shadows:** Shadows must use a low-opacity version of `primary` or `secondary` (e.g., `rgba(151, 169, 255, 0.08)`).
*   **Diffusion:** Use high blur values (30px+) and low spread to create a soft "glow" rather than a hard edge.

### The "Ghost Border" Fallback
If accessibility requirements demand a container edge, use a **Ghost Border**. Apply `outline_variant` (#44484e) at 15% opacity. It should be felt, not seen.

## 5. Components

### Buttons
*   **Primary:** A fluid gradient of `primary` to `primary_dim`. High roundedness (`full`). State changes should involve a slight "lift" (increasing shadow diffusion).
*   **Secondary:** Glassmorphic. `surface_bright` at 20% opacity with a `backdrop-blur`. 
*   **Tertiary (Construction Orange):** Use `tertiary` (#ff8342) for high-alert or "creative" actions. 

### Cards & Lists
*   **The Divider Ban:** Never use line dividers. Use `surface_container_low` for the list background and `surface_container` for the individual list items to create separation through tonal contrast.
*   **Asymmetry:** Occasionally break a card’s container with an image or icon that "bleeds" off the edge, reinforcing the "Fluidity" North Star.

### Input Fields
*   **Styling:** Use `surface_container_lowest` with a "Ghost Border." On focus, the border should animate into a `secondary` (#00f4fe) electric glow.
*   **Typography:** Labels use `label-md` in `on_surface_variant`.

### Tooltips & Overlays
*   **Styling:** Always Glassmorphic. Use `surface_container_highest` at 80% opacity. 
*   **Architectural Detail:** Add a 2px vertical accent bar of `secondary_dim` on the left edge of tooltips to tie back to the blueprint aesthetic.

## 6. Do's and Don'ts

### Do:
*   **Embrace Asymmetry:** Align text to the left while keeping imagery or background "organic shapes" floating to the right.
*   **Use Overlaps:** Let a "Floating Action Button" overlap two different surface containers.
*   **Incorporate Textures:** Subtle background textures like a faint dot-grid (reminiscent of blueprint paper) should be used at 5% opacity in the `background`.

### Don't:
*   **Don't use 100% Black:** Always use `background` (#0a0f13). Pure black kills the depth of the slate tones.
*   **Don't use "Boxy" Grids:** Avoid perfectly even gutters. Vary the spacing between sections to create a more editorial, avant-garde rhythm.
*   **Don't use hard shadows:** If a shadow looks like a line, it's too dark. Increase the blur and reduce opacity.

### Accessibility Note:
While we use low-contrast borders and tonal shifts, always ensure that text-to-background contrast meets WCAG AA standards using the `on_surface` and `on_primary` tokens provided. Performance and beauty must co-exist.