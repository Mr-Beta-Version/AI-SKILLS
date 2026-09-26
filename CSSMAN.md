# CSSMAN

## Purpose

CSSMAN is a CSS cleanup and refinement skill for transforming AI-generated or over-designed CSS into clean, intentional, human-designed CSS.

The goal is **not** to redesign the entire application.

The goal is to:

* Remove unnecessary visual effects
* Reduce repetitive AI-style patterns
* Improve visual hierarchy
* Simplify CSS
* Preserve existing functionality
* Preserve the project's brand identity
* Make components feel intentionally designed rather than generated from a template
* Keep the code maintainable and predictable

CSSMAN works with any project:

* Django
* React
* Next.js
* Vue
* Laravel
* PHP
* Static HTML
* Tailwind-generated CSS
* Bootstrap-based projects
* Plain CSS
* SCSS
* Component CSS
* Dashboard applications
* SaaS applications
* Enterprise applications

---

# Core Principle

> Human-designed CSS is usually driven by hierarchy, context, and purpose. AI-generated CSS often applies the same visual treatment everywhere.

CSSMAN must therefore prefer:

**Purpose over decoration.**

**Hierarchy over uniformity.**

**Consistency over repetition.**

**Clarity over visual complexity.**

**Real UI requirements over generic design trends.**

---

# Operating Rules

## 1. Read Before Changing

Never blindly rewrite a CSS file.

First inspect:

* Existing variables
* Color system
* Typography
* Spacing
* Border radius
* Shadows
* Gradients
* Filters
* Animations
* Responsive rules
* Component structure
* Naming conventions
* Existing utility classes
* Existing design system

Determine what the project is already trying to accomplish.

Do not impose a new design system unless the existing system is clearly broken.

---

# 2. Preserve Functionality

CSSMAN must not break:

* Layout
* Responsive behavior
* Modals
* Dropdowns
* Forms
* Tables
* Navigation
* Buttons
* Cards
* JavaScript-dependent states
* Hover states
* Focus states
* Active states
* Hidden/visible states
* Accessibility behavior

Do not change class names or selectors unnecessarily.

Do not remove CSS merely because it looks unusual.

Every removal must have a reason.

---

# 3. Detect AI-Style CSS Patterns

Look specifically for these patterns.

## Excessive Border Radius

Common AI pattern:

```css
border-radius: 24px;
border-radius: 28px;
border-radius: 32px;
border-radius: 9999px;
```

Do not automatically remove rounded corners.

Instead establish a sensible scale.

Typical business UI:

```css
4px
6px
8px
10px
12px
```

Use `50%` only when a circular shape is intentional:

* Avatar
* Status dot
* Circular icon button
* Circular progress indicator

Do not use `50%` as a generic component radius.

---

# 4. Remove Unnecessary Glassmorphism

Identify:

```css
backdrop-filter
-webkit-backdrop-filter
```

especially:

```css
backdrop-filter: blur(...);
```

Also identify:

```css
background: rgba(...);
```

combined with:

```css
border: 1px solid rgba(...);
box-shadow: ...;
backdrop-filter: blur(...);
```

This combination frequently creates unnecessary glassmorphism.

Replace it with solid surfaces when transparency does not serve a functional purpose.

Prefer:

```css
background: #ffffff;
border: 1px solid #e5e7eb;
```

over:

```css
background: rgba(255, 255, 255, 0.62);
backdrop-filter: blur(20px);
border: 1px solid rgba(255, 255, 255, 0.75);
```

Do not remove transparency when it is required for:

* Overlay effects
* Modal backdrops
* Intentional layering
* Image overlays
* Navigation overlays

---

# 5. Reduce Excessive Shadows

Detect exaggerated shadows such as:

```css
box-shadow: 0 20px 60px rgba(...);
box-shadow: 0 30px 80px rgba(...);
box-shadow: 0 16px 40px rgba(...);
```

Prefer restrained elevation.

Example:

```css
box-shadow: 0 2px 8px rgba(0, 0, 0, 0.08);
```

or:

```css
box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
```

Do not add shadows to every element.

Use shadows primarily for:

* Modal
* Dropdown
* Popover
* Floating panel
* Elevated surface

Cards do not automatically need shadows.

---

# 6. Reduce Gradient Abuse

Detect unnecessary:

```css
linear-gradient(...)
radial-gradient(...)
conic-gradient(...)
```

Do not remove gradients that are part of the brand.

Remove gradients when they exist only for decoration.

AI-style:

```css
background:
  radial-gradient(circle at top left, ...),
  linear-gradient(135deg, ...);
```

Human-oriented alternative:

```css
background: #ffffff;
```

Use gradients deliberately, not as default backgrounds.

---

# 7. Remove Glow Effects

Detect:

```css
filter: drop-shadow(...);
text-shadow: ...;
box-shadow: 0 0 ... rgba(...);
```

especially when the purpose is creating a colored glow.

Examples:

```css
--mint-glow
--green-glow
--blue-glow
--gold-glow
--purple-glow
```

Do not automatically delete variables.

First determine whether they are actually used.

Remove decorative glow when it has no semantic purpose.

---

# 8. Simplify Animations

AI-generated interfaces frequently animate everything.

Look for:

```css
transition: all ...
```

and excessive:

```css
transform
scale()
translateY()
rotate()
pulse
float
glow
```

Do not remove useful interaction feedback.

Prefer targeted transitions:

```css
transition:
  background-color 0.15s ease,
  border-color 0.15s ease,
  color 0.15s ease;
```

Avoid:

```css
transition: all 0.3s ease;
```

unless there is a specific reason.

Do not animate ordinary content unnecessarily.

---

# 9. Avoid Excessive Hover Movement

AI-generated interfaces often use:

```css
.card:hover {
  transform: translateY(-6px);
}
```

or:

```css
button:hover {
  transform: scale(1.05);
}
```

Do not use movement merely to make the UI feel interactive.

For business applications, prefer subtle changes:

```css
button:hover {
  background: var(--green-dark);
}
```

or:

```css
.card:hover {
  border-color: var(--green-line);
}
```

Use movement only when it improves interaction feedback.

---

# 10. Fix Excessive Card Usage

Do not make every section look like a card.

AI pattern:

```text
Card
  Card
    Card
      Card
```

Evaluate whether the information can exist as:

* Table
* List
* Section
* Divider
* Inline information
* Plain container

Cards should communicate grouping.

They should not simply surround every element.

---

# 11. Establish Visual Hierarchy

CSSMAN should identify:

### Primary

Examples:

```css
font-weight: 700;
```

```css
background: var(--brand);
```

### Secondary

Examples:

```css
font-weight: 500;
color: var(--muted);
```

### Supporting

Examples:

```css
font-size: 0.875rem;
color: var(--muted);
```

Not every heading should be:

```css
font-weight: 800;
```

Not every element should have strong contrast.

---

# 12. Normalize Spacing

Detect random spacing such as:

```css
13px
17px
19px
23px
27px
31px
37px
```

Do not blindly convert every value.

Where appropriate, establish a predictable spacing scale:

```text
4px
8px
12px
16px
20px
24px
32px
40px
48px
```

Use spacing according to hierarchy.

Example:

```text
Label → 8px → Input

Input → 16px → Next field

Section → 24px → Section

Major section → 40px/48px → Major section
```

---

# 13. Do Not Make Everything Symmetrical

AI-generated interfaces often have:

```text
Everything centered
Everything equal width
Everything equal spacing
Everything same radius
Everything same shadow
```

Human interfaces often use hierarchy.

Do not force symmetry when the content does not require it.

For example:

```css
.page-header {
  display: flex;
  justify-content: space-between;
}
```

may be more appropriate than centering everything.

---

# 14. Typography

Avoid excessive font weights.

Bad:

```css
font-weight: 900;
```

everywhere.

Prefer:

```text
400 → body
500 → labels
600 → important UI
700 → headings
```

Do not introduce a new font unless there is a clear reason.

Respect existing project fonts.

If the project already uses a typography system, preserve it.

---

# 15. Color Discipline

Do not introduce random colors.

Identify the existing:

* Primary
* Secondary
* Background
* Surface
* Border
* Text
* Muted
* Success
* Warning
* Error
* Info

Use semantic colors consistently.

Avoid unnecessary color variables such as:

```css
--green-glow
--green-soft-2
--green-light-alt
--green-gradient-start
--green-gradient-end
```

when they represent nearly identical colors.

Consolidate duplicates when safe.

---

# 16. Preserve Brand Identity

CSSMAN does not mean:

> Make everything gray and boring.

If the project has a green brand, keep the green.

If the project has a dark theme, preserve the dark theme.

If the project uses distinctive typography, preserve it.

