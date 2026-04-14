# YouTube Thumbnail Recommended Templates

Use `list_templates({ platform: "youtube_thumb" })` to browse all available templates.

## By Video Niche

### Tech / Programming Tutorial
- Search: `list_templates({ platform: "youtube_thumb", q: "tech tutorial coding" })`
- Variables: `title`, `tech_icon`, `bg_color`
- Style: Dark code editor aesthetic

### Product Review
- Search: `list_templates({ platform: "youtube_thumb", q: "review comparison" })`
- Variables: `product_name`, `rating`, `product_image`, `verdict`
- Style: Clean split or centered product

### Vlog / Personal
- Search: `list_templates({ platform: "youtube_thumb", q: "vlog personal" })`
- Variables: `title`, `face_image`, `emotion_bg`
- Style: Face + text

### Finance / Business
- Search: `list_templates({ platform: "youtube_thumb", q: "finance money" })`
- Variables: `amount`, `title`, `chart_direction`
- Style: Big number + context

## Prompt Examples

### Coding Tutorial
```
generate_image({
  prompt: "YouTube thumbnail for a Python tutorial, dark VS Code editor background, large bold yellow text 'PYTHON IN 10 MIN', code snippet visible on left, bright green accent, high contrast for small preview",
  platform: "youtube_thumb",
  locale: "en"
})
```

### Product Review
```
generate_image({
  prompt: "YouTube thumbnail for an iPhone review, clean white background, product photo center, large bold text 'WORTH IT?' in red, rating '8/10' badge in corner, minimal design",
  platform: "youtube_thumb",
  locale: "en"
})
```

### Before/After Transformation
```
generate_image({
  prompt: "YouTube thumbnail split design, left side 'BEFORE' with dull colors, right side 'AFTER' with vibrant colors, bold 'VS' in center, dramatic transformation feel, high contrast",
  platform: "youtube_thumb",
  locale: "en"
})
```

### Finance / Milestone
```
generate_image({
  prompt: "YouTube thumbnail, dark background with green money glow, huge number '$100K' centered, subtitle 'in 12 months' below, upward trending arrow, bold impact font",
  platform: "youtube_thumb",
  locale: "en"
})
```

### Educational Explainer
```
generate_image({
  prompt: "YouTube thumbnail for an explainer video 'How DNS Works', light blue gradient background, simplified network diagram illustration, large bold title text on left, clean educational style",
  platform: "youtube_thumb",
  locale: "en"
})
```
