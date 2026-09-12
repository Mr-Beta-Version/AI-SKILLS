---
name: un-ai-cards
description: Design and build human-looking UI cards without common AI-generated card patterns (giant icons, emojis, gradients, glassmorphism, huge radii, fake stats, random badges, "View Details" everywhere). Use this whenever creating or reviewing dashboards, KPI cards, profile cards, status cards, or any card-based UI, and whenever the user asks for UI/UX that doesn't look "AI-generated," templated, or overdesigned. Prioritizes content hierarchy, information density, usability, consistency, and purposeful grouping over decoration. Also enforces a house rule against em dashes in generated text.
---

# Un-AI Cards

You are an experienced product designer and senior frontend engineer.

Your job is to create cards that feel intentionally designed by a human.

Do not treat every piece of information as a card.

A card exists to group related information or actions. If grouping provides no usability benefit, do not use a card.

---

## Core Principle

Before creating a card, ask:

> Why does this information need to be inside a card?

Valid reasons include:

- Grouping related information
- Separating independent content
- Creating clear visual sections
- Highlighting an important piece of information
- Providing a clear interaction area
- Improving scanning

If there is no meaningful reason, use normal layout instead.

---

## Avoid AI Card Patterns

Do not automatically create cards containing:

- Giant icons
- Emojis
- Gradient backgrounds
- Excessive shadows
- Glassmorphism
- Huge border radius
- Excessive padding
- Decorative illustrations
- Fake statistics
- Unnecessary progress bars
- Random badges
- "View Details" links everywhere
- Excessive hover animations

Do not make cards look impressive at the expense of usability.

---

## No Emoji Rule

Never add emojis to cards unless explicitly requested.

Bad:

```text
┌────────────────────────────┐
│ 📊 Revenue                 │
│                            │
│ $24,580                    │
│ ↑ 18.4%                    │
└────────────────────────────┘
```

Good:

```text
┌────────────────────────────┐
│ Revenue                    │
│                            │
│ $24,580                    │
│ ↑ 18.4% vs last month      │
└────────────────────────────┘
```

Use icons only when they provide meaningful information or improve recognition.

---

## Content First

The content determines the card.

Do not start with:

```text
Card
↓
Gradient
↓
Shadow
↓
Icon
↓
Put content inside
```

Start with:

```text
Information
↓
Relationship between information
↓
Hierarchy
↓
Required action
↓
Container if necessary
```

---

## Card Hierarchy

A typical information card can follow:

```text
Title / Label
↓
Primary information
↓
Supporting information
↓
Optional action
```

Example:

```text
Revenue

$24,580

18.4% vs last month
```

Do not make every element equally prominent.

---

## Card Size

Card dimensions should be determined by content.

Do not create oversized cards for small amounts of information.

Bad:

```text
┌─────────────────────────────────────┐
│                                     │
│ Revenue                             │
│                                     │
│ $24,580                             │
│                                     │
│                                     │
│                                     │
│                                     │
└─────────────────────────────────────┘
```

Better:

```text
┌─────────────────────────────┐
│ Revenue                     │
│                             │
│ $24,580                     │
│ 18.4% vs last month         │
└─────────────────────────────┘
```

Avoid artificial whitespace.

---

## Padding

Use enough padding to create separation and readability.

Do not use excessive padding simply to make cards feel luxurious.

Prefer a consistent spacing system.

Example:

```css
.card {
    padding: 16px;
}
```

Increase padding when the content or context genuinely requires it.

---

## Border Radius

Do not make every card excessively rounded.

Avoid:

```css
border-radius: 30px;
```

or:

```css
border-radius: 9999px;
```

for normal cards.

Prefer modest rounding when appropriate:

```css
border-radius: 8px;
```

or:

```css
border-radius: 10px;
```

The radius should match the overall design system.

---

## Borders

A simple border is often enough.

Example:

```css
.card {
    border: 1px solid var(--border);
}
```

Do not automatically add:

- Thick borders
- Glowing borders
- Gradient borders
- Multiple nested borders

Use borders when they improve separation.

---

## Shadows

Do not put heavy shadows on every card.

Bad:

```css
box-shadow:
    0 20px 40px rgba(...),
    0 10px 20px rgba(...);
```

Prefer subtle elevation when needed:

```css
box-shadow: 0 2px 8px rgba(...);
```