The objective is:

```text
Existing Brand
      +
Less visual noise
      +
Better hierarchy
      +
Purposeful components
```

Not:

```text
Existing Brand
      ↓
Generic white website
```

---

# 17. Component-Specific Rules

## Buttons

Prefer:

```css
border-radius: 6px;
```

or:

```css
border-radius: 8px;
```

Avoid excessive:

```css
border-radius: 9999px;
```

unless the button is intentionally pill-shaped.

Do not use:

* Large glow
* Excessive gradients
* Large scale animations

Primary buttons should be visually stronger than secondary buttons.

---

## Inputs

Prefer clear borders:

```css
border: 1px solid var(--border);
background: #fff;
```

Focus state should be obvious:

```css
input:focus {
  border-color: var(--brand);
  outline: 2px solid rgba(22, 163, 74, 0.12);
}
```

Do not rely only on shadows to indicate focus.

---

## Cards

Default:

```css
background: #fff;
border: 1px solid var(--border);
border-radius: 8px;
```

Shadow should be optional.

Do not automatically use glass effects.

---

## Modals

Prefer:

```css
background: #fff;
border: 1px solid var(--border);
border-radius: 8px;
box-shadow: 0 8px 24px rgba(0, 0, 0, 0.12);
```

The backdrop may remain translucent.

The modal itself normally does not need:

```css
backdrop-filter: blur(...);
```

---

## Tables

Business applications should prioritize tables when data is tabular.

Do not convert table information into decorative cards.

Use:

* Clear column hierarchy
* Compact spacing
* Strong header distinction
* Row hover only when useful
* Status badges where semantic

---

## Navigation

Navigation should prioritize:

1. Current location
2. Primary workflow
3. Secondary navigation
4. Settings/utilities

Do not add decorative effects to every navigation item.

---

# 18. CSS Complexity Reduction

Look for:

* Duplicate declarations
* Duplicate selectors
* Dead styles
* Unused variables
* Repeated media queries
* Repeated colors
* Repeated shadows
* Repeated radius values
* Overly specific selectors
* Unnecessary `!important`
* Redundant vendor prefixes
* Repeated component styles

Simplify where safe.

Do not refactor the entire architecture merely for aesthetics.

---

# 19. Selector Quality

Prefer:

```css
.modal-title
```

over unnecessarily specific selectors:

```css
.page .content .container .modal .modal-content .modal-title
```

Avoid specificity wars.

Do not use:

```css
!important
```

unless necessary to override an external framework or unavoidable legacy rule.

---

# 20. Responsive CSS

Do not destroy existing responsive behavior.

Check:

* Mobile
* Tablet
* Desktop
* Large screens

Avoid arbitrary breakpoints.

Do not create separate desktop and mobile designs unless required.

Preserve existing responsive logic when it works.

---

# 21. Accessibility

Never sacrifice accessibility for visual simplicity.

Preserve:

* Visible focus
* Sufficient contrast
* Reduced motion support
* Keyboard interaction states
* Disabled states
* Error states

When animations are present, consider:

```css
@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    animation-duration: 0.01ms;
    animation-iteration-count: 1;
    transition-duration: 0.01ms;
  }
}
```

Only add this if it fits the project's existing architecture.

---

# 22. Do Not Over-Clean

CSSMAN must not turn every stylesheet into the same style.

Do not blindly enforce:

```text
8px radius
white background
gray border
no shadow
no animation
```

on every project.

The goal is intentional design.

A gaming website, medical dashboard, factory application, portfolio, e-commerce store, and SaaS product can legitimately have different visual systems.

CSSMAN adapts to the project's context.

---

# 23. Human Design Heuristics

When choosing between two visually valid implementations, evaluate:

### Purpose

Does the property communicate something?

### Hierarchy

Does it help users understand importance?

### Context

Does it fit this component?

### Consistency

Does it belong to the project's design system?

### Restraint

Would removing it make the UI clearer?

### Maintainability

Will another developer understand why it exists?

If the answer is no to most of these, simplify it.

---

# 24. Refactoring Priority

Apply changes in this order.

## Level 1 — Visual Noise

Remove:

* Excessive blur
* Excessive glow
* Excessive gradients
* Excessive shadows
* Excessive animations

## Level 2 — Repetition

Fix:

* Every component having identical radius
* Every component having identical shadow
* Every section being a card
* Every element using the same spacing

## Level 3 — Hierarchy

Fix:

* Heading sizes
* Button importance
* Content density
* Section spacing
* Muted text

## Level 4 — Code Quality

Fix:

* Duplicate rules
* Dead variables
* Repeated declarations
* Specificity problems
* Unnecessary `!important`

## Level 5 — Polish

Only after the above:

* Micro-interactions
* Hover states
* Animation timing
* Fine spacing
* Border details

Do not spend time polishing a fundamentally over-designed component.

---

# 25. Before/After Mental Model

## AI-heavy

```text
Gradient
   ↓
Glass card
   ↓
Blur
   ↓
Huge radius
   ↓
Huge shadow
   ↓
Glow
   ↓
Hover scale
```

## Human-oriented

```text
Purpose
   ↓
Hierarchy
   ↓
Spacing
   ↓
Typography
   ↓
Border
   ↓
Subtle elevation
   ↓
Minimal interaction feedback
```

---

# 26. Safe Refactoring Pattern

Before:

```css
.card {
  background: rgba(255, 255, 255, 0.62);
  backdrop-filter: blur(20px);
  border: 1px solid rgba(255, 255, 255, 0.75);
  border-radius: 24px;
  box-shadow:
    0 20px 60px rgba(13, 60, 34, 0.16),
    0 2px 6px rgba(13, 60, 34, 0.08);
  transition: all 0.3s ease;
}

.card:hover {
  transform: translateY(-6px);
  box-shadow:
    0 30px 80px rgba(13, 60, 34, 0.2);
}
```

After:

```css
.card {
  background: #ffffff;
  border: 1px solid var(--border);
  border-radius: 8px;
  transition: border-color 0.15s ease;
}

.card:hover {
  border-color: var(--brand);
}
```

Do not apply this transformation blindly.

It is an example of the decision-making pattern.

---

# 27. Variables

If the project has design tokens, preserve them.

Prefer semantic variables:

```css
:root {
  --brand: #16a34a;
  --brand-dark: #0b6b34;

  --text: #0f2018;
  --text-muted: #48604f;

  --surface: #ffffff;
  --surface-muted: #f8faf9;

  --border: #e3ede6;

  --radius-sm: 6px;
  --radius-md: 8px;

  --shadow-sm: 0 2px 8px rgba(0, 0, 0, 0.08);
  --shadow-md: 0 8px 24px rgba(0, 0, 0, 0.12);
}
```

Do not create tokens for every single value.

---

# 28. Output Requirements

When CSSMAN modifies a CSS file:

1. Preserve all required selectors.
2. Preserve functionality.
3. Preserve responsive behavior.
4. Preserve brand colors unless there is a clear reason to change them.
5. Remove unnecessary visual effects.
6. Reduce repeated patterns.
7. Simplify selectors where safe.
8. Remove genuinely unused declarations when confidently identifiable.
9. Keep formatting consistent with the existing project.
10. Do not add comments everywhere.
11. Do not rewrite unrelated CSS.
12. Do not introduce a new framework.
13. Do not introduce Tailwind, Bootstrap, or another library.
14. Do not change HTML/JS unless explicitly required.
15. Do not invent a design system without examining the existing one.

---

# 29. Final Verification

After editing, inspect the resulting CSS for:

```text
[ ] Broken selectors
[ ] Missing closing braces
[ ] Invalid declarations
[ ] Duplicate rules
[ ] Unnecessary !important
[ ] Broken responsive behavior
[ ] Excessive radius
[ ] Excessive shadows
[ ] Excessive gradients
[ ] Excessive blur
[ ] Excessive glow
[ ] Excessive animation
[ ] Inconsistent spacing
[ ] Inconsistent typography
[ ] Lost focus states
[ ] Lost hover states
[ ] Lost disabled states
```

CSSMAN must prioritize **working CSS over aesthetic purity**.

---

# 30. Definition of Done

A CSS file is considered cleaned when:

* The UI no longer relies on decoration to communicate quality.
* Components have clear visual hierarchy.
* Effects have identifiable purposes.
* Radius values are intentional.
* Shadows are restrained.
* Glassmorphism is not used by default.
* Gradients are purposeful.
* Animations communicate interaction rather than decoration.
* Spacing follows a recognizable system.
* Typography has hierarchy.
* Colors are semantically consistent.
* CSS contains less unnecessary repetition.
* Existing functionality remains intact.
* The result still belongs to the original project's brand.

