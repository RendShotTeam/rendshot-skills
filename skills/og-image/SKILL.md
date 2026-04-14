---
name: og-image
description: "Create Open Graph (OG) images for websites, blogs, and web applications. Use when the user mentions: 'OG image', 'Open Graph', 'social preview', 'link preview image', 'meta image', 'social card', 'share image', or wants to create images that appear when URLs are shared on social media. Combines SEO/social sharing best practices, visual design guidelines, and Rendshot image generation."
---

# OG Image Generator

Create Open Graph images that appear when URLs are shared on Twitter, Facebook, LinkedIn, Slack, Discord, and other platforms.

## Workflow

### Step 1: Understand the Page Context

Ask (if not provided):
- What type of page? (blog post / landing page / product page / docs / personal site)
- Dynamic or static? (one OG image for all pages, or unique per page?)
- Brand guidelines? (colors, fonts, logo)

### Step 2: Apply Social Sharing Best Practices

Read [references/algorithm.md](references/algorithm.md) for:
- How OG images affect click-through on each platform
- Size and format requirements per platform
- Dynamic OG image strategies
- Common mistakes that break previews

### Step 3: Apply Visual Style

Read [references/design-style.md](references/design-style.md) for:
- Layout patterns by page type
- Typography for readability at small preview sizes
- Brand integration guidelines
- Background patterns and visual interest

### Step 4: Generate with Rendshot

**Blog Post OG:**
```
generate_image({
  prompt: "OG image for a technical blog post titled 'Understanding React Server Components', dark gradient background, large white title text, author avatar area bottom-left, site logo top-right, clean modern design",
  platform: "og_image",
  locale: "en"
})
```

**Landing Page OG:**
```
generate_image({
  prompt: "OG image for a SaaS product landing page, product name 'Rendshot' centered, tagline 'HTML to Image API', brand green accent on dark background, minimal and professional",
  platform: "og_image"
})
```

**Dynamic Template (for per-page OG images):**
```
create_template({
  name: "Blog OG Image",
  html: "<div style='...'>{{title}}<br><small>{{author}} · {{date}}</small></div>",
  variables: [
    { key: "title", type: "text", label: "Post Title", default: "Blog Post Title", maxLength: 80 },
    { key: "author", type: "text", label: "Author", default: "Author Name" },
    { key: "date", type: "text", label: "Date", default: "2026-01-01" }
  ],
  platform: "og_image",
  tags: ["blog", "og", "dynamic"]
})

// Then generate per page
generate_image({
  template_id: "tpl_blog_og",
  variables: { title: "Understanding RSC", author: "Jane Doe", date: "2026-04-14" }
})
```

**Using existing templates:**
```
list_templates({ platform: "og_image", q: "blog" })
get_template({ template_id: "tpl_xxx" })
generate_image({ template_id: "tpl_xxx", variables: { ... } })
```

## Format Quick Reference

| Format | Platform preset | Size | Aspect ratio |
|--------|----------------|------|-------------|
| OG Image | `og_image` | 1200x630 | ~1.91:1 |

This single size works across all major platforms: Twitter, Facebook, LinkedIn, Slack, Discord, iMessage.

## Key Principles

- **1200x630 is universal**: Works as OG image across all platforms. No need for separate sizes.
- **Readable at small sizes**: OG images are often previewed at ~600x315. Large text, high contrast.
- **Title is the hero**: Page title should be the dominant element. Keep subtitle/metadata small.
- **Brand anchor**: Include logo or site name for source recognition at a glance.
- **Template-first for blogs**: Use a reusable template with variables for consistent per-page OG images.
- **Use JPG**: `format: "jpg"` + `quality: 85` for OG images — smaller file means faster social card rendering.

## References

- [Social sharing best practices](references/algorithm.md) — platform requirements, dynamic OG strategies
- [Visual design guide](references/design-style.md) — layout patterns, typography, brand integration
- [Recommended templates](references/templates.md) — curated templates by page type
