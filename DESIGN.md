# Design System Strategy: The Radiant Ritual

## 1. Overview & Creative North Star
The "Creative North Star" for this design system is **The Radiant Ritual**. 

Instead of a utilitarian checklist, we are building a "Digital Sanctuary" that mimics the gradual transition of a sunrise. The goal is to move away from the rigid, boxed-in feel of standard productivity apps. We achieve this through **Organic Editorialism**: a layout style that uses intentional asymmetry, generous white space (breathing room), and a "High-Contrast, Low-Tension" typography scale. By overlapping elements and using fluid tonal transitions, we create a sense of momentum that feels energizing for the morning, yet calm enough to prevent "notification anxiety."

## 2. Colors & Tonal Architecture
The palette is rooted in the warmth of a dawning sun. We avoid clinical whites and harsh blacks in favor of creams, ambers, and deep terracottas.

*   **Primary Palette:** Use `primary` (#9b4500) for high-intent actions and `secondary-container` (#fec330) for moments of joy or completion.
*   **The "No-Line" Rule:** This is a hard requirement. Designers are prohibited from using 1px solid borders to define sections. Boundaries must be defined through **Background Color Shifts**. For example, a task card should not have a border; it should be a `surface-container-low` shape sitting on a `surface` background.
*   **Surface Hierarchy & Nesting:** Treat the UI as physical layers of fine paper. 
    *   **Level 0:** `surface` (#fdf9f0) - The base canvas.
    *   **Level 1:** `surface-container-low` (#f7f3ea) - Large layout blocks.
    *   **Level 2:** `surface-container` (#f1eee5) - Interactive cards.
    *   **Level 3:** `surface-container-highest` (#e6e2d9) - Floating elements or active states.
*   **The "Glass & Gradient" Rule:** To provide "soul," use subtle linear gradients for hero components, transitioning from `primary` (#9b4500) to `primary-container` (#ff8c42). For floating navigation or over-content modals, use Glassmorphism: `surface-container-lowest` at 80% opacity with a `24px` backdrop blur.

## 3. Typography: Editorial Rhythm
We use a dual-font strategy to balance "Playful Energy" with "Clear Instruction."

*   **The Voice (Plus Jakarta Sans):** Used for `display` and `headline` tiers. This typeface provides the "Playful" personality. Use `display-lg` for morning greetings (e.g., "Good Morning, Alex") to create a high-end magazine feel. Don't be afraid of tight letter-spacing (-2%) on large headlines.
*   **The Guide (Be Vietnam Pro):** Used for `title`, `body`, and `label` tiers. This ensures high legibility for task descriptions. 
*   **Hierarchy Tip:** Use `title-lg` for task names but keep `body-md` for descriptions. Always ensure `on-surface-variant` (#564338) is used for secondary text to maintain a soft, low-contrast "calm" against the vibrant primary accents.

## 4. Elevation & Depth: Tonal Layering
Traditional drop shadows are too "heavy" for a sunrise aesthetic. We use light to create volume.

*   **The Layering Principle:** Depth is achieved by stacking. An inner card should be `surface-container-lowest` (#ffffff) nested inside a `surface-container` (#f1eee5) parent. This creates a natural "lift" without artificial shadows.
*   **Ambient Shadows:** If an element must float (like a Floating Action Button), use an extra-diffused shadow: `offset: 0, 12px; blur: 32px; color: rgba(28, 28, 23, 0.06)`. The tint is derived from `on-surface`, never pure black.
*   **The "Ghost Border":** For accessibility in input fields, use the `outline-variant` (#ddc1b3) but at **20% opacity**. It should feel like a suggestion of a boundary, not a cage.

## 5. Components

### Buttons
*   **Primary:** Pill-shaped (`rounded-full`). Background is a gradient of `primary` to `primary-container`. Text is `on-primary` (#ffffff), bold.
*   **Secondary:** `surface-container-high` background with `primary` text. No border.
*   **Haptic Feedback:** All buttons should feel "squishy"—design for a subtle scale-down (0.96) on tap.

### Ritual Cards & Lists
*   **The Divider Ban:** Never use horizontal lines. Use `1.5rem` (`md`) vertical spacing between list items.
*   **Progress Cards:** Use `rounded-xl` (3rem) for the main container. Incorporate a `tertiary-container` (#cfa091) accent for tasks that are "in progress" to provide a soft, earthy contrast to the sun-themed primary colors.

### The "Sun" Progress Meter
*   A custom component for this system. Use a thick semi-circular stroke. The "track" is `surface-variant` (#e6e2d9) and the "progress" is a `primary` gradient. This mimics the sun rising as the user completes their routine.

### Input Fields
*   Background: `surface-container-low`.
*   Corners: `rounded-DEFAULT` (1rem).
*   Focus State: A `2px` "Ghost Border" of `primary` at 40% opacity and a subtle `surface-tint` glow.

## 6. Do's and Don'ts

### Do:
*   **Embrace Asymmetry:** Place your `display-lg` headlines off-center to create an editorial, bespoke feel.
*   **Use Generous Padding:** Mobile-first doesn't mean cramped. Use a minimum of `1.5rem` internal padding for all containers.
*   **Tonal Transitions:** Use `surface-bright` for the very top of the scroll view to simulate the brightest part of the sky.

### Don't:
*   **Don't use 100% Black:** Even for text, use `on-surface` (#1c1c17). Pure black breaks the "Warm Sunrise" immersion.
*   **Don't use "Standard" Shadows:** Avoid the default CSS `box-shadow: 0 2px 4px`. It looks cheap. Stick to the Ambient Shadow spec.
*   **Don't Over-Iconize:** Let the typography do the heavy lifting. Use icons sparingly, and only in "Soft" or "Rounded" styles to match the typography's curves.