The final result should look like a developer or designer made deliberate decisions for **this specific application**, rather than applying a generic AI design template.
# CSSMAN

## Purpose

CSSMAN is a CSS cleanup and refinement skill for transforming AI-generated or over-designed CSS into clean, intentional, human-designed CSS.

The goal is **not** to redesign the entire application.

The goal is to:

* Remove unnecessary visual effects
* Reduce repetitive AI-style patterns
* Improve visual hierarchy
* Simplify CSS
* Preserve existing functionality
* Preserve the project's brand identity
* Make components feel intentionally designed rather than generated from a template
* Keep the code maintainable and predictable

CSSMAN works with any project:

* Django
* React
* Next.js
* Vue
* Laravel
* PHP
* Static HTML
* Tailwind-generated CSS
* Bootstrap-based projects
* Plain CSS
* SCSS
* Component CSS
* Dashboard applications
* SaaS applications
* Enterprise applications

---

# Core Principle

> Human-designed CSS is usually driven by hierarchy, context, and purpose. AI-generated CSS often applies the same visual treatment everywhere.

CSSMAN must therefore prefer:

**Purpose over decoration.**

**Hierarchy over uniformity.**

**Consistency over repetition.**

**Clarity over visual complexity.**

**Real UI requirements over generic design trends.**

---

# Operating Rules

## 1. Read Before Changing

Never blindly rewrite a CSS file.

First inspect:

* Existing variables
* Color system
* Typography
* Spacing
* Border radius
* Shadows
* Gradients
* Filters
* Animations
* Responsive rules
* Component structure
* Naming conventions
* Existing utility classes
* Existing design system

Determine what the project is already trying to accomplish.

Do not impose a new design system unless the existing system is clearly broken.

---

# 2. Preserve Functionality

CSSMAN must not break:

* Layout
* Responsive behavior
* Modals
* Dropdowns
* Forms
* Tables
* Navigation
* Buttons
* Cards
* JavaScript-dependent states
* Hover states
* Focus states
* Active states
* Hidden/visible states
* Accessibility behavior

Do not change class names or selectors unnecessarily.

Do not remove CSS merely because it looks unusual.

Every removal must have a reason.

---

# 3. Detect AI-Style CSS Patterns

Look specifically for these patterns.

## Excessive Border Radius

Common AI pattern:

```css
border-radius: 24px;
border-radius: 28px;
border-radius: 32px;
border-radius: 9999px;
```

Do not automatically remove rounded corners.

Instead establish a sensible scale.

Typical business UI:

```css
4px
6px
8px
10px
12px
```

Use `50%` only when a circular shape is intentional:

* Avatar
* Status dot
* Circular icon button
* Circular progress indicator

Do not use `50%` as a generic component radius.

---

# 4. Remove Unnecessary Glassmorphism

Identify:

```css
backdrop-filter
-webkit-backdrop-filter
```

especially:

```css
backdrop-filter: blur(...);
```

Also identify:

```css
background: rgba(...);
```

combined with:

```css
border: 1px solid rgba(...);
box-shadow: ...;
backdrop-filter: blur(...);
```

This combination frequently creates unnecessary glassmorphism.

Replace it with solid surfaces when transparency does not serve a functional purpose.

Prefer:

```css
background: #ffffff;
border: 1px solid #e5e7eb;
```

over:

```css
background: rgba(255, 255, 255, 0.62);
backdrop-filter: blur(20px);
border: 1px solid rgba(255, 255, 255, 0.75);
```

Do not remove transparency when it is required for:

* Overlay effects
* Modal backdrops
* Intentional layering
* Image overlays
* Navigation overlays

---

# 5. Reduce Excessive Shadows

Detect exaggerated shadows such as:

```css
box-shadow: 0 20px 60px rgba(...);
box-shadow: 0 30px 80px rgba(...);
box-shadow: 0 16px 40px rgba(...);
```

Prefer restrained elevation.

Example:

```css
box-shadow: 0 2px 8px rgba(0, 0, 0, 0.08);
```

or:

```css
box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
```

Do not add shadows to every element.

Use shadows primarily for:

* Modal
* Dropdown
* Popover
* Floating panel
* Elevated surface

Cards do not automatically need shadows.

---

# 6. Reduce Gradient Abuse

Detect unnecessary:

```css
linear-gradient(...)
radial-gradient(...)
conic-gradient(...)
```

Do not remove gradients that are part of the brand.

Remove gradients when they exist only for decoration.

AI-style:

```css
background:
  radial-gradient(circle at top left, ...),
  linear-gradient(135deg, ...);
```

Human-oriented alternative:

```css
background: #ffffff;
```

Use gradients deliberately, not as default backgrounds.

---

# 7. Remove Glow Effects

Detect:

```css
filter: drop-shadow(...);
text-shadow: ...;
box-shadow: 0 0 ... rgba(...);
```

especially when the purpose is creating a colored glow.

Examples:

```css
--mint-glow
--green-glow
--blue-glow
--gold-glow
--purple-glow
```

Do not automatically delete variables.

First determine whether they are actually used.

Remove decorative glow when it has no semantic purpose.

---

# 8. Simplify Animations

AI-generated interfaces frequently animate everything.

Look for:

```css
transition: all ...
```

and excessive:

```css
transform
scale()
translateY()
rotate()
pulse
float
glow
```

Do not remove useful interaction feedback.

Prefer targeted transitions:

```css
transition:
  background-color 0.15s ease,
  border-color 0.15s ease,
  color 0.15s ease;
```

Avoid:

```css
transition: all 0.3s ease;
```

unless there is a specific reason.

Do not animate ordinary content unnecessarily.

---

# 9. Avoid Excessive Hover Movement

AI-generated interfaces often use:

```css
.card:hover {
  transform: translateY(-6px);
}
```

or:

```css
button:hover {
  transform: scale(1.05);
}
```

Do not use movement merely to make the UI feel interactive.

For business applications, prefer subtle changes:

```css
button:hover {
  background: var(--green-dark);
}
```

or:

```css
.card:hover {
  border-color: var(--green-line);
}
```

Use movement only when it improves interaction feedback.

---

# 10. Fix Excessive Card Usage

Do not make every section look like a card.

AI pattern:

```text
Card
  Card
    Card
      Card
```

Evaluate whether the information can exist as:

* Table
* List
* Section
* Divider
* Inline information
* Plain container

Cards should communicate grouping.

They should not simply surround every element.

---

# 11. Establish Visual Hierarchy

CSSMAN should identify:

### Primary

Examples:

```css
font-weight: 700;
```

```css
background: var(--brand);
```

### Secondary

Examples:

```css
font-weight: 500;
color: var(--muted);
```

### Supporting

Examples:

```css
font-size: 0.875rem;
color: var(--muted);
```

Not every heading should be:

```css
font-weight: 800;
```

Not every element should have strong contrast.

---

# 12. Normalize Spacing

Detect random spacing such as:

```css
13px
17px
19px
23px
27px
31px
37px
```

Do not blindly convert every value.

Where appropriate, establish a predictable spacing scale:

```text
4px
8px
12px
16px
20px
24px
32px
40px
48px
```

Use spacing according to hierarchy.

Example:

```text
Label → 8px → Input

Input → 16px → Next field

Section → 24px → Section

Major section → 40px/48px → Major section
```

---

# 13. Do Not Make Everything Symmetrical

AI-generated interfaces often have:

```text
Everything centered
Everything equal width
Everything equal spacing
Everything same radius
Everything same shadow
```

Human interfaces often use hierarchy.

Do not force symmetry when the content does not require it.

For example:

```css
.page-header {
  display: flex;
  justify-content: space-between;
}
```

may be more appropriate than centering everything.

---

# 14. Typography

Avoid excessive font weights.

Bad:

```css
font-weight: 900;
```

everywhere.

Prefer:

```text
400 → body
500 → labels
600 → important UI
700 → headings
```

Do not introduce a new font unless there is a clear reason.

Respect existing project fonts.

If the project already uses a typography system, preserve it.

---

# 15. Color Discipline

Do not introduce random colors.

Identify the existing:

* Primary
* Secondary
* Background
* Surface
* Border
* Text
* Muted
* Success
* Warning
* Error
* Info

Use semantic colors consistently.

Avoid unnecessary color variables such as:

```css
--green-glow
--green-soft-2
--green-light-alt
--green-gradient-start
--green-gradient-end
```

when they represent nearly identical colors.

Consolidate duplicates when safe.

---

# 16. Preserve Brand Identity

CSSMAN does not mean:

> Make everything gray and boring.

If the project has a green brand, keep the green.

If the project has a dark theme, preserve the dark theme.

If the project uses distinctive typography, preserve it.

The objective is:

```text
Existing Brand
      +
Less visual noise
      +
Better hierarchy
      +
Purposeful components
```

Not:

```text
Existing Brand
      ↓
Generic white website
```

---

# 17. Component-Specific Rules

## Buttons

Prefer:

```css
border-radius: 6px;
```

or:

```css
border-radius: 8px;
```

Avoid excessive:

```css
border-radius: 9999px;
```

unless the button is intentionally pill-shaped.

Do not use:

* Large glow
* Excessive gradients
* Large scale animations

Primary buttons should be visually stronger than secondary buttons.

---

## Inputs

Prefer clear borders:

```css
border: 1px solid var(--border);
background: #fff;
```

Focus state should be obvious:

```css
input:focus {
  border-color: var(--brand);
  outline: 2px solid rgba(22, 163, 74, 0.12);
}
```

Do not rely only on shadows to indicate focus.

---

## Cards

Default:

```css
background: #fff;
border: 1px solid var(--border);
border-radius: 8px;
```

Shadow should be optional.

Do not automatically use glass effects.

---

## Modals

Prefer:

```css
background: #fff;
border: 1px solid var(--border);
border-radius: 8px;
box-shadow: 0 8px 24px rgba(0, 0, 0, 0.12);
```

The backdrop may remain translucent.

The modal itself normally does not need:

```css
backdrop-filter: blur(...);
```

---

## Tables

Business applications should prioritize tables when data is tabular.

Do not convert table information into decorative cards.

Use:

* Clear column hierarchy
* Compact spacing
* Strong header distinction
* Row hover only when useful
* Status badges where semantic

---

## Navigation

Navigation should prioritize:

1. Current location
2. Primary workflow
3. Secondary navigation
4. Settings/utilities

Do not add decorative effects to every navigation item.

---

# 18. CSS Complexity Reduction

Look for:

* Duplicate declarations
* Duplicate selectors
* Dead styles
* Unused variables
* Repeated media queries
* Repeated colors
* Repeated shadows
* Repeated radius values
* Overly specific selectors
* Unnecessary `!important`
* Redundant vendor prefixes
* Repeated component styles

Simplify where safe.

Do not refactor the entire architecture merely for aesthetics.

---

# 19. Selector Quality

Prefer:

```css
.modal-title
```

over unnecessarily specific selectors:

```css
.page .content .container .modal .modal-content .modal-title
```

Avoid specificity wars.

Do not use:

```css
!important
```

unless necessary to override an external framework or unavoidable legacy rule.

---

# 20. Responsive CSS

Do not destroy existing responsive behavior.

Check:

* Mobile
* Tablet
* Desktop
* Large screens

Avoid arbitrary breakpoints.

Do not create separate desktop and mobile designs unless required.

Preserve existing responsive logic when it works.

---

# 21. Accessibility

Never sacrifice accessibility for visual simplicity.

Preserve:

* Visible focus
* Sufficient contrast
* Reduced motion support
* Keyboard interaction states
* Disabled states
* Error states

When animations are present, consider:

```css
@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    animation-duration: 0.01ms;
    animation-iteration-count: 1;
    transition-duration: 0.01ms;
  }
}
```

Only add this if it fits the project's existing architecture.

---

# 22. Do Not Over-Clean

CSSMAN must not turn every stylesheet into the same style.

Do not blindly enforce:

```text
8px radius
white background
gray border
no shadow
no animation
```

on every project.

The goal is intentional design.

A gaming website, medical dashboard, factory application, portfolio, e-commerce store, and SaaS product can legitimately have different visual systems.

CSSMAN adapts to the project's context.

---

# 23. Human Design Heuristics

When choosing between two visually valid implementations, evaluate:

### Purpose

Does the property communicate something?

### Hierarchy

Does it help users understand importance?

### Context

Does it fit this component?

### Consistency

Does it belong to the project's design system?

### Restraint

Would removing it make the UI clearer?

### Maintainability

Will another developer understand why it exists?

If the answer is no to most of these, simplify it.

---

# 24. Refactoring Priority

Apply changes in this order.

## Level 1 — Visual Noise

Remove:

* Excessive blur
* Excessive glow
* Excessive gradients
* Excessive shadows
* Excessive animations

## Level 2 — Repetition

Fix:

* Every component having identical radius
* Every component having identical shadow
* Every section being a card
* Every element using the same spacing

## Level 3 — Hierarchy

Fix:

* Heading sizes
* Button importance
* Content density
* Section spacing
* Muted text

## Level 4 — Code Quality

Fix:

* Duplicate rules
* Dead variables
* Repeated declarations
* Specificity problems
* Unnecessary `!important`

## Level 5 — Polish

Only after the above:

* Micro-interactions
* Hover states
* Animation timing
* Fine spacing
* Border details

Do not spend time polishing a fundamentally over-designed component.

---

# 25. Before/After Mental Model

## AI-heavy

```text
Gradient
   ↓
Glass card
   ↓
Blur
   ↓
Huge radius
   ↓
Huge shadow
   ↓
Glow
   ↓
Hover scale
```

## Human-oriented

```text
Purpose
   ↓
Hierarchy
   ↓
Spacing
   ↓
Typography
   ↓
Border
   ↓
Subtle elevation
   ↓
Minimal interaction feedback
```

---

# 26. Safe Refactoring Pattern

Before:

```css
.card {
  background: rgba(255, 255, 255, 0.62);
  backdrop-filter: blur(20px);
  border: 1px solid rgba(255, 255, 255, 0.75);
  border-radius: 24px;
  box-shadow:
    0 20px 60px rgba(13, 60, 34, 0.16),
    0 2px 6px rgba(13, 60, 34, 0.08);
  transition: all 0.3s ease;
}

.card:hover {
  transform: translateY(-6px);
  box-shadow:
    0 30px 80px rgba(13, 60, 34, 0.2);
}
```

After:

```css
.card {
  background: #ffffff;
  border: 1px solid var(--border);
  border-radius: 8px;
  transition: border-color 0.15s ease;
}

.card:hover {
  border-color: var(--brand);
}
```

Do not apply this transformation blindly.

It is an example of the decision-making pattern.

---

# 27. Variables

If the project has design tokens, preserve them.

Prefer semantic variables:

```css
:root {
  --brand: #16a34a;
  --brand-dark: #0b6b34;

  --text: #0f2018;
  --text-muted: #48604f;

  --surface: #ffffff;
  --surface-muted: #f8faf9;

  --border: #e3ede6;

  --radius-sm: 6px;
  --radius-md: 8px;

  --shadow-sm: 0 2px 8px rgba(0, 0, 0, 0.08);
  --shadow-md: 0 8px 24px rgba(0, 0, 0, 0.12);
}
```

Do not create tokens for every single value.

---

# 28. Output Requirements

When CSSMAN modifies a CSS file:

1. Preserve all required selectors.
2. Preserve functionality.
3. Preserve responsive behavior.
4. Preserve brand colors unless there is a clear reason to change them.
5. Remove unnecessary visual effects.
6. Reduce repeated patterns.
7. Simplify selectors where safe.
8. Remove genuinely unused declarations when confidently identifiable.
9. Keep formatting consistent with the existing project.
10. Do not add comments everywhere.
11. Do not rewrite unrelated CSS.
12. Do not introduce a new framework.
13. Do not introduce Tailwind, Bootstrap, or another library.
14. Do not change HTML/JS unless explicitly required.
15. Do not invent a design system without examining the existing one.

---

# 29. Final Verification

After editing, inspect the resulting CSS for:

```text
[ ] Broken selectors
[ ] Missing closing braces
[ ] Invalid declarations
[ ] Duplicate rules
[ ] Unnecessary !important
[ ] Broken responsive behavior
[ ] Excessive radius
[ ] Excessive shadows
[ ] Excessive gradients
[ ] Excessive blur
[ ] Excessive glow
[ ] Excessive animation
[ ] Inconsistent spacing
[ ] Inconsistent typography
[ ] Lost focus states
[ ] Lost hover states
[ ] Lost disabled states
```

CSSMAN must prioritize **working CSS over aesthetic purity**.

---

# 30. Definition of Done

A CSS file is considered cleaned when:

* The UI no longer relies on decoration to communicate quality.
* Components have clear visual hierarchy.
* Effects have identifiable purposes.
* Radius values are intentional.
* Shadows are restrained.
* Glassmorphism is not used by default.
* Gradients are purposeful.
* Animations communicate interaction rather than decoration.
* Spacing follows a recognizable system.
* Typography has hierarchy.
* Colors are semantically consistent.
* CSS contains less unnecessary repetition.
* Existing functionality remains intact.
* The result still belongs to the original project's brand.

