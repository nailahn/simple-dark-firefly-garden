# Design System Document: The Living Nocturne

## 1. Overview & Creative North Star
**Creative North Star: The Ethereal Jardin**

This design system rejects the sterile rigidity of modern software. Inspired by the poetic, hand-drawn legacy of early-2000s web illustration, it envisions the interface not as a tool, but as a "living, breathing illustration." We are moving away from the "app" feel toward an immersive "misty night garden."

The system is defined by **Intentional Imperfection**. To achieve a high-end, bespoke aesthetic, designers must actively fight the urge for symmetry and geometric precision. Every element should feel as though it was painted onto a wet canvas, with pigment bleeding into the deep indigo air.

## 2. Colors
The palette is a study in tonal depth, transitioning from the crushing depths of a midnight sky to the vibrant, bioluminescent glow of fireflies.

*   **Atmospheric Foundations:** Use `background` (#10141a) and `surface` for the core environment. These deep indigos and teals create the "fog" that recedes into the distance.
*   **Bioluminescent Highlights:** The `tertiary` (#c2cf47) and `secondary` (#94d3c1) tokens represent our fireflies. These are reserved for moments of high interaction or vital focus.
*   **The "No-Line" Rule:** 1px solid borders are strictly prohibited. Boundaries must be defined through background shifts (e.g., a `surface-container-low` element resting on a `surface` background) or soft, volumetric gradients.
*   **Surface Hierarchy & Nesting:** Treat the UI as layers of mist. Use `surface-container-lowest` for distant, background-level elements and `surface-container-highest` for elements that "drift" closer to the user.
*   **The Glass & Gradient Rule:** To mimic watercolor bleeds, use semi-transparent `surface-variant` colors with heavy `backdrop-filter: blur()`. CTA elements should utilize a radial gradient transitioning from `primary` (#bdc2ff) to `primary-container` (#1a237e) to simulate a soft, glowing orb rather than a flat button.

## 3. Typography
While the primary experience is visual, any necessary textual metadata uses **Plus Jakarta Sans** to maintain a modern editorial edge against the organic background.

*   **Visual Weighting:** Use the typography scale to define the *scale* of organic symbols. A `display-lg` scale should govern the size of primary focal points, while `label-sm` dictates the size of minor "spark" elements.
*   **Hierarchy of Presence:** `headline-lg` and `headline-md` should be used sparingly, treated as "titles of a painting." They convey authority through whitespace rather than bold weight.
*   **Text as Texture:** When text appears, it should feel "etched" into the mist. Use `on-surface-variant` with a slightly reduced opacity to ensure the typography feels like part of the environment, not an overlay.

## 4. Elevation & Depth
In this system, depth is atmospheric, not structural. We replace "shadows" with "glows" and "occlusion."

*   **The Layering Principle:** Stack `surface-container` tiers to create a natural lift. An "active" element doesn't move "up" on a Z-axis; it becomes "clearer" as if moving out of a fog.
*   **Ambient Shadows:** Traditional drop shadows are replaced by "Bloom." If an element must float, use a wide, soft outer glow using the `surface-tint` color at 5% opacity.
*   **The "Ghost Border" Fallback:** If a container requires a boundary, use the `outline-variant` at 15% opacity, but apply a non-uniform border-radius or a subtle SVG mask to ensure the line feels hand-drawn.
*   **Glassmorphism:** All "floating" containers must use `surface-container-high` with a 20px–40px backdrop blur. This allows the midnight garden colors to bleed through, maintaining the "wet-on-wet" watercolor feel.

## 5. Components

### Navigation & Interaction (The "Fireflies")
*   **Interactive Orbs (Buttons):** Forgo rectangular buttons. Use asymmetric, soft-edged shapes. The `primary` state should feel like a concentrated glow. On hover, increase the "bloom" (glow) rather than changing the color.
*   **Floating Clusters (Chips):** Use `secondary-container` for background elements. They should be clustered asymmetrically, mimicking a swarm of insects or a patch of flora.

### Containers & Lists
*   **Organic Canvases (Cards):** Cards must never have a 100% straight edge. Use `surface-container-low` and apply an irregular mask.
*   **The Divider Ban:** Never use lines to separate content. Use the **Spacing Scale** (e.g., `spacing-12` or `spacing-16`) to create "clearings" in the mist. Content is separated by distance and darkness, not by strokes.

### Inputs & Feedback
*   **Glow States (Inputs):** When an area is "active," the `tertiary-fixed` (#dfec60) color should pulse gently, mimicking the heartbeat of a firefly.
*   **Misty Overlays (Tooltips/Modals):** These should be the most "transparent" elements in the system. Use `surface-bright` with 60% opacity and a high blur.

## 6. Do's and Don'ts

### Do:
*   **Embrace Asymmetry:** If you have three elements, place them in a staggered, organic cluster rather than a row.
*   **Bleed the Edges:** Allow gradients to spill outside of their perceived "containers."
*   **Use Tonal Transitions:** Transition from `midnight blue` to `dark teal` to create a sense of vast, humid space.
*   **Animate with Intent:** Interactions should feel "floaty" and eased. Use long duration, high-latency transitions.

### Don't:
*   **No Geometric Perfection:** Never use a perfect circle or a square with 0px border-radius.
*   **No Pure White:** The brightest light should be the warm yellow-green of the `tertiary` token, never `#FFFFFF`.
*   **No Rigid Grids:** Avoid 12-column layouts. Use "Focal Points" and "Negative Space" to guide the eye.
*   **No High Contrast Borders:** If you see a hard line, the "mist" is broken. Soften it.