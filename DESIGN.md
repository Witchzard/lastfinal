# Design System Document: The Ethereal Momentum

## 1. Overview & Creative North Star: "The Digital Sanctuary"
The objective of this design system is to transcend the utility of a standard "tracker" and become a "sanctuary." We are moving away from the rigid, boxed-in layouts of traditional productivity apps. 

**The Creative North Star: "The Digital Sanctuary"**
This system is built on the philosophy of **Adaptive Luminosity**. Instead of using lines to contain data, we use light, depth, and breathing room to guide the eye. We break the "template" look through:
*   **Intentional Asymmetry:** Hero sections should utilize off-center typography and overlapping glass cards to create a sense of organic movement.
*   **Tonal Depth:** Replacing harsh borders with a sophisticated stacking of semi-transparent surfaces.
*   **High-Contrast Scale:** Using massive `display-lg` headers against delicate `label-sm` metadata to create an editorial, high-end feel.

---

## 2. Colors & Surface Philosophy
The palette balances the "Deep Indigo" authority with "Mint Green" vitality. However, the secret to the premium feel lies in how we treat the neutrals and backgrounds.

### The "No-Line" Rule
**Standard 1px borders are strictly prohibited.** Boundaries must be defined solely through background color shifts. To separate a section, transition from `surface` (#f6fafe) to `surface-container-low` (#f0f4f8). This creates a "soft-edge" transition that feels sophisticated rather than clinical.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers of frosted glass.
*   **Base:** `surface` (#f6fafe)
*   **Sectioning:** `surface-container` (#eaeef2)
*   **Elevated Components:** `surface-container-lowest` (#ffffff) for high-contrast cards.

### The "Glass & Gradient" Rule
To achieve the signature "Soft UI" look:
*   **Glassmorphism:** Use `primary_container` (#4f46e5) with a 60-80% opacity and a `20px` backdrop blur for floating action elements.
*   **Signature Textures:** Main CTAs should not be flat. Use a linear gradient from `primary` (#3525cd) to `primary_container` (#4f46e5) at a 135-degree angle to provide visual "soul."

---

## 3. Typography: Editorial Authority
We pair **Plus Jakarta Sans** (Display/Headlines) for its modern, geometric confidence with **Manrope** (Body/Labels) for its high legibility and soft curves.

*   **Display (Plus Jakarta Sans):** Used for "Big Wins" and daily streaks. The size difference between `display-lg` (3.5rem) and `body-md` (0.875rem) should be exploited to create a dramatic, premium hierarchy.
*   **Headlines (Plus Jakarta Sans):** Bold, tight tracking (-0.02em). Use these to anchor sections.
*   **Body & Labels (Manrope):** Generous line height (1.6x) for body text to maintain the "lightweight" feel. 
*   **The Identity Shift:** Typography is not just for reading; it is a graphical element. Don't be afraid to let a `headline-lg` overlap a glass card slightly to break the grid.

---

## 4. Elevation & Depth: Tonal Layering
Traditional shadows are too "heavy" for this system. We use light to lift objects.

*   **The Layering Principle:** Place a `surface-container-lowest` (#ffffff) card on a `surface-container-low` (#f0f4f8) background. The delta in lightness provides enough "lift" for the human eye without a single drop shadow.
*   **Ambient Shadows:** For floating elements (like a FAB), use a blur of `32px` and a color derived from `on_surface` at 6% opacity. It should feel like a soft glow, not a shadow.
*   **The "Ghost Border" Fallback:** If a divider is essential for accessibility, use the `outline_variant` (#c7c4d8) at **15% opacity**. It should be barely perceptible.
*   **Glass Depth:** For modal overlays, use `surface_variant` at 40% opacity with a `12px` backdrop blur. This ensures the user never loses context of the "world" beneath the current task.

---

## 5. Components

### Cards & Lists
*   **The "No-Divider" Rule:** Forbid 1px lines between list items. Use `spacing-4` (1.4rem) to create separation through "white space." 
*   **Habit Cards:** Use `surface-container-lowest` with a `DEFAULT` (1rem) roundedness. Use a vertical `tertiary_fixed` (#6ffbbe) pill on the far left to indicate a "Success" state instead of a checkbox.

### Buttons
*   **Primary:** Gradient (`primary` to `primary_container`), `full` roundedness, `headline-sm` type.
*   **Secondary:** `surface-container-highest` background with `primary` text. No border.
*   **Tertiary:** Transparent background, `primary` text, bold weight.

### Input Fields
*   **Styling:** Use `surface-container-low` for the input track. Upon focus, transition the background to `surface-container-lowest` and add a "Ghost Border" of `primary` at 20% opacity. 
*   **Labels:** Use `label-md` in `on_surface_variant` (#464555), positioned `spacing-1` above the input.

### Progress Orbs (Custom Component)
*   Instead of flat progress bars, use concentric "Glass Orbs." Use `tertiary_container` for the track and a glowing `tertiary` (#005338) for the progress, utilizing a subtle outer glow to simulate "energy."

---

## 6. Do's and Don'ts

### Do:
*   **DO** use whitespace as a functional element. If a screen feels "busy," increase spacing tokens rather than adding borders.
*   **DO** use `tertiary` (Mint Green) sparingly. It is a reward color, used only for completed habits and positive trend lines.
*   **DO** ensure all glassmorphic containers have a minimum backdrop-blur of `10px` to maintain text legibility.

### Don't:
*   **DON'T** use pure black (#000000). Use `on_surface` (#171c1f) for all "black" text to maintain the soft, premium feel.
*   **DON'T** use "Drop Shadows" from a standard UI kit. Use the Ambient Shadow guidelines (low opacity, high blur).
*   **DON'T** use sharp corners. The minimum radius is `sm` (0.5rem); the standard is `DEFAULT` (1rem).
*   **DON'T** use 100% opaque secondary buttons. They should feel integrated into the surface, not sitting on top of it.