The final result should look like a developer or designer made deliberate decisions for **this specific application**, rather than applying a generic AI design template.
# CSSMAN

## Purpose

CSSMAN is a CSS cleanup and refinement skill for transforming AI-generated or over-designed CSS into clean, intentional, human-designed CSS.

The goal is **not** to redesign the entire application.

The goal is to:

* Remove unnecessary visual effects
* Reduce repetitive AI-style patterns
* Improve visual hierarchy
* Simplify CSS
* Preserve existing functionality
* Preserve the project's brand identity
* Make components feel intentionally designed rather than generated from a template
* Keep the code maintainable and predictable

CSSMAN works with any project:

* Django
* React
* Next.js
* Vue
* Laravel
* PHP
* Static HTML
* Tailwind-generated CSS
* Bootstrap-based projects
* Plain CSS
* SCSS
* Component CSS
* Dashboard applications
* SaaS applications
* Enterprise applications

---

# Core Principle

> Human-designed CSS is usually driven by hierarchy, context, and purpose. AI-generated CSS often applies the same visual treatment everywhere.

CSSMAN must therefore prefer:

**Purpose over decoration.**

**Hierarchy over uniformity.**

**Consistency over repetition.**

**Clarity over visual complexity.**

**Real UI requirements over generic design trends.**

---

# Operating Rules

## 1. Read Before Changing

Never blindly rewrite a CSS file.

First inspect:

* Existing variables
* Color system
* Typography
* Spacing
* Border radius
* Shadows
* Gradients
* Filters
* Animations
* Responsive rules
* Component structure
* Naming conventions
* Existing utility classes
* Existing design system

Determine what the project is already trying to accomplish.

Do not impose a new design system unless the existing system is clearly broken.

---

# 2. Preserve Functionality

CSSMAN must not break:

* Layout
* Responsive behavior
* Modals
* Dropdowns
* Forms
* Tables
* Navigation
* Buttons
* Cards
* JavaScript-dependent states
* Hover states
* Focus states
* Active states
* Hidden/visible states
* Accessibility behavior

Do not change class names or selectors unnecessarily.

Do not remove CSS merely because it looks unusual.

Every removal must have a reason.

---

# 3. Detect AI-Style CSS Patterns

Look specifically for these patterns.

## Excessive Border Radius

Common AI pattern:

```css
border-radius: 24px;
border-radius: 28px;
border-radius: 32px;
border-radius: 9999px;
```

Do not automatically remove rounded corners.

Instead establish a sensible scale.

Typical business UI:

```css
4px
6px
8px
10px
12px
```

Use `50%` only when a circular shape is intentional:

* Avatar
* Status dot
* Circular icon button
* Circular progress indicator

Do not use `50%` as a generic component radius.

---

# 4. Remove Unnecessary Glassmorphism

Identify:

```css
backdrop-filter
-webkit-backdrop-filter
```

especially:

```css
backdrop-filter: blur(...);
```

Also identify:

```css
background: rgba(...);
```

combined with:

```css
border: 1px solid rgba(...);
box-shadow: ...;
backdrop-filter: blur(...);
```

This combination frequently creates unnecessary glassmorphism.

Replace it with solid surfaces when transparency does not serve a functional purpose.

Prefer:

```css
background: #ffffff;
border: 1px solid #e5e7eb;
```

over:

```css
background: rgba(255, 255, 255, 0.62);
backdrop-filter: blur(20px);
border: 1px solid rgba(255, 255, 255, 0.75);
```

Do not remove transparency when it is required for:

* Overlay effects
* Modal backdrops
* Intentional layering
* Image overlays
* Navigation overlays

---

# 5. Reduce Excessive Shadows

Detect exaggerated shadows such as:

```css
box-shadow: 0 20px 60px rgba(...);
box-shadow: 0 30px 80px rgba(...);
box-shadow: 0 16px 40px rgba(...);
```

Prefer restrained elevation.

Example:

```css
box-shadow: 0 2px 8px rgba(0, 0, 0, 0.08);
```

or:

```css
box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
```

Do not add shadows to every element.

Use shadows primarily for:

* Modal
* Dropdown
* Popover
* Floating panel
* Elevated surface

Cards do not automatically need shadows.

---

# 6. Reduce Gradient Abuse

Detect unnecessary:

```css
linear-gradient(...)
radial-gradient(...)
conic-gradient(...)
```

Do not remove gradients that are part of the brand.

Remove gradients when they exist only for decoration.

AI-style:

```css
background:
  radial-gradient(circle at top left, ...),
  linear-gradient(135deg, ...);
```

Human-oriented alternative:

```css
background: #ffffff;
```

Use gradients deliberately, not as default backgrounds.

---

# 7. Remove Glow Effects

Detect:

```css
filter: drop-shadow(...);
text-shadow: ...;
box-shadow: 0 0 ... rgba(...);
```

especially when the purpose is creating a colored glow.

Examples:

```css
--mint-glow
--green-glow
--blue-glow
--gold-glow
--purple-glow
```

Do not automatically delete variables.

First determine whether they are actually used.

Remove decorative glow when it has no semantic purpose.

---

# 8. Simplify Animations

AI-generated interfaces frequently animate everything.

Look for:

```css
transition: all ...
```

and excessive:

```css
transform
scale()
translateY()
rotate()
pulse
float
glow
```

Do not remove useful interaction feedback.

Prefer targeted transitions:

```css
transition:
  background-color 0.15s ease,
  border-color 0.15s ease,
  color 0.15s ease;
```

Avoid:

```css
transition: all 0.3s ease;
```

unless there is a specific reason.

Do not animate ordinary content unnecessarily.

---

# 9. Avoid Excessive Hover Movement

AI-generated interfaces often use:

```css
.card:hover {
  transform: translateY(-6px);
}
```

or:

```css
button:hover {
  transform: scale(1.05);
}
```

Do not use movement merely to make the UI feel interactive.

For business applications, prefer subtle changes:

```css
button:hover {
  background: var(--green-dark);
}
```

or:

```css
.card:hover {
  border-color: var(--green-line);
}
```

Use movement only when it improves interaction feedback.

---

# 10. Fix Excessive Card Usage

Do not make every section look like a card.

AI pattern:

```text
Card
  Card
    Card
      Card
```

Evaluate whether the information can exist as:

* Table
* List
* Section
* Divider
* Inline information
* Plain container

Cards should communicate grouping.

They should not simply surround every element.

---

# 11. Establish Visual Hierarchy

CSSMAN should identify:

### Primary

Examples:

```css
font-weight: 700;
```

```css
background: var(--brand);
```

### Secondary

Examples:

```css
font-weight: 500;
color: var(--muted);
```

### Supporting

Examples:

```css
font-size: 0.875rem;
color: var(--muted);
```

Not every heading should be:

```css
font-weight: 800;
```

Not every element should have strong contrast.

---

# 12. Normalize Spacing

Detect random spacing such as:

```css
13px
17px
19px
23px
27px
31px
37px
```

Do not blindly convert every value.

Where appropriate, establish a predictable spacing scale:

```text
4px
8px
12px
16px
20px
24px
32px
40px
48px
```

Use spacing according to hierarchy.

Example:

```text
Label → 8px → Input

Input → 16px → Next field

Section → 24px → Section

Major section → 40px/48px → Major section
```

---

# 13. Do Not Make Everything Symmetrical

AI-generated interfaces often have:

```text
Everything centered
Everything equal width
Everything equal spacing
Everything same radius
Everything same shadow
```

Human interfaces often use hierarchy.

Do not force symmetry when the content does not require it.

For example:

```css
.page-header {
  display: flex;
  justify-content: space-between;
}
```

may be more appropriate than centering everything.

---

# 14. Typography

Avoid excessive font weights.

Bad:

```css
font-weight: 900;
```

everywhere.

Prefer:

```text
400 → body
500 → labels
600 → important UI
700 → headings
```

Do not introduce a new font unless there is a clear reason.

Respect existing project fonts.

If the project already uses a typography system, preserve it.

---

# 15. Color Discipline

Do not introduce random colors.

Identify the existing:

* Primary
* Secondary
* Background
* Surface
* Border
* Text
* Muted
* Success
* Warning
* Error
* Info

Use semantic colors consistently.

Avoid unnecessary color variables such as:

```css
--green-glow
--green-soft-2
--green-light-alt
--green-gradient-start
--green-gradient-end
```

when they represent nearly identical colors.

Consolidate duplicates when safe.

---

# 16. Preserve Brand Identity

CSSMAN does not mean:

> Make everything gray and boring.

If the project has a green brand, keep the green.

If the project has a dark theme, preserve the dark theme.

If the project uses distinctive typography, preserve it.

The objective is:

```text
Existing Brand
      +
Less visual noise
      +
Better hierarchy
      +
Purposeful components
```

Not:

```text
Existing Brand
      ↓
Generic white website
```

---

# 17. Component-Specific Rules

## Buttons

Prefer:

```css
border-radius: 6px;
```

or:

```css
border-radius: 8px;
```

Avoid excessive:

```css
border-radius: 9999px;
```

unless the button is intentionally pill-shaped.

Do not use:

* Large glow
* Excessive gradients
* Large scale animations

Primary buttons should be visually stronger than secondary buttons.

---

## Inputs

Prefer clear borders:

```css
border: 1px solid var(--border);
background: #fff;
```

Focus state should be obvious:

```css
input:focus {
  border-color: var(--brand);
  outline: 2px solid rgba(22, 163, 74, 0.12);
}
```

Do not rely only on shadows to indicate focus.

---

## Cards

Default:

```css
background: #fff;
border: 1px solid var(--border);
border-radius: 8px;
```

Shadow should be optional.

Do not automatically use glass effects.

---

## Modals

Prefer:

```css
background: #fff;
border: 1px solid var(--border);
border-radius: 8px;
box-shadow: 0 8px 24px rgba(0, 0, 0, 0.12);
```

The backdrop may remain translucent.

The modal itself normally does not need:

```css
backdrop-filter: blur(...);
```

---

## Tables

Business applications should prioritize tables when data is tabular.

Do not convert table information into decorative cards.

Use:

* Clear column hierarchy
* Compact spacing
* Strong header distinction
* Row hover only when useful
* Status badges where semantic

---

## Navigation

Navigation should prioritize:

1. Current location
2. Primary workflow
3. Secondary navigation
4. Settings/utilities

Do not add decorative effects to every navigation item.

---

# 18. CSS Complexity Reduction

Look for:

* Duplicate declarations
* Duplicate selectors
* Dead styles
* Unused variables
* Repeated media queries
* Repeated colors
* Repeated shadows
* Repeated radius values
* Overly specific selectors
* Unnecessary `!important`
* Redundant vendor prefixes
* Repeated component styles

Simplify where safe.

Do not refactor the entire architecture merely for aesthetics.

---

# 19. Selector Quality

Prefer:

```css
.modal-title
```

over unnecessarily specific selectors:

```css
.page .content .container .modal .modal-content .modal-title
```

Avoid specificity wars.

Do not use:

```css
!important
```

unless necessary to override an external framework or unavoidable legacy rule.

---

# 20. Responsive CSS

Do not destroy existing responsive behavior.

Check:

* Mobile
* Tablet
* Desktop
* Large screens

Avoid arbitrary breakpoints.

Do not create separate desktop and mobile designs unless required.

Preserve existing responsive logic when it works.

---

# 21. Accessibility

Never sacrifice accessibility for visual simplicity.

Preserve:

* Visible focus
* Sufficient contrast
* Reduced motion support
* Keyboard interaction states
* Disabled states
* Error states

When animations are present, consider:

```css
@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    animation-duration: 0.01ms;
    animation-iteration-count: 1;
    transition-duration: 0.01ms;
  }
}
```

Only add this if it fits the project's existing architecture.

---

# 22. Do Not Over-Clean

CSSMAN must not turn every stylesheet into the same style.

Do not blindly enforce:

```text
8px radius
white background
gray border
no shadow
no animation
```

on every project.

The goal is intentional design.

A gaming website, medical dashboard, factory application, portfolio, e-commerce store, and SaaS product can legitimately have different visual systems.

CSSMAN adapts to the project's context.

---

# 23. Human Design Heuristics

When choosing between two visually valid implementations, evaluate:

### Purpose

Does the property communicate something?

### Hierarchy

Does it help users understand importance?

### Context

Does it fit this component?

### Consistency

Does it belong to the project's design system?

### Restraint

Would removing it make the UI clearer?

### Maintainability

Will another developer understand why it exists?

If the answer is no to most of these, simplify it.

---

# 24. Refactoring Priority

Apply changes in this order.

## Level 1 — Visual Noise

Remove:

* Excessive blur
* Excessive glow
* Excessive gradients
* Excessive shadows
* Excessive animations

## Level 2 — Repetition

Fix:

* Every component having identical radius
* Every component having identical shadow
* Every section being a card
* Every element using the same spacing

## Level 3 — Hierarchy

Fix:

* Heading sizes
* Button importance
* Content density
* Section spacing
* Muted text

## Level 4 — Code Quality

Fix:

* Duplicate rules
* Dead variables
* Repeated declarations
* Specificity problems
* Unnecessary `!important`

## Level 5 — Polish

Only after the above:

* Micro-interactions
* Hover states
* Animation timing
* Fine spacing
* Border details

Do not spend time polishing a fundamentally over-designed component.

---

# 25. Before/After Mental Model

## AI-heavy

```text
Gradient
   ↓
Glass card
   ↓
Blur
   ↓
Huge radius
   ↓
Huge shadow
   ↓
Glow
   ↓
Hover scale
```

## Human-oriented

```text
Purpose
   ↓
Hierarchy
   ↓
Spacing
   ↓
Typography
   ↓
Border
   ↓
Subtle elevation
   ↓
Minimal interaction feedback
```

---

# 26. Safe Refactoring Pattern

Before:

```css
.card {
  background: rgba(255, 255, 255, 0.62);
  backdrop-filter: blur(20px);
  border: 1px solid rgba(255, 255, 255, 0.75);
  border-radius: 24px;
  box-shadow:
    0 20px 60px rgba(13, 60, 34, 0.16),
    0 2px 6px rgba(13, 60, 34, 0.08);
  transition: all 0.3s ease;
}

.card:hover {
  transform: translateY(-6px);
  box-shadow:
    0 30px 80px rgba(13, 60, 34, 0.2);
}
```

After:

```css
.card {
  background: #ffffff;
  border: 1px solid var(--border);
  border-radius: 8px;
  transition: border-color 0.15s ease;
}

.card:hover {
  border-color: var(--brand);
}
```

Do not apply this transformation blindly.

It is an example of the decision-making pattern.

---

# 27. Variables

If the project has design tokens, preserve them.

Prefer semantic variables:

```css
:root {
  --brand: #16a34a;
  --brand-dark: #0b6b34;

  --text: #0f2018;
  --text-muted: #48604f;

  --surface: #ffffff;
  --surface-muted: #f8faf9;

  --border: #e3ede6;

  --radius-sm: 6px;
  --radius-md: 8px;

  --shadow-sm: 0 2px 8px rgba(0, 0, 0, 0.08);
  --shadow-md: 0 8px 24px rgba(0, 0, 0, 0.12);
}
```

Do not create tokens for every single value.

---

# 28. Output Requirements

When CSSMAN modifies a CSS file:

1. Preserve all required selectors.
2. Preserve functionality.
3. Preserve responsive behavior.
4. Preserve brand colors unless there is a clear reason to change them.
5. Remove unnecessary visual effects.
6. Reduce repeated patterns.
7. Simplify selectors where safe.
8. Remove genuinely unused declarations when confidently identifiable.
9. Keep formatting consistent with the existing project.
10. Do not add comments everywhere.
11. Do not rewrite unrelated CSS.
12. Do not introduce a new framework.
13. Do not introduce Tailwind, Bootstrap, or another library.
14. Do not change HTML/JS unless explicitly required.
15. Do not invent a design system without examining the existing one.

---

# 29. Final Verification

After editing, inspect the resulting CSS for:

```text
[ ] Broken selectors
[ ] Missing closing braces
[ ] Invalid declarations
[ ] Duplicate rules
[ ] Unnecessary !important
[ ] Broken responsive behavior
[ ] Excessive radius
[ ] Excessive shadows
[ ] Excessive gradients
[ ] Excessive blur
[ ] Excessive glow
[ ] Excessive animation
[ ] Inconsistent spacing
[ ] Inconsistent typography
[ ] Lost focus states
[ ] Lost hover states
[ ] Lost disabled states
```

CSSMAN must prioritize **working CSS over aesthetic purity**.

---

# 30. Definition of Done

A CSS file is considered cleaned when:

* The UI no longer relies on decoration to communicate quality.
* Components have clear visual hierarchy.
* Effects have identifiable purposes.
* Radius values are intentional.
* Shadows are restrained.
* Glassmorphism is not used by default.
* Gradients are purposeful.
* Animations communicate interaction rather than decoration.
* Spacing follows a recognizable system.
* Typography has hierarchy.
* Colors are semantically consistent.
* CSS contains less unnecessary repetition.
* Existing functionality remains intact.
* The result still belongs to the original project's brand.

The final result should look like a developer or designer made deliberate decisions for **this specific application**, rather than applying a generic AI design template.
# CSSMAN

