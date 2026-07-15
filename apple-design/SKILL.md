---

name: apple-ui-design
description: >
Design, implement, review, and refine Apple-inspired web, desktop, and mobile
interfaces. Use for Apple-style minimal UI, macOS/iOS visual language,
translucent materials, fluid motion, premium landing pages, dashboards,
settings panels, scientific software, and polished product interfaces.
----------------------------------------------------------------------

# Apple UI Design Skill

## Goal

Create interfaces that feel calm, precise, premium, coherent, and native.

Do not merely copy Apple colors, blur effects, or rounded rectangles. Reproduce the deeper qualities of Apple interface design:

* strong visual hierarchy
* restrained decoration
* generous whitespace
* clear typography
* spatial consistency
* direct manipulation
* immediate feedback
* fluid, interruptible motion
* progressive disclosure
* accessibility by default

The result should feel designed, not generated.

---

# 1. Working Process

For every UI task, follow this sequence.

## Step 1: Understand the product

Determine:

* target platform: web, macOS, iOS, iPadOS, or responsive
* main user goal
* primary action
* information hierarchy
* expected content density
* light mode, dark mode, or both
* existing framework and component library
* whether the request means Apple-inspired or truly native Apple UI

Do not start coding before identifying the primary user flow.

## Step 2: Inspect the existing project

Before modifying code:

* inspect the repository structure
* identify the framework
* identify existing components
* inspect current typography, spacing, colors, and tokens
* reuse existing dependencies where appropriate
* avoid replacing the entire architecture unnecessarily

Preserve functional behavior unless the user explicitly asks for structural changes.

## Step 3: Establish a design direction

Summarize internally:

* visual character
* layout structure
* typography hierarchy
* surface hierarchy
* interaction model
* motion language

Use one coherent direction. Do not mix Apple, Material Design, cyberpunk, glassmorphism, and generic dashboard styles.

## Step 4: Implement

Build the complete interface, not an isolated visual mockup.

Include:

* responsive layout
* empty states
* loading states
* hover, focus, pressed, selected, disabled states
* keyboard interaction
* reduced-motion handling
* light/dark appearance where relevant

## Step 5: Review

Before finishing, inspect:

* alignment
* spacing rhythm
* contrast
* typography hierarchy
* component consistency
* interaction feedback
* responsive behavior
* accessibility
* unnecessary visual effects
* generic AI-generated patterns

Refine until the interface looks intentional.

---

# 2. Core Design Principles

## Clarity

Every screen must have an obvious purpose.

The user should quickly understand:

* where they are
* what information matters
* what they can do next
* what changed after an action

Use visual hierarchy rather than excessive labels and borders.

## Deference

Content is more important than decoration.

Navigation, controls, backgrounds, and effects should support the content rather than compete with it.

## Depth

Use layering, motion, scale, translucency, and shadows to communicate relationships.

Depth must explain structure. It must not exist only for decoration.

## Restraint

Prefer fewer, stronger decisions.

Avoid:

* too many cards
* excessive gradients
* excessive blur
* decorative glows
* oversized headings everywhere
* unnecessary badges
* excessive borders
* multiple competing accent colors
* animations on every element

## Consistency

Similar elements must behave similarly.

Use consistent:

* spacing
* corner radii
* control heights
* icon style
* typography
* transitions
* surface treatment

---

# 3. Layout System

## Page structure

Prefer clear spatial zones:

1. navigation
2. page title or contextual toolbar
3. primary content
4. secondary details
5. persistent actions only when necessary

Do not put every section inside a separate card.

Use cards only when the content represents a meaningful object, group, or interactive unit.

## Content width

For reading-focused pages:

```css
max-width: 720px;
```

For product dashboards and editors:

```css
max-width: 1200px;
```

For immersive tools:

```css
width: 100%;
```

Allow content to breathe. Do not stretch text paragraphs across very wide screens.

## Spacing scale

Use a consistent 4-point or 8-point spacing system.

Recommended scale:

```text
4, 8, 12, 16, 20, 24, 32, 40, 48, 64, 80, 96
```

Typical usage:

```text
4–8 px     icon/text adjustment
8–12 px    compact internal spacing
12–16 px   control spacing
16–24 px   card padding
24–32 px   section spacing
40–64 px   major content separation
64–96 px   page-level breathing room
```

