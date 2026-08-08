---
name: glassy-design
description: Generate premium glassmorphism interfaces with modern SaaS aesthetics, translucent surfaces, layered depth, backdrop blur, soft lighting, and production-ready HTML, CSS, and JavaScript. Use when designing dashboards, landing pages, admin panels, portfolio sites, analytics tools, fintech apps, AI products, or any modern UI requiring a polished glass effect.
---

# Glassy Design System

## Core Mission

Create visually stunning glassmorphism interfaces that look premium, modern, and production-ready.

Every UI must feel:
- Clean
- Spacious
- Elegant
- Futuristic
- Professional

Avoid beginner-level glassmorphism.

## Visual Principles

### Layered Depth

Always build at least 3 visual layers:

1. Background layer
2. Ambient light layer
3. Glass surface layer

Example:

- Gradient background
- Blurred glowing orbs
- Glass cards above everything

### Glass Surface Rules

Every glass element must contain:

```css
background: rgba(255,255,255,0.08);
backdrop-filter: blur(20px);
-webkit-backdrop-filter: blur(20px);

border: 1px solid rgba(255,255,255,0.15);

box-shadow:
0 8px 32px rgba(0,0,0,0.2),
inset 0 1px 0 rgba(255,255,255,0.2);
```

Never use solid backgrounds unless specifically requested.

## Color System

Preferred palettes:

### Blue Glass

```css
#60a5fa
#2563eb
#0f172a
#e2e8f0
```

### Purple Glass

```css
#c084fc
#8b5cf6
#1e1b4b
#f5f3ff
```

### Cyan Glass

```css
#22d3ee
#06b6d4
#083344
#ecfeff
```

### Dark Luxury

```css
#0f172a
#111827
#1e293b
#f8fafc
```

## Typography

Preferred fonts:

- Inter
- Geist
- Poppins
- Manrope

Rules:

- Large headlines
- Strong hierarchy
- Generous spacing
- Minimal text density

Example:

```css
h1 {
font-size: clamp(3rem, 8vw, 6rem);
font-weight: 800;
}
```

## Cards

Cards should never look flat.

Required:

```css
border-radius: 24px;
backdrop-filter: blur(20px);

transition: all .35s ease;
```

Hover:

```css
transform: translateY(-6px);
```

Add subtle lighting changes on hover.

## Buttons

Buttons must feel premium.

Primary button:

```css
background:
linear-gradient(
135deg,
#60a5fa,
#2563eb
);

box-shadow:
0 10px 30px rgba(37,99,235,.35);
```

Hover:

```css
transform: translateY(-2px);
```

Never use default HTML buttons.

## Background Effects

Use at least one:

### Gradient Mesh

```css
background:
radial-gradient(circle at top left,#60a5fa,transparent),
radial-gradient(circle at bottom right,#8b5cf6,transparent),
#0f172a;
```

### Glow Orbs

```css
filter: blur(120px);
opacity: .5;
```

### Noise Overlay

Very subtle grain texture.

Opacity:

```css
0.02 - 0.05
```

## Dashboard Rules

For analytics dashboards:

Required:

- KPI cards
- Modern charts
- Glass sidebar
- Floating header
- Smooth hover states

Avoid:

- Heavy borders
- Dense layouts
- Table-heavy designs

## Animation Rules

Animation duration:

```css
200ms - 400ms
```

Preferred effects:

- Fade
- Scale
- Float
- Blur reveal
- Glass shimmer

Avoid:

- Excessive bouncing
- Spinning UI
- Flashing colors

## Mobile Rules

Must be responsive.

Requirements:

- Single-column layouts
- Touch-friendly controls
- Minimum 44px tap targets

## HTML/CSS Output Rules

When generating UI:

1. Produce complete HTML.
2. Include complete CSS.
3. Include JavaScript if interactions exist.
4. Do not use placeholder styling.
5. Do not leave TODO comments.
6. Components must be visually polished.
7. Use semantic HTML.
8. Use CSS variables.
9. Prefer Flexbox and Grid.
10. Ensure accessibility.

## Forbidden Patterns

Do NOT generate:

- Bootstrap-looking layouts
- Generic admin templates
- Gray boxes everywhere
- Sharp corners
- Tiny text
- Flat white cards
- Default browser styles
- Crowded spacing

## Success Criteria

A generated interface should resemble the quality level of:

- Linear
- Stripe
- Raycast
- Vercel
- Framer
- Arc Browser

while maintaining a premium glassmorphism aesthetic.