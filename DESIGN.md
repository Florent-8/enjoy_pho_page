# Design System Document

## 1. Overview & Creative North Star: "The Living Steam"
This design system rejects the "fast-food grid" in favor of a high-end editorial experience that mirrors the ritual of enjoying a bowl of Pho. Our Creative North Star is **"The Living Steam"**—a concept that emphasizes fluidity, warmth, and organic layering. 

To achieve this, we move away from rigid, boxed layouts. We utilize **intentional asymmetry**, allowing elements to breathe and overlap as if they were fresh herbs scattered on a table. By leveraging high-contrast typography scales and deep tonal depth, we transform a simple menu into a curated culinary journey. The interface should feel less like a software application and more like a premium lifestyle magazine.

---

## 2. Colors: Tonal Depth over Borders
The palette is rooted in the lush landscapes of Vietnam. We utilize the contrast between the deep, nourishing greens and the warm, breathable ivory to create a sense of calm.

### The "No-Line" Rule
**Explicit Instruction:** 1px solid borders are strictly prohibited for sectioning content. Visual boundaries must be defined exclusively through background color shifts. For example, a `surface-container-low` section should sit directly against a `surface` background. The transition of color is the boundary.

### Surface Hierarchy & Nesting
Treat the UI as physical layers of fine handmade paper. 
*   **Base:** `surface` (#fbfaee) acts as our ivory canvas.
*   **Layering:** Use `surface-container-low` (#f5f4e8) for secondary content areas and `surface-container-high` (#e9e9dd) for interactive elements that need to feel "closer" to the user.
*   **Nesting:** A `surface-container-lowest` (#ffffff) card placed inside a `surface-container-low` section creates a natural, soft lift that feels integrated rather than forced.

### The "Glass & Gradient" Rule
To evoke the "steam" motif, floating elements (like navigation bars or modal overlays) should utilize **Glassmorphism**. Apply `surface` at 80% opacity with a `24px` backdrop blur. 
*   **Signature Textures:** Use subtle linear gradients for CTAs, transitioning from `primary` (#004434) to `primary-container` (#1a5c4a). This adds a "soul" to the buttons that flat color cannot replicate.

---

## 3. Typography: Editorial Elegance
The typography system balances the modern precision of *Plus Jakarta Sans* with the airy, rhythmic quality of *Be Vietnam Pro*.

*   **Display & Headlines (Plus Jakarta Sans):** These are our "hero" moments. Use `display-lg` and `headline-lg` with generous tracking (-0.02em) to create an authoritative, premium feel. The stroke quality of Jakarta Sans provides a subtle nod to Asian calligraphy without being literal or cliché.
*   **Body (Be Vietnam Pro):** Our body text is designed to feel "light and airy." Use `body-lg` for descriptions to maintain readability and a "spa-like" openness. 
*   **Hierarchy as Brand:** Use extreme scale shifts. A `display-md` headline paired with a `label-md` uppercase subtitle creates a high-end editorial contrast that guides the eye through the "nourishing" content.

---

## 4. Elevation & Depth: Atmospheric Layering
We do not use shadows to create "pop"; we use them to create "atmosphere."

*   **The Layering Principle:** Depth is achieved by "stacking" the `surface-container` tiers. A `surface-container-lowest` card on a `surface-container-low` background provides enough contrast to be legible without a single pixel of shadow.
*   **Ambient Shadows:** If a floating effect is required (e.g., a "Quick Add" FAB), use an extra-diffused shadow: `box-shadow: 0 12px 40px rgba(27, 28, 21, 0.06);`. The shadow color is a tint of our `on-surface` (#1b1c15), ensuring it looks like a natural cast light.
*   **The "Ghost Border" Fallback:** If a container absolutely requires a boundary for accessibility, use the `outline-variant` (#bfc9c3) at **15% opacity**. This creates a "whisper" of a line rather than a hard edge.

---

## 5. Components: Organic Primitives

### Buttons
*   **Primary:** Gradient fill (`primary` to `primary-container`), white text (`on-primary`), and `xl` (1.5rem) roundedness. No border.
*   **Secondary:** `surface-container-highest` fill with `primary` text. This feels like a soft stone button.
*   **Tertiary:** Pure text in `secondary` (#326856) with a subtle underline that only appears on hover.

### Cards & Menu Items
*   **The Rule:** Forbid divider lines between items. 
*   **Implementation:** Use vertical white space (32px or 48px) to separate items. For menu categories, use a subtle background shift to `surface-container-low` to group items together.
*   **Visual Motifs:** Incorporate a "Steam Wisp" SVG pattern as a background element for featured cards, using `outline-variant` at 5% opacity.

### Inputs & Fields
*   **Style:** Minimalist. Only a bottom stroke using `outline-variant` at 40% opacity. 
*   **Focus State:** The bottom stroke transitions to `primary` (#004434) and thickens to 2px. No "box" focus states.

### Signature Component: The "Herb Tag" (Chips)
*   **Selection Chips:** Use `secondary-fixed` (#b6eed8) with `on-secondary-fixed` (#002117) text. The roundedness should be `full` to mimic the shape of a mint or basil leaf.

---

## 6. Do's and Don'ts

### Do:
*   **Embrace Asymmetry:** Let food photography bleed off the edge of the screen.
*   **Use Generous White Space:** If a layout feels "full," remove an element. The brand is "clean and wholesome."
*   **Layer Surfaces:** Use `surface-container` tiers to create hierarchy.
*   **Textural Dividers:** Use a single, thin bamboo-inspired line motif (0.5pt stroke) only at the very end of long-form content as a "sign-off."

### Don't:
*   **Don't use 100% black:** Always use `on-surface` (#1b1c15) or `primary` for text to keep the heat "soft."
*   **Don't use hard corners:** Avoid `none` or `sm` roundedness. Stay within `md` to `xl` to maintain the "organic" feel.
*   **Don't use standard Dividers:** Never use a gray `<hr>` tag. Use space or color transitions instead.
*   **Don't crowd the Steam:** If using herb or steam motifs, ensure they do not overlap with legibility-critical text. They are "vibes," not "content."