Avoid arbitrary values unless alignment requires optical correction.

## Alignment

Use strong shared alignment lines.

Prefer:

* aligned text baselines
* consistent left edges
* balanced optical centering
* even vertical rhythm
* logical grouping through proximity

Do not center all content by default.

---

# 4. Typography

## Font stack

For web interfaces, use:

```css
font-family:
  -apple-system,
  BlinkMacSystemFont,
  "SF Pro Display",
  "SF Pro Text",
  "Helvetica Neue",
  Arial,
  sans-serif;
```

Do not bundle or distribute Apple proprietary font files.

Use the system font stack so Apple devices render the native system typeface.

## Typography hierarchy

Suggested scale:

```text
Large display: 48–72 px
Page title:    32–44 px
Section title: 22–28 px
Card title:    17–20 px
Body:          15–17 px
Secondary:     13–15 px
Caption:       11–13 px
```

Use smaller sizes for dense desktop tools and larger sizes for marketing pages.

## Weight

Prefer:

```text
400 regular
500 medium
600 semibold
700 bold, used sparingly
```

Avoid making all headings heavy.

## Line height

Recommended:

```text
Display: 1.05–1.15
Heading: 1.15–1.3
Body:    1.45–1.65
Caption: 1.3–1.5
```

## Tracking

Large headings may use slightly tighter tracking:

```css
letter-spacing: -0.02em;
```

Small uppercase labels may use slightly wider tracking, but avoid overusing uppercase text.

## Text color

Use hierarchy through opacity rather than many unrelated gray values.

Example:

```css
--text-primary: rgba(0, 0, 0, 0.88);
--text-secondary: rgba(0, 0, 0, 0.58);
--text-tertiary: rgba(0, 0, 0, 0.38);
```

Dark mode:

```css
--text-primary: rgba(255, 255, 255, 0.92);
--text-secondary: rgba(255, 255, 255, 0.62);
--text-tertiary: rgba(255, 255, 255, 0.40);
```

Ensure accessible contrast for essential content.

---

# 5. Color System

## Base palette

Start with neutral surfaces.

Light mode example:

```css
:root {
  --background: #f5f5f7;
  --surface: rgba(255, 255, 255, 0.72);
  --surface-solid: #ffffff;
  --surface-elevated: rgba(255, 255, 255, 0.88);

  --text-primary: rgba(0, 0, 0, 0.88);
  --text-secondary: rgba(0, 0, 0, 0.58);
  --text-tertiary: rgba(0, 0, 0, 0.38);

  --separator: rgba(0, 0, 0, 0.10);
  --border-subtle: rgba(0, 0, 0, 0.08);

  --accent: #0071e3;
  --accent-hover: #0077ed;
}
```

Dark mode example:

```css
@media (prefers-color-scheme: dark) {
  :root {
    --background: #000000;
    --surface: rgba(28, 28, 30, 0.72);
    --surface-solid: #1c1c1e;
    --surface-elevated: rgba(44, 44, 46, 0.88);

    --text-primary: rgba(255, 255, 255, 0.92);
    --text-secondary: rgba(255, 255, 255, 0.62);
    --text-tertiary: rgba(255, 255, 255, 0.40);

    --separator: rgba(255, 255, 255, 0.14);
    --border-subtle: rgba(255, 255, 255, 0.10);

    --accent: #0a84ff;
    --accent-hover: #409cff;
  }
}
```

## Accent color

Use one primary accent color.

Accent color should indicate:

* primary actions
* links
* selected state
* active controls
* progress

Do not color every icon and heading.

## Semantic colors

Use semantic colors only when they communicate meaning:

```text
blue    action or selection
green   success
orange  warning
red     destructive action or error
gray    inactive or secondary
```

Never rely on color alone. Pair color with text, shape, icon, or state change.

---

# 6. Surfaces and Materials

## Solid surfaces

Use solid surfaces for:

* dense data tables
* forms
* reading content
* high-contrast information
* accessibility-critical content

## Translucent surfaces

Use translucency for:

* toolbars
* floating controls
* sidebars
* overlays
* navigation bars
* sheets
* temporary contextual layers

Example:

```css
.glass-surface {
  background: rgba(255, 255, 255, 0.68);
  backdrop-filter: saturate(180%) blur(20px);
  -webkit-backdrop-filter: saturate(180%) blur(20px);
  border: 1px solid rgba(255, 255, 255, 0.28);
}
```

Dark mode:

```css
.glass-surface {
  background: rgba(30, 30, 32, 0.68);
  border-color: rgba(255, 255, 255, 0.10);
}
```

Provide a fallback background when `backdrop-filter` is unsupported.

## Glass usage rules

Do not:

* make every card glass
* put translucent text over noisy images
* stack many blurred layers
* use blur without meaningful depth
* reduce contrast for aesthetic reasons

Glass is a material, not a theme.

## Corner radius

Recommended scale:

```text
6 px   compact controls
8 px   small buttons and inputs
10 px  standard controls
12 px  compact cards
16 px  standard cards
20 px  prominent panels
24 px  large feature surfaces
999 px capsules and circular controls
```

Use fewer radius values per interface.

## Borders

Prefer subtle separators rather than strong outlines.

Example:

```css
border: 1px solid rgba(0, 0, 0, 0.08);
```

Do not add borders around every element.

## Shadows

Use soft, low-opacity shadows.

```css
box-shadow:
  0 1px 2px rgba(0, 0, 0, 0.04),
  0 8px 24px rgba(0, 0, 0, 0.08);
```

Floating overlay:

```css
box-shadow:
  0 12px 40px rgba(0, 0, 0, 0.16),
  0 2px 8px rgba(0, 0, 0, 0.08);
```

Avoid strong black shadows and glowing outlines.

---

# 7. Controls

## Buttons

Primary button:

```css
.button-primary {
  min-height: 44px;
  padding: 0 20px;
  border: 0;
  border-radius: 999px;
  background: var(--accent);
  color: white;
  font-weight: 600;
}
```

Secondary button:

```css
.button-secondary {
  min-height: 44px;
  padding: 0 20px;
  border-radius: 999px;
  background: rgba(120, 120, 128, 0.12);
  color: var(--text-primary);
}
```

Use rectangular rounded buttons for toolbars and dense desktop interfaces when capsules consume too much space.

Every interactive control needs:

* default
* hover
* pressed
* focus-visible
* disabled
* loading, when applicable

Pressed states should usually combine slight opacity, brightness, or scale changes.

## Inputs

Inputs should:

* have clear labels
* retain visible focus
* provide validation feedback
* avoid placeholder-only labels
* use consistent heights
* avoid excessive borders

Example:

```css
.input {
  min-height: 44px;
  padding: 0 14px;
  border-radius: 10px;
  border: 1px solid var(--border-subtle);
  background: var(--surface-solid);
}
```

Focus:

```css
.input:focus-visible {
  outline: 3px solid color-mix(in srgb, var(--accent) 30%, transparent);
  border-color: var(--accent);
}
```

## Toggles

Use toggles for immediate binary settings.

Do not use a toggle when the action requires confirmation or triggers a large irreversible operation.

## Segmented controls

Use segmented controls for a small set of mutually exclusive views.

Keep labels short. Avoid more than approximately five segments.

## Menus

Menus should:

* be aligned to their trigger
* use clear grouping
* support keyboard navigation
* distinguish destructive actions
* close predictably
* avoid overly wide layouts

---

# 8. Navigation

## Sidebars

Use a sidebar when the product has several stable top-level destinations.

Sidebar guidance:

* 220–280 px on desktop
* clear selected state
* restrained icons
* logical grouping
* optional collapse behavior
* preserve content priority

Avoid excessive nested navigation.

## Top bars

Use top bars for:

* page context
* search
* global actions
* window-level controls
* compact navigation

Keep the number of visible actions small.

## Tabs

Use tabs for peer-level content within one context.

Do not use tabs as decorative headings.

## Breadcrumbs

Use breadcrumbs only for genuinely hierarchical information.

Do not add breadcrumbs to shallow applications.

---

# 9. Cards and Data Presentation

## Cards

A card should represent a meaningful unit.

Good uses:

* project
* dataset
* document
* experiment
* device
* result summary
* actionable notification

Poor uses:

* every paragraph
* every setting row
* every chart
* every navigation item
* arbitrary whitespace grouping

## Tables

For scientific or professional software:

