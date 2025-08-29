# CDL Institute - Core Design System & Knowledge Base

## 1. Knowledge Base: What is CDL Institute?

*This section defines our brand identity, derived from our established marketing pages and content assets. It is the context for all design and copy decisions.*

*   **Core Mission:** CDL Institute is an official, FMCSA-approved (#CDL-2024-0892) training provider whose primary goal is to help students pass their CDL Knowledge Test on the first attempt, guaranteed.
*   **Key Differentiator:** We use an "assessment-driven" or "adaptive learning" approach. We start with a free diagnostic assessment to identify a student's specific knowledge gaps, then create a personalized study path. This is a smarter, faster way to pass compared to traditional methods.
*   **Target Audience:** Aspiring CDL drivers who are likely anxious about the test, value their time, and are looking for a reliable, modern, and guaranteed path to success.
*   **Brand Voice:** Confident, reassuring, expert, and results-oriented. We speak directly to the user's goals ("Pass Your CDL Test") and fears ("No questions. No stress. No pressure.").
*   **Value Proposition (Freemium Model):**
    *   **Free Tier:** A "Free Diagnostic Assessment" which provides a personalized study plan, a "Readiness Score," and access to basic practice questions. This is our primary lead magnet.
    *   **Paid Tier ("Complete ELDT + Exam Prep"):** A one-time payment ($147) for the complete program, which includes official ELDT certification, all endorsements, 1,200+ questions, and the "Ultimate Pass Guarantee."
*   **The Pass Guarantee:** If a student completes the full program and fails, we provide a 100% refund AND pay for their retest. This is our strongest risk-reversal claim.

### **Course Curriculum (Derived from `CDL_Content_Assets.csv`)**

Our curriculum is structured into core knowledge areas and specialized endorsements, ensuring comprehensive coverage for all CDL classes.

*   **Core Knowledge Areas (The Foundation):**
    *   **General Knowledge:** The mandatory foundation for all CDL classes, covering safety, rules of the road, and basic vehicle control.
    *   **Combination Vehicles:** Essential for Class A drivers. Covers coupling, uncoupling, and maneuvering tractor-trailers.
    *   **Air Brakes:** A critical component covering the operation, inspection, and maintenance of air brake systems.
    *   **Pre-Trip Inspection:** A detailed, step-by-step guide to the vehicle inspection process required to stay compliant and safe.
    *   **Hours of Service (HOS):** Covers ELD rules, driving limits, and rest requirements to avoid violations.

*   **Specialized Endorsements (For Higher-Paying Jobs):**
    *   **HazMat (H):** For transporting hazardous materials.
    *   **Tanker (N):** For hauling liquids and managing surge.
    *   **Passenger (P):** For operating vehicles that transport people, like buses.
    *   **Doubles/Triples (T):** For pulling multiple trailers.
    *   **School Bus (S):** Specialized training for the safe transport of children.

---

## 2. Development Philosophy: Build on Tailwind

*   **Utility-First is Law:** Always use Tailwind's utility classes directly in the HTML.
*   **Avoid Custom CSS:** Only use custom CSS for things impossible to achieve with Tailwind utilities (e.g., the scrollbar-hiding style `[scrollbar-width:none]`).
*   **Configuration over Customization:** If a new style is needed, add it to the `tailwind.config.js` file first. The `brand.blue` color is a perfect example of this.

---

## 3. Page Structure & Layout

### Header
*   **Theme:** Dark, semi-transparent, "glassmorphism" effect.
*   **Background:** Black with opacity and a backdrop blur.
*   **Tailwind Implementation:** `sticky top-0 z-50 bg-black/90 backdrop-blur-sm`.
*   **Height & Icon Size (Strict Rule):**
    *   The header navigation bar must have a **consistent height of 64px (`h-16`)** across all pages and screen sizes.
    *   The brand logo icon within the header must have a **consistent size of 36px by 36px (`h-9 w-9`)**. This ensures brand consistency at every touchpoint.

### Main Content Area
*   **Theme:** Light.
*   **Default Background:** White (`bg-white`).
*   **Sectional Background:** Light Gray (`bg-zinc-50`) is used to create visual separation between some sections.

### Footer
*   **Theme:** Dark.
*   **Background:** A very dark gray, Zinc 950 (`bg-zinc-950`).

---

## 4. Color Palette

| Role                   | Color Name      | Hex Code  | Tailwind Class      |
| ---------------------- | --------------- | --------- | ------------------- |
| **Primary Brand**      | Brand Blue      | `#1E66FF` | `bg-brand-blue`     |
| **Header/Footer BG**   | Black / Zinc 950| `#000` / `#09090b` | `bg-black` / `bg-zinc-950` |
| **Main Content BG**    | White           | `#ffffff` | `bg-white`          |
| **Section BG**         | Zinc 50         | `#fafafa` | `bg-zinc-50`        |
| **Card/Surface BG**    | White           | `#ffffff` | `bg-white`          |
| **Text (on Light BG)** | Zinc 900        | `#18181b` | `text-zinc-900`     |
| **Text (on Dark BG)**  | White           | `#ffffff` | `text-white`        |
| **Text Secondary**     | Zinc 600        | `#52525b` | `text-zinc-600`     |
| **Borders**            | Zinc 200        | `#e4e4e7` | `border-zinc-200`   |
| **Success**            | Green 500/600   | `#22c55e` | `text-green-500`    |

---

## 5. Typography

*   **Font Family:** `Inter` is the intended primary font, with `system-ui` fallbacks.
*   **Hero Headline (H1):** `text-3xl` up to `md:text-5xl`, `font-extrabold`, `tracking-tight`.
*   **Section Headlines (H2):** `text-3xl` up to `md:text-4xl`, `font-bold`, `tracking-tight`.
*   **Card/Item Titles (H3):** `font-semibold`.
*   **Body Text:** `text-zinc-600` or `text-zinc-300` (on dark backgrounds).

---

## 6. Components

### Buttons
*   **Primary CTA:**
    *   **Style:** `rounded-lg bg-brand-blue text-white font-semibold`.
    *   **Hover:** `hover:bg-blue-600`.
    *   **Iconography:** Often includes a right arrow icon (`ri-arrow-right-line`).

*   **Secondary/Dark CTA:**
    *   **Style:** `bg-zinc-900 text-white font-semibold rounded-lg`.
    *   **Hover:** `hover:bg-zinc-800`.

### Cards
*   **Standard Card:** `bg-white p-5 rounded-xl border border-zinc-200`.
*   **Pricing Card:** Similar to standard but with a `border-2` and a `shadow-xl` for the "Most Popular" option. The popular option also has a colored border (`border-brand-blue`).

### FAQ / Details Element
*   **Structure:** Uses the `<details>` and `<summary>` HTML elements.
*   **Style:** `bg-zinc-50 border border-zinc-200 rounded-xl p-6`.
*   **Icon:** An animated plus icon (`ri-add-line`) that rotates on open (`group-open:rotate-45`).

---

## 7. Animation & Motion

*   **Reveal Animation:** A gentle fade-in and upward slide is the standard for all content sections.
*   **Implementation:** A `reveal` class with an `in` class added by JavaScript when the element is in view.
*   **CSS:** `opacity: 0; transform: translateY(8px); transition: opacity .6s ease, transform .6s ease;`
*   **Accessibility:** Must respect `prefers-reduced-motion`.

---

## 8. Iconography

*   **Library:** **Remix Icon** is the exclusive icon library.
*   **Usage:** Icons are used extensively to add visual interest and context to feature lists, cards, and buttons. Both "Line" and "Fill" styles are used.
*   **Sizing:** Default icon size is `text-2xl` (`1.5rem`) within components, unless otherwise specified (e.g., header icon).

