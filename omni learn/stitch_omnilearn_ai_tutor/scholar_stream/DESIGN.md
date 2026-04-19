# Design System Document: The Guided Luminary

## 1. Overview & Creative North Star
This design system is built upon the "Guided Luminary" creative north star. For an AI-driven educational platform, we must move away from the cluttered, "dashboard-heavy" aesthetics of legacy LMS platforms. Instead, we embrace an **Editorial Clarity**—a high-end, bespoke experience that feels like a premium digital textbook meets a high-end productivity suite.

The system breaks the "standard template" look through **intentional asymmetry**, large-scale typography, and **tonal depth**. We treat the screen as a canvas of layered light and paper, using breathing room (white space) not just as a gap, but as a structural element that guides the student's focus toward their learning goals.

---

## 2. Colors: Tonal Architecture
The palette is rooted in authoritative blues (`primary`) and success-driven greens (`tertiary`), set against a sophisticated, calm neutral foundation.

### The "No-Line" Rule
**Explicit Instruction:** Traditional 1px solid borders for sectioning are strictly prohibited. We define boundaries through background color shifts and tonal transitions. 
- To separate a sidebar from a main content area, place a `surface-container-low` panel against a `surface` background.
- To highlight a lesson module, use a `surface-container-highest` card on a `surface-container` background.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. 
- **Base Layer:** `surface` (#f8f9ff) for the overall canvas.
- **Content Blocks:** `surface-container-low` or `surface-container-lowest` for primary interaction areas.
- **Nested Detail:** Use `surface-container-high` for internal components (like a search bar inside a header).

### The Glass & Gradient Rule
To prevent the UI from feeling "flat," use **Glassmorphism** for floating elements (e.g., sticky headers or mobile navigation). Apply `surface-container-lowest` with a 70% opacity and a 20px backdrop-blur. 
- **Signature Gradients:** For main Hero sections or high-impact CTAs, use a subtle linear gradient from `primary` (#00497d) to `primary-container` (#0061a4) at a 135-degree angle. This adds a "soulful" depth that a flat fill cannot provide.

---

## 3. Typography: The Editorial Voice
We utilize a dual-font strategy to balance authority with friendliness.

*   **Display & Headings (Plus Jakarta Sans):** A slightly rounded, modern sans-serif. It conveys a "friendly mentor" persona. Use `display-lg` for hero welcome messages to create an immediate, high-impact editorial feel.
*   **Body & Labels (Manrope):** A high-readability, geometric sans-serif designed for sustained reading. It provides the "trustworthy" backbone for educational content.

**Hierarchy Strategy:** 
- Use `headline-lg` for lesson titles to command attention.
- Use `body-lg` for instructional text to ensure accessibility for all students.
- `label-md` should be used sparingly for metadata (e.g., "5 mins remaining"), typeset in all-caps with 0.05em letter spacing for an architectural touch.

---

## 4. Elevation & Depth: Tonal Layering
In this system, depth is a feeling, not a drop-shadow.

*   **The Layering Principle:** Stacking tiers creates natural lift. A `surface-container-lowest` (#ffffff) card placed on a `surface-container-low` (#f2f3fa) background provides enough contrast to be perceived as "elevated" without a single shadow pixel.
*   **Ambient Shadows:** If an element must float (e.g., a modal or a floating action button), use an extra-diffused shadow: `box-shadow: 0 12px 40px rgba(25, 28, 32, 0.06)`. Note the low opacity and the use of the `on-surface` color for the shadow tint, mimicking natural light.
*   **The "Ghost Border" Fallback:** If a border is required for high-contrast accessibility requirements, use the `outline-variant` token at **20% opacity**. It should be a suggestion of a line, not a hard edge.

---

## 5. Components

### Buttons
- **Primary:** Full rounded (`9999px`). Background: `primary` to `primary-container` gradient. Text: `on-primary` (#ffffff).
- **Secondary:** Full rounded. Background: `secondary-container`. Text: `on-secondary-container`. No border.
- **Tertiary (Success):** Use for "Lesson Complete" or "Submit." Background: `tertiary`. Text: `on-tertiary`.

### Input Fields
- Avoid the "box" look. Use a `surface-container-high` fill with a `sm` (0.25rem) corner radius. 
- On focus, transition the background to `surface-container-lowest` and add a 2px `ghost border` using the `primary` color.

### Cards & Progress
- **Cards:** Strictly no dividers. Use vertical white space (calculated via the spacing scale) to separate the title from the body.
- **Progress Bars:** Use `tertiary-fixed` as the track and `tertiary` as the indicator. This "Success Green" provides positive reinforcement.

### Custom Component: The "Learning Focus" Pane
A large, `xl` (1.5rem) rounded container using `surface-container-lowest`. It should feature an asymmetrical layout: a wide column for the main content and a narrow, tinted `surface-container-low` column for supplementary AI hints.

---

## 6. Do’s and Don'ts

### Do:
- **Do** use `display-lg` typography to break up long sections of text.
- **Do** use `tertiary` (Green) accents for progress indicators to maintain an "encouraging" vibe.
- **Do** maximize the use of the `xl` (1.5rem) rounding for large containers to soften the professional aesthetic.

### Don't:
- **Don't** use black (#000000) for text. Always use `on-surface` (#191c20) to maintain a soft, premium contrast.
- **Don't** use 1px solid dividers to separate list items. Use an 8px vertical gap and a background shift on hover.
- **Don't** use standard "drop shadows." If it doesn't look like it's glowing or naturally resting, it’s too heavy.