* prioritize scanability
* align numeric values by decimal or right edge
* keep headers visible when scrolling
* support sorting and filtering when needed
* use subtle row separators
* avoid excessive zebra striping
* provide selected and hover states
* allow horizontal scrolling on small screens

Do not force dense datasets into oversized cards.

## Charts

Charts should use:

* clear labels
* restrained palettes
* readable axes
* meaningful tooltips
* consistent legends
* sufficient contrast
* no decorative 3D effects unless scientifically necessary

The interface should not imitate Apple marketing at the cost of scientific readability.

---

# 10. Motion

## Motion purpose

Animation must communicate:

* continuity
* state change
* hierarchy
* causality
* direct manipulation
* feedback

Do not animate merely because animation is possible.

## Timing

Suggested durations:

```text
80–120 ms    button feedback
140–200 ms   hover and small state change
200–300 ms   panels and menus
300–450 ms   sheets and larger spatial transitions
```

## Easing

For standard UI transitions:

```css
cubic-bezier(0.22, 1, 0.36, 1)
```

For entering elements:

```css
cubic-bezier(0.16, 1, 0.3, 1)
```

For exiting elements:

```css
cubic-bezier(0.4, 0, 1, 1)
```

Use spring motion for:

* draggable objects
* sheets
* cards returning to position
* gesture-driven interactions
* playful but controlled feedback

## Interruptibility

Longer animations must be interruptible.

User input should take priority over an animation already in progress.

## Reduced motion

Always support:

```css
@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    scroll-behavior: auto !important;
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}
```

Do not remove essential state feedback.

---

# 11. Icons and Imagery

## Icons

Prefer:

* one consistent icon family
* simple silhouettes
* optical alignment
* consistent stroke weight
* clear active and inactive states

For web projects, use the icon library already installed in the repository.

Do not use emoji as primary interface icons unless explicitly requested.

Avoid mixing filled, outlined, hand-drawn, and multicolor icons.

## Images

Use imagery only when it supports:

* product understanding
* content hierarchy
* emotional tone
* demonstration
* identity

Do not add random stock illustrations to fill empty space.

---

# 12. Responsive Design

## Mobile

On small screens:

* use one primary column
* maintain touch targets of at least approximately 44 × 44 px
* collapse secondary navigation
* move low-priority actions into menus
* avoid tiny desktop-style controls
* keep primary actions reachable
* prevent horizontal page overflow

## Tablet

Use tablet width for:

* split views
* sidebars
* flexible inspector panels
* larger touch targets
* responsive content grids

## Desktop

Desktop UI may be denser, but must remain calm and legible.

Support:

* keyboard shortcuts
* hover states
* context menus when useful
* resizable regions where appropriate
* efficient multi-column workflows

Do not turn a desktop tool into an enlarged mobile app.

---

# 13. Accessibility

Accessibility is mandatory.

Ensure:

* semantic HTML
* keyboard navigation
* visible focus states
* sufficient contrast
* accessible names
* meaningful labels
* logical heading structure
* reduced-motion support
* screen-reader announcements for important dynamic updates
* touch targets large enough for reliable interaction
* color-independent status communication

Use native controls where possible.

Do not replace accessible native behavior with visually attractive but incomplete custom controls.

---

# 14. Apple-Inspired Web Design

When creating an Apple-inspired website, capture these characteristics:

* confident typography
* highly focused messaging
* generous spacing
* simple navigation
* premium imagery
* smooth scroll-linked storytelling used sparingly
* restrained color
* clear product hierarchy
* subtle material depth
* precise motion

Do not clone Apple pages exactly.

Avoid:

* copying Apple trademarks
* copying product imagery
* copying proprietary assets
* copying page text
* pretending a product is affiliated with Apple
* reproducing the Apple website pixel-for-pixel

Create an original design that uses similar design principles.

---

# 15. Native Apple Interfaces

When implementing SwiftUI or Apple-platform UI:

* prefer native SwiftUI components
* use platform-standard navigation
* respect safe areas
* support Dynamic Type
* use semantic system colors
* support light and dark mode
* use native materials
* use native sheets, alerts, menus, toolbars, and controls
* avoid rebuilding standard controls without strong reason
* preserve platform conventions
* verify API availability for the deployment target

For newer Liquid Glass APIs, only use APIs supported by the project's deployment target.

