# OG Image Social Sharing Best Practices

## How OG Images Work

When a URL is shared on social media, the platform fetches Open Graph meta tags:
```html
<meta property="og:image" content="https://example.com/og.png" />
<meta property="og:title" content="Page Title" />
<meta property="og:description" content="Description" />
```

The image appears as a visual preview card. A good OG image dramatically increases click-through from social shares.

## Platform Requirements

| Platform | Recommended size | Aspect ratio | Notes |
|----------|-----------------|-------------|-------|
| Twitter/X | 1200x630 | 1.91:1 | Uses `twitter:image` or falls back to `og:image` |
| Facebook | 1200x630 | 1.91:1 | Standard OG image |
| LinkedIn | 1200x627 | ~1.91:1 | Very similar to Facebook |
| Slack | 1200x630 | 1.91:1 | Unfurls link with OG image |
| Discord | 1200x630 | 1.91:1 | Embed card with image |
| iMessage | 1200x630 | 1.91:1 | Link preview bubble |
| WhatsApp | 1200x630 | 1.91:1 | Link preview card |

**1200x630 is the universal safe size.** It works everywhere without cropping.

## OG Image Strategies

### Static (one image for entire site)
- Simple: one OG image in the root
- Good for: Landing pages, single-product sites
- Limitation: every shared page looks the same

### Per-page (template + variables)
- Generate unique OG image per page using a template
- Variables: title, author, date, category
- Good for: Blogs, docs, multi-page sites
- Best approach for most websites

### Dynamic (on-demand generation)
- Generate OG image at request time via API
- Cache with long TTL
- Good for: User-generated content, dashboards, profiles
- Rendshot API as the generation backend

## CTR Impact

- Posts with OG images get **2-3x more clicks** than those without
- Custom OG images outperform auto-generated screenshots by ~40%
- Consistent branded OG images build recognition across repeated shares

## Common Mistakes

1. **No OG image at all** — Platform shows a generic gray card or nothing
2. **Wrong aspect ratio** — Image gets cropped awkwardly (square images lose top/bottom)
3. **Too much text** — Platforms show title + description below the image; don't repeat
4. **Tiny text** — Preview is often ~600x315px; text must be large
5. **Dark image + dark card background** — Edges disappear on dark mode platforms
6. **Slow loading** — Large PNG files delay card rendering. Use JPG for OG images
7. **Missing meta tags** — `og:image` must be an absolute URL, not relative
8. **Cache issues** — Social platforms cache OG images aggressively. Use unique URLs when updating

## Technical Checklist

- Format: JPG preferred (smaller file, faster unfurl)
- Size: 1200x630px
- File size: Under 1MB (under 300KB ideal)
- URL: Absolute, HTTPS, publicly accessible
- Cache headers: Set appropriate cache duration
- Validation: Use Facebook Sharing Debugger, Twitter Card Validator to test