## Purpose

CSSMAN is a CSS cleanup and refinement skill for transforming AI-generated or over-designed CSS into clean, intentional, human-designed CSS.

The goal is **not** to redesign the entire application.

The goal is to:

* Remove unnecessary visual effects
* Reduce repetitive AI-style patterns
* Improve visual hierarchy
* Simplify CSS
* Preserve existing functionality
* Preserve the project's brand identity
* Make components feel intentionally designed rather than generated from a template
* Keep the code maintainable and predictable

CSSMAN works with any project:

* Django
* React
* Next.js
* Vue
* Laravel
* PHP
* Static HTML
* Tailwind-generated CSS
* Bootstrap-based projects
* Plain CSS
* SCSS
* Component CSS
* Dashboard applications
* SaaS applications
* Enterprise applications

---

# Core Principle

> Human-designed CSS is usually driven by hierarchy, context, and purpose. AI-generated CSS often applies the same visual treatment everywhere.

CSSMAN must therefore prefer:

**Purpose over decoration.**

**Hierarchy over uniformity.**

**Consistency over repetition.**

**Clarity over visual complexity.**

**Real UI requirements over generic design trends.**

---

# Operating Rules

## 1. Read Before Changing

Never blindly rewrite a CSS file.

First inspect:

* Existing variables
* Color system
* Typography
* Spacing
* Border radius
* Shadows
* Gradients
* Filters
* Animations
* Responsive rules
* Component structure
* Naming conventions
* Existing utility classes
* Existing design system

Determine what the project is already trying to accomplish.

Do not impose a new design system unless the existing system is clearly broken.

---

# 2. Preserve Functionality

CSSMAN must not break:

* Layout
* Responsive behavior
* Modals
* Dropdowns
* Forms
* Tables
* Navigation
* Buttons
* Cards
* JavaScript-dependent states
* Hover states
* Focus states
* Active states
* Hidden/visible states
* Accessibility behavior

Do not change class names or selectors unnecessarily.

Do not remove CSS merely because it looks unusual.

Every removal must have a reason.

---

# 3. Detect AI-Style CSS Patterns

Look specifically for these patterns.

## Excessive Border Radius

Common AI pattern:

```css
border-radius: 24px;
border-radius: 28px;
border-radius: 32px;
border-radius: 9999px;
```

Do not automatically remove rounded corners.

Instead establish a sensible scale.

Typical business UI:

```css
4px
6px
8px
10px
12px
```

Use `50%` only when a circular shape is intentional:

* Avatar
* Status dot
* Circular icon button
* Circular progress indicator

Do not use `50%` as a generic component radius.

---

# 4. Remove Unnecessary Glassmorphism

Identify:

```css
backdrop-filter
-webkit-backdrop-filter
```

especially:

```css
backdrop-filter: blur(...);
```

Also identify:

```css
background: rgba(...);
```

combined with:

```css
border: 1px solid rgba(...);
box-shadow: ...;
backdrop-filter: blur(...);
```

This combination frequently creates unnecessary glassmorphism.

Replace it with solid surfaces when transparency does not serve a functional purpose.

Prefer:

```css
background: #ffffff;
border: 1px solid #e5e7eb;
```

over:

```css
background: rgba(255, 255, 255, 0.62);
backdrop-filter: blur(20px);
border: 1px solid rgba(255, 255, 255, 0.75);
```

Do not remove transparency when it is required for:

* Overlay effects
* Modal backdrops
* Intentional layering
* Image overlays
* Navigation overlays

---

# 5. Reduce Excessive Shadows

Detect exaggerated shadows such as:

```css
box-shadow: 0 20px 60px rgba(...);
box-shadow: 0 30px 80px rgba(...);
box-shadow: 0 16px 40px rgba(...);
```

Prefer restrained elevation.

Example:

```css
box-shadow: 0 2px 8px rgba(0, 0, 0, 0.08);
```

or:

```css
box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
```

Do not add shadows to every element.

Use shadows primarily for:

* Modal
* Dropdown
* Popover
* Floating panel
* Elevated surface

Cards do not automatically need shadows.

---

# 6. Reduce Gradient Abuse

Detect unnecessary:

```css
linear-gradient(...)
radial-gradient(...)
conic-gradient(...)
```

Do not remove gradients that are part of the brand.

Remove gradients when they exist only for decoration.

AI-style:

```css
background:
  radial-gradient(circle at top left, ...),
  linear-gradient(135deg, ...);
```

Human-oriented alternative:

```css
background: #ffffff;
```

Use gradients deliberately, not as default backgrounds.

---

# 7. Remove Glow Effects

Detect:

```css
filter: drop-shadow(...);
text-shadow: ...;
box-shadow: 0 0 ... rgba(...);
```

especially when the purpose is creating a colored glow.

Examples:

```css
--mint-glow
--green-glow
--blue-glow
--gold-glow
--purple-glow
```

Do not automatically delete variables.

First determine whether they are actually used.

Remove decorative glow when it has no semantic purpose.

---

# 8. Simplify Animations

AI-generated interfaces frequently animate everything.

Look for:

```css
transition: all ...
```

and excessive:

```css
transform
scale()
translateY()
rotate()
pulse
float
glow
```

Do not remove useful interaction feedback.

Prefer targeted transitions:

```css
transition:
  background-color 0.15s ease,
  border-color 0.15s ease,
  color 0.15s ease;
```

Avoid:

```css
transition: all 0.3s ease;
```

unless there is a specific reason.

Do not animate ordinary content unnecessarily.

---

# 9. Avoid Excessive Hover Movement

AI-generated interfaces often use:

```css
.card:hover {
  transform: translateY(-6px);
}
```

or:

```css
button:hover {
  transform: scale(1.05);
}
```

Do not use movement merely to make the UI feel interactive.

For business applications, prefer subtle changes:

```css
button:hover {
  background: var(--green-dark);
}
```

or:

```css
.card:hover {
  border-color: var(--green-line);
}
```

Use movement only when it improves interaction feedback.

---

# 10. Fix Excessive Card Usage

Do not make every section look like a card.

AI pattern:

```text
Card
  Card
    Card
      Card
```

Evaluate whether the information can exist as:

* Table
* List
* Section
* Divider
* Inline information
* Plain container

Cards should communicate grouping.

They should not simply surround every element.

---

# 11. Establish Visual Hierarchy

CSSMAN should identify:

### Primary

Examples:

```css
font-weight: 700;
```

```css
background: var(--brand);
```

### Secondary

Examples:

```css
font-weight: 500;
color: var(--muted);
```

### Supporting

Examples:

```css
font-size: 0.875rem;
color: var(--muted);
```

Not every heading should be:

```css
font-weight: 800;
```

Not every element should have strong contrast.

---

# 12. Normalize Spacing

Detect random spacing such as:

```css
13px
17px
19px
23px
27px
31px
37px
```

Do not blindly convert every value.

Where appropriate, establish a predictable spacing scale:

```text
4px
8px
12px
16px
20px
24px
32px
40px
48px
```

Use spacing according to hierarchy.

Example:

```text
Label → 8px → Input

Input → 16px → Next field

Section → 24px → Section

Major section → 40px/48px → Major section
```

---

# 13. Do Not Make Everything Symmetrical

AI-generated interfaces often have:

```text
Everything centered
Everything equal width
Everything equal spacing
Everything same radius
Everything same shadow
```

Human interfaces often use hierarchy.

Do not force symmetry when the content does not require it.

For example:

```css
.page-header {
  display: flex;
  justify-content: space-between;
}
```

may be more appropriate than centering everything.

---

# 14. Typography

Avoid excessive font weights.

Bad:

```css
font-weight: 900;
```

everywhere.

Prefer:

```text
400 → body
500 → labels
600 → important UI
700 → headings
```

Do not introduce a new font unless there is a clear reason.

Respect existing project fonts.

If the project already uses a typography system, preserve it.

---

# 15. Color Discipline

Do not introduce random colors.

Identify the existing:

* Primary
* Secondary
* Background
* Surface
* Border
* Text
* Muted
* Success
* Warning
* Error
* Info

Use semantic colors consistently.

Avoid unnecessary color variables such as:

```css
--green-glow
--green-soft-2
--green-light-alt
--green-gradient-start
--green-gradient-end
```

when they represent nearly identical colors.

Consolidate duplicates when safe.

---

# 16. Preserve Brand Identity

CSSMAN does not mean:

> Make everything gray and boring.

If the project has a green brand, keep the green.

If the project has a dark theme, preserve the dark theme.

If the project uses distinctive typography, preserve it.

The objective is:

```text
Existing Brand
      +
Less visual noise
      +
Better hierarchy
      +
Purposeful components
```