Do not invent Apple APIs.

---

# 16. Scientific and Research Software

For scientific applications, combine Apple-style polish with technical clarity.

Prioritize:

* data visibility
* accurate labels
* reproducible controls
* obvious parameter state
* clear file and experiment context
* readable plots
* dense but orderly layouts
* non-destructive workflows
* progress feedback
* error recovery
* export visibility

Recommended structure:

```text
Sidebar
  datasets
  experiments
  models
  history

Main workspace
  spectrum, image, table, or editor

Inspector panel
  parameters
  metadata
  preprocessing
  model configuration

Bottom/status area
  progress
  device status
  logs
  warnings
```

Use Apple visual principles without hiding important scientific details behind excessive minimalism.

---

# 17. Anti-Patterns

Reject the following unless the user explicitly asks for them:

* purple-blue gradient backgrounds
* neon glow
* excessive glassmorphism
* floating cards everywhere
* random blobs
* giant hero text in application screens
* excessive pill-shaped controls
* icons inside every heading
* multiple accent colors
* excessive animation
* tiny gray text
* low-contrast controls
* meaningless metrics
* placeholder charts
* generic SaaS dashboards
* endless rounded rectangles
* excessive shadows
* decorative 3D objects
* emojis used as interface icons
* gradients applied to all buttons
* hidden essential actions
* replacing tables with cards for no reason

Avoid the recognizable default “AI-generated UI” appearance.

---

# 18. Code Quality

Generated code must be:

* complete
* runnable
* responsive
* accessible
* maintainable
* consistent with the existing project
* free of unnecessary dependencies
* separated into logical components
* based on reusable design tokens
* free of placeholder TODO sections unless unavoidable

Do not output only a visual description when implementation is requested.

Do not rewrite working business logic unnecessarily.

Do not introduce a new framework unless the task requires it.

---

# 19. Design Tokens

Prefer reusable tokens.

Example:

```css
:root {
  --space-1: 4px;
  --space-2: 8px;
  --space-3: 12px;
  --space-4: 16px;
  --space-5: 20px;
  --space-6: 24px;
  --space-8: 32px;
  --space-10: 40px;
  --space-12: 48px;
  --space-16: 64px;

  --radius-sm: 8px;
  --radius-md: 12px;
  --radius-lg: 16px;
  --radius-xl: 24px;
  --radius-pill: 999px;

  --control-height-sm: 32px;
  --control-height-md: 40px;
  --control-height-lg: 44px;

  --duration-fast: 120ms;
  --duration-normal: 220ms;
  --duration-slow: 360ms;

  --ease-standard: cubic-bezier(0.22, 1, 0.36, 1);
}
```

Use project-specific tokens if they already exist.

---

# 20. Final Review Checklist

Before completing any Apple-style UI task, verify:

## Product

* Is the primary user goal obvious?
* Is the main action visually clear?
* Is unnecessary content removed?

## Layout

* Are alignment and spacing consistent?
* Is whitespace intentional?
* Are cards used only where appropriate?
* Does the layout work at mobile and desktop widths?

## Typography

* Is the hierarchy obvious?
* Is body text readable?
* Are heading weights restrained?
* Are line lengths reasonable?

## Surfaces

* Is translucency used selectively?
* Is contrast sufficient?
* Are shadows subtle?
* Are corner radii consistent?

## Interaction

* Do controls have hover, pressed, focus, disabled, and loading states?
* Is keyboard navigation supported?
* Is feedback immediate?
* Are animations purposeful and interruptible?

## Accessibility

* Are semantic elements used?
* Are focus states visible?
* Is reduced motion supported?
* Is important meaning independent of color?

## Quality

* Does it avoid generic AI dashboard styling?
* Does it feel coherent rather than decorative?
* Is the code complete and runnable?
* Does it preserve existing project functionality?

---

# 21. Response Behavior

When asked to create or redesign an interface:

1. inspect the existing project
2. identify the primary workflow
3. choose one coherent design direction
4. implement the interface
5. run or build the project when possible
6. inspect the rendered result
7. correct obvious design and interaction issues
8. summarize only the important changes

Do not provide multiple weak alternatives when one strong solution is possible.

Do not stop after writing a plan when implementation is requested.

Do not claim the interface is polished without reviewing the rendered result.
