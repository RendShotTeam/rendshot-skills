# YouTube Thumbnail Visual Design Guide

## The 168x94 Rule

YouTube thumbnails appear at various sizes:
- Mobile home feed: ~168x94px
- Desktop sidebar: ~168x94px
- Desktop home: ~360x202px
- Full preview: 1280x720px

**Design for 168x94px first.** If text is unreadable at that size, it fails.

## Color Psychology for CTR

| Color | Emotion | Use case |
|-------|---------|----------|
| Red `#FF0000` | Urgency, excitement | Alerts, drama, reactions |
| Yellow `#FFD600` | Energy, optimism | Tutorials, tips, positive content |
| Blue `#2196F3` | Trust, calm | Educational, tech, reviews |
| Green `#4CAF50` | Growth, money | Finance, success, nature |
| Orange `#FF9800` | Enthusiasm, creativity | Creative content, food |
| Black `#000000` | Premium, serious | Luxury, cinematic, dark topics |
| White `#FFFFFF` | Clean, minimal | Apple-style, minimalist creators |

**Pro tip**: Use colors that contrast with YouTube's UI. Red and yellow stand out against both light and dark mode.

## Typography Rules

### Text on Thumbnails
- **Max 3-4 words**: "BUILD AN APP" not "How to Build a Full-Stack Web Application"
- **Font size**: 80-120px (at 1280x720) to be readable at 168px wide
- **Weight**: Extra-bold or black weight only
- **Font**: Impact, Bebas Neue, Montserrat Black, Oswald Bold
- **Outline or shadow**: Always add text stroke or drop shadow for contrast
- **Color**: White or yellow text on dark backgrounds, black on bright backgrounds

### Text Placement
- Keep text in the LEFT 2/3 of the frame (right side has timestamp overlay)
- Avoid bottom-right corner (duration badge covers it)
- Top area or center works best

## Composition Patterns

### Face + Text (Most Common)
```
┌──────────────────────────────┐
│  BIG TEXT     │              │
│  here         │   FACE       │
│               │   (emotion)  │
│               │              │
└──────────────────────────────┘
```

### Split / Before-After
```
┌──────────────────────────────┐
│              │               │
│   BEFORE     │    AFTER      │
│              │               │
│         ←  VS  →            │
└──────────────────────────────┘
```

### Centered Impact
```
┌──────────────────────────────┐
│                              │
│        BIG NUMBER            │
│        or STATEMENT          │
│        context line          │
│                              │
└──────────────────────────────┘
```

### Mystery / Arrow
```
┌──────────────────────────────┐
│                              │
│    TEXT    ──→  🔴           │
│               (blurred       │
│                element)      │
│                              │
└──────────────────────────────┘
```

## Niche-Specific Styles

### Tech / Programming
- Dark code editor background
- Syntax-highlighted code snippet
- Bright accent color (green terminal, blue UI)
- Logo/framework icon as visual anchor

### Gaming
- In-game screenshot with overlaid text
- Bright, saturated colors
- Character/avatar prominence
- Energy and motion feel

### Educational / Explainer
- Clean background (white, light blue, gradient)
- Concept diagram or illustration
- Clear text hierarchy
- Trustworthy, authoritative feel

### Vlog / Lifestyle
- High-quality photo as base
- Expressive face
- Minimal text (let the emotion speak)
- Warm color grading

### Finance / Business
- Clean professional look
- Dollar signs, charts, or numbers
- Trust colors (navy, green)
- Metric/stat as focal point

## Design Anti-Patterns

1. **Unreadable text at mobile size**: The #1 mistake. Test at 168px wide
2. **Text in bottom-right**: Hidden by duration badge
3. **Low-contrast text**: Gets lost against background
4. **Cluttered image**: Multiple subjects, multiple text blocks
5. **Thin fonts**: Disappear at small sizes. Always use bold/black weight
6. **Borders/frames**: Waste precious pixel space at small sizes
7. **Multiple text colors**: Chaotic. Stick to 1-2 text colors max