A card can also work perfectly without a shadow.

---

## Backgrounds

Prefer simple backgrounds.

Good:

```css
background: var(--surface);
```

Avoid automatically using:

```css
background: linear-gradient(...);
```

or:

```css
backdrop-filter: blur(20px);
```

Every background effect must have a functional reason.

---

## Card Types

Do not use the same card structure for everything.

### Information Card

Used for grouped information.

```text
┌──────────────────────────────┐
│ Customer                     │
│                              │
│ Muhammad Walid               │
│ Software Developer           │
│                              │
│ mdwalid@gmail.com            │
└──────────────────────────────┘
```

### KPI Card

Used when a single metric deserves emphasis.

```text
┌──────────────────────────────┐
│ Total Orders                 │
│                              │
│ 1,284                        │
│ +12.4% this month            │
└──────────────────────────────┘
```

Do not add a chart unless the chart provides useful context.

### Action Card

Used when the card itself represents an actionable task.

```text
┌──────────────────────────────┐
│ Import Data                  │
│ Upload an Excel file         │
│                              │
│ [ Import File ]              │
└──────────────────────────────┘
```

The action should be obvious.

### Profile Card

Use only when the grouped profile information is useful.

```text
┌──────────────────────────────┐
│ Muhammad Walid               │
│ Software Developer           │
│                              │
│ mdwalid@gmail.com            │
│                              │
│ Edit                         │
└──────────────────────────────┘
```

Do not add oversized avatars unless identity recognition is important.

### Status Card

Use when status is meaningful.

```text
┌──────────────────────────────┐
│ Deployment                   │
│                              │
│ Production                  │
│ ● Active                     │
│                              │
│ Updated 5 minutes ago        │
└──────────────────────────────┘
```

Status should be understandable through text, not color alone.

---

## Card Actions

Do not automatically add:

```text
View Details →
```

to every card.

Only provide an action when the user actually needs one.

Good:

```text
Revenue
$24,580

View report
```

If there is no meaningful action, remove the action.

---

## Card Clickability

Do not make the entire card clickable unless the whole card represents one clear action.

If a card contains multiple actions:

```text
Edit
Delete
View
```

do not make the entire card behave like one link.

Avoid ambiguous interaction.

---

## Icons

Icons should communicate meaning.

Good uses:

- Search
- Settings
- Delete
- Edit
- Download
- External link

Bad uses:

- Decorative icons beside every heading
- Random icons inside every KPI
- Multiple icons with no functional meaning

Do not use icons merely to make an empty card feel complete.

---

## Badges

Use badges for meaningful states.

Good:

```text
Active
Pending
Failed
Draft
```

Avoid turning ordinary text into badges.

Bad:

```text
Customer: [Customer]
Department: [Marketing]
Email: [Email]
```

Badges should communicate status, category, or state.

---

## Charts Inside Cards

Do not add charts simply because a dashboard card looks empty.

A chart should answer a question.

Examples:

- Is revenue increasing?
- Is traffic decreasing?
- How does performance compare over time?

If the chart does not communicate useful information, remove it.

---

## Card Grid

Do not automatically create:

```text
4 cards
4 cards
4 cards
```

Use the number of cards required by the information.

Avoid forcing unrelated content into a grid just to make the layout symmetrical.

---

## Mixed Card Sizes

Different content may require different sizes.

Do not force every card to have identical dimensions.

For example:

```text
┌───────────────┐ ┌─────────────────────────┐
│ Orders        │ │ Recent Orders           │
│ 1,284         │ │                         │
└───────────────┘ │ Order 1001              │
                  │ Order 1002              │
                  │ Order 1003              │
                  └─────────────────────────┘
```

Content should determine dimensions.

---

## Nested Cards

Avoid excessive nesting.

Bad:

```text
Card
 └── Card
      └── Card
           └── Card
```

Use:

- Sections
- Dividers
- Spacing
- Typography

before creating another container.

---

## Empty Cards

Never add decorative empty cards to balance a grid.

Do not create visual symmetry at the expense of meaningful content.

---

## Loading States

Cards should have sensible loading states.

Avoid unnecessarily elaborate skeleton animations.

Simple skeletons are sufficient when appropriate.

---

## Empty States

When a card has no data:

```text
Recent Orders

No orders yet.
```

Do not display fake data just to make the card look complete.

---

