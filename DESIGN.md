# Design System Strategy: High-End Editorial Music Experience

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Nocturnal Curator."** 

We are moving away from the "utility-first" look of standard streaming platforms and toward a high-end editorial experience. This system captures the energy of a live venue at midnight—high contrast, immersive, and premium. We break the traditional grid through **intentional asymmetry** and **overlapping depth**. Instead of placing elements side-by-side in rigid columns, we use the heavy `Roundedness Scale` and large-scale typography to create a layout that feels like a physical magazine brought to life in a digital, glowing space.

The aesthetic goal is to make the user feel less like they are browsing a database and more like they are interacting with a living, vibrating piece of art.

---

## 2. Colors
Our palette is rooted in the high-energy tension between **Deep Obsidian (#0D0D0D)** and **Electric Lime (#E2FF3B)**, with **Magenta Pulse (#FF007A)** reserved for high-frequency emotional triggers (likes, active states, and live alerts).

*   **The "No-Line" Rule:** Under no circumstances are 1px solid borders to be used for sectioning or containment. Boundaries must be defined solely through background color shifts. For example, a card should be distinguished from the background by moving from `surface` (#0e0e0e) to `surface_container_low` (#131313). 
*   **Surface Hierarchy & Nesting:** Treat the UI as a series of physical layers. Nesting is key: A `surface_container_highest` (#262626) element should only exist inside a `surface_container` (#1a1919) or lower to create a natural, "stacked" logic.
*   **The "Glass & Gradient" Rule:** To achieve a premium feel, floating players or navigation bars must utilize **Glassmorphism**. Use `surface_container_high` at 60% opacity with a `backdrop-blur` of 20px–40px. 
*   **Signature Textures:** Use subtle linear gradients (from `primary` to `primary_container`) for main Action Buttons. This provides a "soul" to the color that flat hex codes cannot achieve, mimicking the way light hits a physical surface.

---

## 3. Typography
We utilize a high-contrast pairing to drive the editorial tone. We use **Space Grotesk** for high-impact brand moments and **Manrope** for functional, geometric clarity.

*   **Display & Headlines (Space Grotesk):** These should be treated as graphic elements. Use `display-lg` (3.5rem) with tight letter-spacing to create an aggressive, high-fashion look.
*   **Titles & Body (Manrope):** We use a geometric sans-serif to maintain a "tech-forward" feel while ensuring maximum legibility. `title-lg` (1.375rem) provides enough weight to anchor a section without competing with the display type.
*   **Hierarchy as Identity:** The massive jump between `display-lg` and `body-md` is intentional. This "Typographic Tension" is what creates the premium editorial feel.

---

## 4. Elevation & Depth
In this system, depth is a functional tool, not just a visual flourish.

*   **The Layering Principle:** Depth is achieved through Tonal Layering. If a section needs to stand out, do not add a border; instead, drop the background of that section to `surface_container_lowest` (#000000) to create a "well" or lift it to `surface_bright` (#2c2c2c) to create a "plateau."
*   **Ambient Shadows:** For floating elements like Modals or Now-Playing sheets, use extra-diffused shadows. 
    *   *Spec:* Blur: 40px–60px | Opacity: 8% | Color: `primary` (tinted). This mimics the "glow" of the Electric Lime reflecting off the Obsidian surface.
*   **The "Ghost Border" Fallback:** If accessibility requirements demand a container boundary, use a "Ghost Border." This is the `outline_variant` (#484847) token set to **15% opacity**. It should be felt, not seen.
*   **Immersive Blurs:** Backgrounds should frequently utilize a 60% blurred version of the current album art. This anchors the UI in the music and softens the harshness of the high-contrast palette.

---

## 5. Components

### Buttons
*   **Primary:** Uses `primary` (#e2ff3a) background with `on_primary` (#536000) text. Corner radius must be `full` (9999px) for that "pill" aesthetic. Use a subtle glow shadow on hover.
*   **Secondary:** Glassmorphic. `surface_container_high` at 40% opacity with a `Ghost Border`.

### Cards & Lists
*   **No Dividers:** Forbid the use of 1px lines between list items. Use the `Spacing Scale` (specifically `6` or `2rem`) to create clean, breathable "white space" (Obsidian space) to separate tracks or albums.
*   **Album Art:** Always use the `xl` (3rem) corner radius for album thumbnails to match the high-energy, rounded theme.

### Chips
*   **Filter Chips:** Use `surface_container_highest` for unselected and `primary` for selected. Sizing should be compact but touch-friendly, following the `spacing-3` scale for internal padding.

### Input Fields
*   **Interaction:** Text inputs should not have a bottom line or a full box. Use a `surface_container_low` background with a `full` corner radius. When focused, the "Ghost Border" should transition to 100% opacity `primary`.

### Navigation (The Pulse Bar)
*   The bottom navigation should be a floating glass element, decoupled from the screen edges using `spacing-4` (1.4rem) margins. This creates an "object" feel rather than a "utility" feel.

---

## 6. Do's and Don'ts

### Do
*   **DO** use intentional asymmetry. Overlap an album cover slightly over a headline to create depth.
*   **DO** lean into the `xl` (3rem) roundedness for large containers; it softens the high-contrast "Electric Lime."
*   **DO** use the `secondary` (Magenta Pulse) sparingly—only for "Live" indicators, "Favorite" toggles, or critical errors.

### Don'ts
*   **DON'T** use pure grey for shadows. Always tint shadows with a hint of the `primary` or `background` color to maintain tonal richness.
*   **DON'T** use 1px solid borders. If the design feels "flat," adjust your `surface_container` tiers instead of reaching for a line.
*   **DON'T** use standard geometric alignments. Experiment with `title-lg` labels being placed vertically or at the very edge of the screen to lean into the editorial look.
*   **DON'T** clutter the UI. If you have more than 5 elements on a screen, check if you can use a horizontal scroll (using the `spacing-6` gap) to hide secondary info.