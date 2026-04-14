# OG Image Visual Design Guide

## Design Principles

OG images are seen in a feed context — they must communicate quickly and stand out.

### Key constraints:
- Viewed at ~600x315px or smaller (half the actual size)
- Surrounded by platform UI (text, buttons, other posts)
- Paired with og:title and og:description text (don't duplicate)
- Must work on both light and dark mode platforms

## Style Categories

### 1. Branded Blog Post — Most common use case
- Brand colors as background
- Page title as primary text
- Author name/avatar (optional)
- Site logo anchor
- Consistent across all posts

### 2. Product / Landing Page
- Product name + tagline
- Key visual or product screenshot
- Brand colors, minimal text
- Logo prominently placed

### 3. Documentation / Technical
- Section title + breadcrumb
- Code-style font for technical terms
- Muted professional palette
- Consistent template for all docs pages

### 4. Personal Site / Portfolio
- Name + title/tagline
- Headshot or avatar
- Warm, personal palette
- Unique but simple design

### 5. SaaS Dashboard / App
- App name + page context
- Mini screenshot or illustration
- Trust-building design (clean, professional)
- Dark theme often works well

## Color Palettes

### Developer / Tech
- Background: Dark `#0F1419` or Indigo `#1A1A2E`
- Text: White `#FFFFFF`
- Accent: Cyan `#00BCD4` or Green `#4CAF50`

### Blog / Content
- Background: Brand primary color or gradient
- Text: White or contrasting
- Accent: Brand secondary

### Corporate / SaaS
- Background: Navy `#1A2332` or brand dark
- Text: White
- Accent: Brand highlight color

### Personal / Creative
- Background: Warm gradient or photography
- Text: White with shadow for readability
- Accent: Personal brand color

## Typography Rules

### Title Text
- Size: 48-72px (at 1200x630)
- Weight: Bold or Extra-bold
- Max 2 lines, ~50 characters total
- Left-aligned or centered
- Must be readable at 600px width

### Metadata (author, date, site name)
- Size: 20-28px
- Weight: Regular
- Placement: Bottom area or beside logo
- Less prominent than title

### Font Recommendations
- Sans-serif: Inter, DM Sans, Plus Jakarta Sans
- Serif (editorial): Playfair Display, DM Serif Display
- Mono (tech): JetBrains Mono, Fira Code

## Layout Patterns

### Blog Post (most common)
```
┌─────────────────────────────┐
│  [Site Logo]                │
│                             │
│  POST TITLE TEXT            │
│  in bold, 1-2 lines        │
│                             │
│  Author Name · Date         │
└─────────────────────────────┘
```

### Product Landing
```
┌─────────────────────────────┐
│                             │
│  PRODUCT NAME               │
│  Tagline or description     │
│                             │
│  [Product illustration]     │
│                     [Logo]  │
└─────────────────────────────┘
```

### Documentation
```
┌─────────────────────────────┐
│  [Docs Logo]  > Section     │
│                             │
│  PAGE TITLE                 │
│                             │
│  Brief context or           │
│  code snippet preview       │
└─────────────────────────────┘
```

### Personal Site
```
┌─────────────────────────────┐
│                             │
│  [Avatar]  Name Surname     │
│            Title / Role     │
│                             │
│  tagline or site URL        │
└─────────────────────────────┘
```

## Dynamic Template Design

For per-page OG images, design a template with variable zones:

```
┌─────────────────────────────┐
│  {{site_logo}}              │
│                             │
│  {{title}}                  │  ← Variable: page title
│                             │
│  {{author}} · {{date}}      │  ← Variable: metadata
│                     {{tag}} │  ← Variable: category/tag
└─────────────────────────────┘
```

Key rules for templates:
- Keep visual structure fixed, only text content changes
- Test with short titles (3 words) AND long titles (10+ words)
- Ensure text truncation looks clean (ellipsis or line limit)

## Design Anti-Patterns

1. **Repeating the page title**: og:title already shows the title. Image should add visual context
2. **Tiny text**: Unreadable at preview size
3. **No brand anchor**: Viewer can't tell which site this is from
4. **Pure white background**: Disappears on light-mode platforms (no visible card boundary)
5. **Too many elements**: One focal point, clean composition
6. **Screenshot as OG image**: Low quality, hard to read, feels lazy
