---

name: elite-color-system
description: Prevent repetitive AI-generated color palettes. Create unique, professional, human-designed color systems inspired by branding, psychology, visual hierarchy, accessibility, and modern product design. Use for websites, dashboards, SaaS products, portfolios, ERP systems, landing pages, mobile apps, and enterprise software.
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

# Elite Color System

## Core Objective

Never generate websites that look like generic AI templates.

Every project must receive a deliberately chosen color system based on:

* Industry
* Brand personality
* Target audience
* Product purpose
* Emotional impact
* Visual hierarchy

Color selection is a design decision, not decoration.

---

# Forbidden AI Patterns

Avoid overusing:

* Blue + Purple gradients
* Cyan + Purple combinations
* Neon glow everywhere
* Generic dark mode palettes
* Tailwind default color combinations
* Identical button colors across projects
* One-color websites

If the generated design looks similar to a previous design, redesign the palette.

---

# Human Designer Thinking Process

Before selecting colors determine:

### What is being built?

Examples:

Finance:

* Trust
* Stability
* Confidence

Healthcare:

* Cleanliness
* Safety
* Calmness

Manufacturing:

* Reliability
* Efficiency
* Precision

Luxury Brand:

* Exclusivity
* Elegance
* Prestige

AI Product:

* Innovation
* Intelligence
* Modernity

ERP System:

* Productivity
* Clarity
* Structure

Portfolio:

* Personality
* Creativity
* Memorability

Color must support the purpose.

---

# Professional Palette Construction

Every project requires:

### Primary Color

Brand identity color.

### Secondary Color

Supporting accent.

### Neutral Scale

Backgrounds and typography.

### Success Color

Status indicators.

### Warning Color

Alerts.

### Error Color

Critical actions.

---

# Example Manufacturing ERP Palette

```css id="8v9t2e"
--primary: #1f4e79;
--secondary: #4f6d7a;

--bg: #f5f7fa;
--surface: #ffffff;

--text: #1b2430;
--muted: #5b6770;

--success: #2e7d32;
--warning: #ed6c02;
--danger: #d32f2f;
```

Feels industrial and professional.

---

# Example Luxury Palette

```css id="mbk63d"
--primary: #b08d57;
--secondary: #d4af37;

--bg: #0f0f0f;
--surface: #171717;

--text: #f5f5f5;
--muted: #b3b3b3;
```

Feels premium.

---

# Example Modern SaaS Palette

```css id="2z0h6q"
--primary: #2563eb;
--secondary: #0ea5e9;

--bg: #f8fafc;
--surface: #ffffff;

--text: #0f172a;
--muted: #64748b;
```

Feels scalable and trustworthy.

---

# Color Distribution Rule

Use:

```text
60% Background
30% Surface
10% Accent
```

Do not make everything colorful.

Professional interfaces rely on restraint.

---

# Contrast Rules

Text must always pass accessibility standards.

Avoid:

* Light gray text on white
* Dark gray text on black
* Low contrast buttons

Always prioritize readability over aesthetics.

---

# Accent Color Strategy

Accent colors should be rare.

Use only for:

* CTA buttons
* Important metrics
* Links
* Active states
* Highlights

If every element uses the accent color, the accent loses meaning.

---

# Industry-Specific Recommendations

## Manufacturing / RMG

Preferred:

* Steel Blue
* Slate
* Navy
* Industrial Gray
* Deep Green

Avoid:

* Neon Purple
* Bright Pink
* Gaming-style palettes

---

## Banking

Preferred:

* Navy
* Emerald
* Charcoal

Avoid:

* Excessive gradients
* Bright orange interfaces

---

## Healthcare

Preferred:

* Teal
* Soft Green
* Clean White

Avoid:

* Aggressive reds

---

## Education

Preferred:

* Blue
* Warm Orange
* Neutral White

Avoid:

* Dark intimidating themes

---

## AI Products

Preferred:

* Sophisticated neutrals
* Controlled accents
* Minimal gradients

Avoid:

* Excessive cyberpunk aesthetics

---

# Human Design References

When choosing palettes, think visually similar to:

* Apple
* Stripe
* Linear
* Notion
* Figma
* Framer
* Vercel
* Airtable
* Slack
* Arc Browser

Do not copy them.

Understand why their colors work.

---

# Component Color Logic

Cards:

```css id="r0c4z8"
background: var(--surface);
```

Headings:

```css id="4i5z3r"
color: var(--text);
```

Muted Text:

```css id="2o7q1j"
color: var(--muted);
```

Primary Actions:

```css id="v1m8xy"
background: var(--primary);
```

Secondary Actions:

```css id="m7w4ts"
border: 1px solid var(--primary);
```

---

# Palette Generation Rule

For every new project:

1. Analyze industry.
2. Analyze target audience.
3. Analyze desired emotion.
4. Create a unique palette.
5. Explain palette reasoning internally.
6. Never reuse palettes automatically.

Every design should feel intentionally branded.

---

# Final Requirement

A user should never be able to look at two generated websites and say:

"These are obviously AI-generated."

The color system must feel as if it was selected by a senior product designer with years of experience, not by a template generator.
