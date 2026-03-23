# Design System Specification: The Urban Atelier

## 1. Overview & Creative North Star: "The Curated Canvas"
This design system rejects the "templated" nature of modern web apps in favor of a high-end editorial experience. It is designed for the urban professional—someone who values the intersection of craft coffee and digital precision. 

**The Creative North Star: The Curated Canvas.** 
The interface should feel like a high-end lifestyle magazine: deliberate, spacious, and authoritative. We achieve this by breaking the rigid, centered grid. We embrace intentional asymmetry, where large serif typography (`display-lg`) overlaps subtle organic textures, and content is sectioned not by lines, but by shifts in light and tone. The goal is a "Quiet Luxury" aesthetic—professional enough for a morning meeting, yet cozy enough for a rainy afternoon.

---

## 2. Colors & Tonal Architecture
The palette is a dialogue between the warmth of a sunlit cafe and the industrial depth of the city.

### The "No-Line" Rule
**Strict Mandate:** Designers are prohibited from using 1px solid borders for sectioning or containment. Traditional "boxes" make an interface feel cramped and generic. Instead, boundaries must be defined solely through:
1.  **Background Color Shifts:** Use `surface-container-low` sections nested within a `surface` background.
2.  **Generous Negative Space:** Use the Spacing Scale (specifically `8` to `16`) to create mental groupings.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers, like stacked sheets of premium vellum.
*   **Base:** `surface` (#fbf9f4) is our primary canvas.
*   **Layer 1 (Subtle Inset):** Use `surface-container-low` for large content areas that need a soft distinction.
*   **Layer 2 (Elevated Content):** Use `surface-container-highest` for prominent cards or modal backgrounds.
*   **Layer 3 (Floating Elements):** Use `surface-container-lowest` (#ffffff) to create a "pop" of brightness that draws the eye.

### The "Glass & Gradient" Rule
To add "soul" to the digital experience:
*   **Glassmorphism:** Use `surface` colors at 70% opacity with a `20px` backdrop-blur for sticky headers or floating navigation.
*   **Signature Gradients:** For Hero backgrounds or Primary CTAs, utilize a subtle linear gradient from `primary` (#17211d) to `primary-container` (#2c3632). This adds a tactile, "roasted" depth that flat charcoal cannot achieve.

---

## 3. Typography: Editorial Authority
We utilize a high-contrast typographic scale to guide the user’s eye with intentionality.

*   **The Serif (notoSerif):** Used for `display` and `headline` levels. This is our "Brand Voice." It should be set with tighter letter-spacing and generous line-height to feel like a masthead. 
*   **The Sans (inter):** Used for `title` and `body`. This is our "Utility." Inter provides maximum readability for menus and long-form coffee descriptions.
*   **The Technical (manrope):** Reserved for `label` styles. Use this for price points, metadata (e.g., "Origin: Ethiopia"), and micro-copy.

**Editorial Tip:** Do not center-align everything. Use left-aligned `display-lg` headings paired with right-aligned `body-md` descriptions to create an asymmetric, sophisticated flow.

---

## 4. Elevation & Depth: Tonal Layering
In this design system, shadows are a last resort, not a default.

*   **The Layering Principle:** Achieve depth by "stacking" surface tiers. A `surface-container-lowest` card sitting on a `surface-container-low` section creates a natural, soft lift.
*   **Ambient Shadows:** If an element must "float" (like a floating action button), use an extra-diffused shadow: `box-shadow: 0 20px 40px rgba(27, 28, 25, 0.06)`. The shadow color is derived from `on-surface` to ensure it feels like a natural shadow cast on cream paper.
*   **The "Ghost Border" Fallback:** If accessibility requires a border, use the `outline-variant` token at **15% opacity**. It should be felt, not seen.
*   **Roundedness:** We use a refined `lg` (0.5rem) for most containers to maintain a modern edge, while `full` (9999px) is reserved exclusively for interactive pills and chips.

---

## 5. Components: Minimalist Utility

### Buttons (The Kinetic Accent)
*   **Primary:** Background `primary`, Text `on-primary`. Use `roundedness-full`.
*   **Secondary:** Background `secondary` (#944a00 - Terracotta), Text `on-secondary`. Use this for high-conversion actions like "Order Now."
*   **Tertiary:** No background. Use `title-sm` typography with an `on-surface` underline that appears only on hover.

### Input Fields
*   **Style:** Avoid the 4-sided box. Use a `surface-container-high` background with a `roundedness-sm` bottom-only highlight using the `primary` token. 
*   **Focus State:** Shift the background to `surface-container-highest` and increase the bottom highlight to 2px.

### Cards & Lists (The Editorial Grid)
*   **Rule:** **No Divider Lines.** 
*   Separate list items using `spacing-4` or `spacing-5`. 
*   For cards, use a background of `surface-container-low` and internal padding of `spacing-6`. 
*   **Coffee Feature Card:** Use an asymmetric layout where the image (with `roundedness-xl`) breaks the top boundary of the container.

### Chips (The Filter System)
*   **Filter Chips:** Use `surface-container-high` for unselected and `primary` for selected. 
*   Keep typography to `label-md` for a precise, technical look.

---

## 6. Do’s and Don’ts

### Do:
*   **Do** use `spacing-16` or `spacing-20` between major sections to let the design breathe.
*   **Do** use `secondary` (Terracotta) sparingly as a "heat" accent for price points or alerts.
*   **Do** use high-quality photography with warm, desaturated tones to match the `background` (#fbf9f4).

### Don’t:
*   **Don’t** use pure black (#000000). Always use `primary` (#17211d) for "Black" text.
*   **Don’t** use standard 1px dividers. If you must separate content, use a 1px tall block of `outline-variant` at 20% opacity that doesn't span the full width.
*   **Don’t** crowd the edges. If a container feels full, increase the padding by two steps on the Spacing Scale.