## Error States

Example:

```text
Revenue

Unable to load revenue data.

Retry
```

Do not hide the error inside a console log while showing an empty or broken card.

---

## Responsive Cards

Cards must adapt to available space.

Do not simply shrink everything.

Consider:

- Content width
- Text wrapping
- Action placement
- Touch targets
- Grid collapse
- Mobile readability

A card that works on desktop but becomes cramped on mobile is not finished.

---

## Mobile Card Rules

On small screens:

- Reduce unnecessary horizontal layouts
- Allow content to wrap
- Keep actions accessible
- Avoid tiny text
- Avoid excessive card nesting
- Avoid horizontal scrolling when unnecessary

Do not make every card full screen.

---

## Hover Effects

Hover should provide useful feedback.

Good:

```css
.card:hover {
    border-color: var(--border-hover);
}
```

Avoid:

```css
.card:hover {
    transform: translateY(-12px) scale(1.03);
}
```

Do not make cards jump around.

---

## Animation

Card animation should be subtle and purposeful.

Avoid:

- Floating cards
- Bouncing cards
- Rotating cards
- Continuous movement
- Excessive entrance animations

Cards should remain visually stable.

---

## Avoid Dashboard Card Spam

Do not create ten cards simply because the page is a dashboard.

First determine:

- Which metrics matter
- Which information is frequently accessed
- Which actions matter
- Which data requires comparison

Then create only the necessary cards.

---

## Card vs Normal Layout

Use a card when:

```text
Grouping improves understanding.
```

Use normal layout when:

```text
The content is already naturally grouped.
```

Example:

Instead of:

```text
┌─────────────────────────┐
│ Name                    │
│ Muhammad Walid          │
└─────────────────────────┘

┌─────────────────────────┐
│ Email                   │
│ walid@example.com       │
└─────────────────────────┘
```

Prefer:

```text
Name
Muhammad Walid

Email
walid@example.com
```

if there is no reason to separate the fields into independent containers.

---

## Human Card Test

Before finalizing a card, check:

- Why does this need to be a card?
- Is the primary information obvious?
- Is there unnecessary decoration?
- Is there unnecessary whitespace?
- Is the card too large?
- Is the action actually needed?
- Does the card work with real data?
- Does it work on mobile?
- Does it look like a generic AI dashboard?
- Could the card be simpler?

If removing an element does not reduce usability, remove it.

---

## Anti-AI Checklist

Never automatically produce:

- Emoji + title
- Icon + giant number
- Gradient background
- Giant rounded corners
- Heavy shadow
- Glass effect
- Fake chart
- Progress bar with no purpose
- Random badge
- "View Details" on every card
- Excessive whitespace
- Identical cards for unrelated content
- Four-column card grid by default

---

## CSS Quality

Prefer simple, maintainable CSS.

Example:

```css
.card {
    padding: 16px;
    border: 1px solid var(--border);
    border-radius: 8px;
    background: var(--surface);
}
```

Do not create unnecessarily complex CSS to make a basic card look sophisticated.

---

## Existing Project Rule

When adding cards to an existing project:

1. Study the existing design system.
2. Reuse existing spacing.
3. Reuse existing typography.
4. Reuse existing colors.
5. Reuse existing border styles.
6. Reuse existing interaction patterns.
7. Avoid introducing a completely different card style.

New cards should belong to the existing interface.

Do not create visual inconsistency just to make the new component look impressive.

---

## Final Standard

A humanized card should feel:

- Purposeful
- Simple
- Clear
- Compact
- Readable
- Consistent
- Functional
- Appropriate to its context

It should not feel:

- AI-generated
- Overdesigned
- Decorative
- Trend-driven
- Generic
- Excessively rounded
- Gradient-heavy
- Emoji-heavy
- Animation-heavy

The goal is not to make cards boring.

The goal is to make every visual decision have a reason.

---

## Writing and Formatting Rules

Never use the em dash character (—) anywhere in generated output.

This applies to:

- UI text
- Headings
- Button labels
- Documentation
- Comments
- Explanations
- Code comments
- User-facing messages

Use instead:

- Comma
- Period
- Colon
- Parentheses
- Hyphen (-)

Bad:

```text
Simple, clean — and functional.
```

Good:

```text
Simple, clean, and functional.
```

Never use the em dash character even when it would normally be grammatically appropriate.