Not:

```text
Existing Brand
      ↓
Generic white website
```

---

# 17. Component-Specific Rules

## Buttons

Prefer:

```css
border-radius: 6px;
```

or:

```css
border-radius: 8px;
```

Avoid excessive:

```css
border-radius: 9999px;
```

unless the button is intentionally pill-shaped.

Do not use:

* Large glow
* Excessive gradients
* Large scale animations

Primary buttons should be visually stronger than secondary buttons.

---

## Inputs

Prefer clear borders:

```css
border: 1px solid var(--border);
background: #fff;
```

Focus state should be obvious:

```css
input:focus {
  border-color: var(--brand);
  outline: 2px solid rgba(22, 163, 74, 0.12);
}
```

Do not rely only on shadows to indicate focus.

---

## Cards

Default:

```css
background: #fff;
border: 1px solid var(--border);
border-radius: 8px;
```

Shadow should be optional.

Do not automatically use glass effects.

---

## Modals

Prefer:

```css
background: #fff;
border: 1px solid var(--border);
border-radius: 8px;
box-shadow: 0 8px 24px rgba(0, 0, 0, 0.12);
```

The backdrop may remain translucent.

The modal itself normally does not need:

```css
backdrop-filter: blur(...);
```

---

## Tables

Business applications should prioritize tables when data is tabular.

Do not convert table information into decorative cards.

Use:

* Clear column hierarchy
* Compact spacing
* Strong header distinction
* Row hover only when useful
* Status badges where semantic

---

## Navigation

Navigation should prioritize:

1. Current location
2. Primary workflow
3. Secondary navigation
4. Settings/utilities

Do not add decorative effects to every navigation item.

---

# 18. CSS Complexity Reduction

Look for:

* Duplicate declarations
* Duplicate selectors
* Dead styles
* Unused variables
* Repeated media queries
* Repeated colors
* Repeated shadows
* Repeated radius values
* Overly specific selectors
* Unnecessary `!important`
* Redundant vendor prefixes
* Repeated component styles

Simplify where safe.

Do not refactor the entire architecture merely for aesthetics.

---

# 19. Selector Quality

Prefer:

```css
.modal-title
```

over unnecessarily specific selectors:

```css
.page .content .container .modal .modal-content .modal-title
```

Avoid specificity wars.

Do not use:

```css
!important
```

unless necessary to override an external framework or unavoidable legacy rule.

---

# 20. Responsive CSS

Do not destroy existing responsive behavior.

Check:

* Mobile
* Tablet
* Desktop
* Large screens

Avoid arbitrary breakpoints.

Do not create separate desktop and mobile designs unless required.

Preserve existing responsive logic when it works.

---

# 21. Accessibility

Never sacrifice accessibility for visual simplicity.

Preserve:

* Visible focus
* Sufficient contrast
* Reduced motion support
* Keyboard interaction states
* Disabled states
* Error states

When animations are present, consider:

```css
@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    animation-duration: 0.01ms;
    animation-iteration-count: 1;
    transition-duration: 0.01ms;
  }
}
```

Only add this if it fits the project's existing architecture.

---

# 22. Do Not Over-Clean

CSSMAN must not turn every stylesheet into the same style.

Do not blindly enforce:

```text
8px radius
white background
gray border
no shadow
no animation
```

on every project.

The goal is intentional design.

A gaming website, medical dashboard, factory application, portfolio, e-commerce store, and SaaS product can legitimately have different visual systems.

CSSMAN adapts to the project's context.

---

# 23. Human Design Heuristics

When choosing between two visually valid implementations, evaluate:

### Purpose

Does the property communicate something?

### Hierarchy

Does it help users understand importance?

### Context

Does it fit this component?

### Consistency

Does it belong to the project's design system?

### Restraint

Would removing it make the UI clearer?

### Maintainability

Will another developer understand why it exists?

If the answer is no to most of these, simplify it.

---

# 24. Refactoring Priority

Apply changes in this order.

## Level 1 — Visual Noise

Remove:

* Excessive blur
* Excessive glow
* Excessive gradients
* Excessive shadows
* Excessive animations

## Level 2 — Repetition

Fix:

* Every component having identical radius
* Every component having identical shadow
* Every section being a card
* Every element using the same spacing

## Level 3 — Hierarchy

Fix:

* Heading sizes
* Button importance
* Content density
* Section spacing
* Muted text

## Level 4 — Code Quality

Fix:

* Duplicate rules
* Dead variables
* Repeated declarations
* Specificity problems
* Unnecessary `!important`

## Level 5 — Polish

Only after the above:

* Micro-interactions
* Hover states
* Animation timing
* Fine spacing
* Border details

Do not spend time polishing a fundamentally over-designed component.

---

# 25. Before/After Mental Model

## AI-heavy

```text
Gradient
   ↓
Glass card
   ↓
Blur
   ↓
Huge radius
   ↓
Huge shadow
   ↓
Glow
   ↓
Hover scale
```

## Human-oriented

```text
Purpose
   ↓
Hierarchy
   ↓
Spacing
   ↓
Typography
   ↓
Border
   ↓
Subtle elevation
   ↓
Minimal interaction feedback
```

---

# 26. Safe Refactoring Pattern

Before:

```css
.card {
  background: rgba(255, 255, 255, 0.62);
  backdrop-filter: blur(20px);
  border: 1px solid rgba(255, 255, 255, 0.75);
  border-radius: 24px;
  box-shadow:
    0 20px 60px rgba(13, 60, 34, 0.16),
    0 2px 6px rgba(13, 60, 34, 0.08);
  transition: all 0.3s ease;
}

.card:hover {
  transform: translateY(-6px);
  box-shadow:
    0 30px 80px rgba(13, 60, 34, 0.2);
}
```

After:

```css
.card {
  background: #ffffff;
  border: 1px solid var(--border);
  border-radius: 8px;
  transition: border-color 0.15s ease;
}

.card:hover {
  border-color: var(--brand);
}
```

Do not apply this transformation blindly.

It is an example of the decision-making pattern.

---

# 27. Variables

If the project has design tokens, preserve them.

Prefer semantic variables:

```css
:root {
  --brand: #16a34a;
  --brand-dark: #0b6b34;

  --text: #0f2018;
  --text-muted: #48604f;

  --surface: #ffffff;
  --surface-muted: #f8faf9;

  --border: #e3ede6;

  --radius-sm: 6px;
  --radius-md: 8px;

  --shadow-sm: 0 2px 8px rgba(0, 0, 0, 0.08);
  --shadow-md: 0 8px 24px rgba(0, 0, 0, 0.12);
}
```

Do not create tokens for every single value.

---

# 28. Output Requirements

When CSSMAN modifies a CSS file:

1. Preserve all required selectors.
2. Preserve functionality.
3. Preserve responsive behavior.
4. Preserve brand colors unless there is a clear reason to change them.
5. Remove unnecessary visual effects.
6. Reduce repeated patterns.
7. Simplify selectors where safe.
8. Remove genuinely unused declarations when confidently identifiable.
9. Keep formatting consistent with the existing project.
10. Do not add comments everywhere.
11. Do not rewrite unrelated CSS.
12. Do not introduce a new framework.
13. Do not introduce Tailwind, Bootstrap, or another library.
14. Do not change HTML/JS unless explicitly required.
15. Do not invent a design system without examining the existing one.

---

# 29. Final Verification

After editing, inspect the resulting CSS for:

```text
[ ] Broken selectors
[ ] Missing closing braces
[ ] Invalid declarations
[ ] Duplicate rules
[ ] Unnecessary !important
[ ] Broken responsive behavior
[ ] Excessive radius
[ ] Excessive shadows
[ ] Excessive gradients
[ ] Excessive blur
[ ] Excessive glow
[ ] Excessive animation
[ ] Inconsistent spacing
[ ] Inconsistent typography
[ ] Lost focus states
[ ] Lost hover states
[ ] Lost disabled states
```

CSSMAN must prioritize **working CSS over aesthetic purity**.

---

# 30. Definition of Done

A CSS file is considered cleaned when:

* The UI no longer relies on decoration to communicate quality.
* Components have clear visual hierarchy.
* Effects have identifiable purposes.
* Radius values are intentional.
* Shadows are restrained.
* Glassmorphism is not used by default.
* Gradients are purposeful.
* Animations communicate interaction rather than decoration.
* Spacing follows a recognizable system.
* Typography has hierarchy.
* Colors are semantically consistent.
* CSS contains less unnecessary repetition.
* Existing functionality remains intact.
* The result still belongs to the original project's brand.

The final result should look like a developer or designer made deliberate decisions for **this specific application**, rather than applying a generic AI design template.
