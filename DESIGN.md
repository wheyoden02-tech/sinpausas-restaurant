# Design System Document: The Curated Hearth

## 1. Overview & Creative North Star

This design system is built to evoke the "Curated Hearth"—a digital translation of the rugged, mist-covered beauty of Chiloé. It rejects the sterility of standard SaaS interfaces in favor of a **High-End Editorial** experience. We are not building a utility app; we are crafting a digital gastronomic magazine that breathes with the rhythm of the Chilean archipelago.

### The Creative North Star: "Organic Editorial"
The system breaks the "template" look through **intentional asymmetry** and **tonal depth**. We achieve a premium feel by treating the screen like a physical page of a luxury publication. This means:
*   **Generous Negative Space:** White space is not "empty"; it is a luxury material.
*   **Layered Textures:** Subtle paper and linen overlays that soften the digital glow.
*   **Asymmetric Balance:** Elements should feel like they were placed by hand, often overlapping containers to break the rigid grid.

---

## 2. Colors & Surface Philosophy

The palette is rooted in the desaturated, earthy tones of Southern Patagonia. We move beyond flat hex codes by focusing on how light interacts with materials.

### The "No-Line" Rule
**Explicit Instruction:** Designers are prohibited from using 1px solid borders to define sections. Boundaries must be established through:
1.  **Background Shifts:** Transitioning from `surface` (#fef9f1) to `surface-container-low` (#f8f3eb).
2.  **Tonal Transitions:** Using `surface-container` tiers to create logical groupings.

### Surface Hierarchy & Nesting
Treat the UI as a series of stacked, fine paper sheets. 
*   **Base:** `surface` (#fef9f1) as the canvas.
*   **Nested Content:** Use `surface-container-lowest` (#ffffff) for high-priority cards to create a subtle "lift" against the cream background.
*   **Recessed Content:** Use `surface-dim` (#ded9d2) for footers or utility bars to ground the experience.

### The "Glass & Gradient" Rule
To capture the misty atmosphere of the archipelago, use **Glassmorphism** for floating elements (like navigation bars or modal overlays). 
*   **Implementation:** Use a semi-transparent `surface` color with a `backdrop-blur` of 12px–20px. 
*   **Signature Gradients:** Apply a subtle radial gradient from `primary` (#502c12) to `primary-container` (#6b4226) for main CTAs to give them the depth of polished wood.

---

## 3. Typography

The typography scale relies on the tension between a sophisticated serif and a functional sans-serif.

*   **Display & Headline (Newsreader):** This is our "voice." Used for titles, quotes, and section headers. It should be typeset with slightly tighter letter-spacing for a high-end magazine feel.
*   **Body & Labels (Manrope):** This is our "engine." It provides clarity and modern contrast to the serif. 

**Hierarchy Strategy:**
*   **Scale Contrast:** Don't be afraid to pair a `display-lg` headline with a `label-sm` caption immediately below it. This high-low contrast is a hallmark of premium editorial design.
*   **Intentional Weight:** Use `primary` (#502c12) for headlines to ensure warmth and readability, while using `on-surface-variant` (#51443d) for body text to reduce eye strain and maintain the "desaturated" aesthetic.

---

## 4. Elevation & Depth

In this system, depth is organic, not structural. We avoid heavy shadows that feel "tech-heavy."

*   **Tonal Layering:** Instead of a shadow, place a `surface-container-lowest` card on a `surface-container-high` background. The difference in luminance provides all the separation required.
*   **Ambient Shadows:** If a floating element is necessary (e.g., a "Book a Table" FAB), use a wide-spread, low-opacity shadow. 
    *   *Spec:* `0px 12px 32px rgba(29, 28, 23, 0.06)`. The color is a tint of our `on-surface`, never pure black.
*   **The "Ghost Border" Fallback:** If a container requires a border for accessibility, use `outline-variant` (#d5c3b9) at **15% opacity**. It should be felt, not seen.
*   **Texture Overlays:** Apply a 2% opacity "Linen Texture" noise layer globally over `surface` colors to break the digital flatness and reinforce the "rustic soul."

---

## 5. Components

### Buttons
*   **Primary:** `primary` (#502c12) background, `on-primary` (#ffffff) text. Use `md` (0.375rem) roundedness. 
*   **Secondary (Editorial):** A "Ghost" style button. No background, no border, just a `title-sm` weight label with a subtle `primary` underline that expands on hover.
*   **Tertiary:** `secondary-container` (#d0e7b9) with `on-secondary-container` (#546944) text for low-priority actions like "Filter."

### Cards & Lists
*   **The Rule of Space:** Forbid the use of divider lines. Separate list items using 24px–32px of vertical white space.
*   **Editorial Cards:** Images should use `md` (0.375rem) corner radius. Captions should be placed asymmetrically—overlapping the image edge or set in a wide margin.

### Input Fields
*   **Style:** Minimalist. Only a bottom border using `outline` (#83746c) at 30% opacity. 
*   **State:** When focused, the border transitions to `primary` (#502c12) and the label (Manrope) shifts to a small `label-sm` above the line.

### Menu Items (Specific to App)
*   Use `display-sm` for dish titles.
*   Use `body-md` in `on-surface-variant` (#51443d) for descriptions.
*   **The Signature Element:** Use a `tertiary` (#243552) accent dot or small icon to denote "Traditional Chiloté Recipe."

---

## 6. Do’s and Don’ts

### Do:
*   **Do** use asymmetrical layouts. Let an image bleed off the edge of the screen.
*   **Do** lean into the "Wood Brown" and "Moss Green" for interactive elements to ground the UI in nature.
*   **Do** use large, high-quality photography as a primary UI "material."

### Don't:
*   **Don't** use 100% black (#000000). Use `on-surface` (#1d1c17) for all text.
*   **Don't** use sharp corners. Always use at least the `sm` (0.125rem) radius to soften the experience.
*   **Don't** crowd the content. If you think there is enough padding, add 16px more.
*   **Don't** use standard "Material Design" blue for links or errors. Use `tertiary` for accents and `error` (#ba1a1a) only when absolutely critical.