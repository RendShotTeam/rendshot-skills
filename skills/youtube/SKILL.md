---
name: youtube
description: "Create high-performing YouTube thumbnails optimized for click-through rate. Use when the user mentions: 'YouTube', 'YouTube thumbnail', 'video thumbnail', 'YT thumb', 'YouTube cover', or wants to create thumbnail images for YouTube videos. Combines CTR optimization knowledge, visual design best practices, and Rendshot image generation."
---

# YouTube Thumbnail Generator

Create video thumbnails optimized for click-through rate (CTR) — the single most important factor for YouTube video discovery.

## Workflow

### Step 1: Understand the Video Context

Ask (if not provided):
- What's the video about? (topic + title)
- What niche? (tech, gaming, education, vlog, cooking, fitness)
- What's the emotional hook? (curiosity, shock, transformation, FOMO)
- Face thumbnail or graphic-only?

### Step 2: Apply CTR Optimization

Read [references/algorithm.md](references/algorithm.md) for:
- How thumbnails affect CTR and recommendation
- Proven thumbnail patterns by niche
- A/B testing considerations
- Common CTR-killing mistakes

### Step 3: Apply Visual Style

Read [references/design-style.md](references/design-style.md) for:
- High-contrast design for small preview sizes
- Color psychology for CTR
- Typography that works at 168x94px (mobile preview)
- Face expression and composition rules

### Step 4: Generate with Rendshot

**Standard Thumbnail (1280x720):**
```
generate_image({
  prompt: "YouTube thumbnail for a coding tutorial 'Build an AI App in 10 Minutes', bright yellow background, large bold text, surprised face expression area on right, code editor screenshot on left, high contrast, 3 words max",
  platform: "youtube_thumb",
  locale: "en"
})
```

**Face-based Thumbnail:**
```
generate_image({
  prompt: "YouTube thumbnail, dramatic dark background with spotlight, large text 'I QUIT MY JOB', red and white color scheme, face photo area on right side with shocked expression, bold impact font",
  platform: "youtube_thumb"
})
```

**Using templates:**
```
list_templates({ platform: "youtube_thumb", q: "tutorial" })
get_template({ template_id: "tpl_xxx" })
generate_image({ template_id: "tpl_xxx", variables: { ... } })
```

### Step 5: Save for Series Consistency

```
create_template({
  name: "Coding Tutorial Thumb",
  html: "<returned html>",
  variables: [...],
  platform: "youtube_thumb",
  tags: ["coding", "tutorial", "tech"]
})
```

## Format Quick Reference

| Format | Platform preset | Size | Aspect ratio |
|--------|----------------|------|-------------|
| Thumbnail | `youtube_thumb` | 1280x720 | 16:9 |

## Key Principles

- **3-word rule**: Max 3-4 large words on a thumbnail. It must be readable at 168x94px (mobile).
- **High contrast**: The thumbnail competes with dozens of others. Bold colors, sharp edges.
- **Face = CTR**: Thumbnails with expressive human faces get 30-40% higher CTR.
- **Complement the title**: Thumbnail and title should tell different parts of the story, not repeat each other.
- **Avoid clutter**: One focal point, one emotion, one message.

## References

- [CTR optimization and algorithm](references/algorithm.md) — how thumbnails drive discovery, proven patterns
- [Visual design guide](references/design-style.md) — color psychology, typography at small sizes, composition
- [Recommended templates](references/templates.md) — curated templates by video niche
