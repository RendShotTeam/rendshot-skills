# OG Image Recommended Templates

Use `list_templates({ platform: "og_image" })` to browse all available templates.

## By Page Type

### Blog Post
- Search: `list_templates({ platform: "og_image", q: "blog post article" })`
- Variables: `title`, `author`, `date`, `site_logo`, `bg_color`
- Style: Branded Blog Post

### Landing Page
- Search: `list_templates({ platform: "og_image", q: "landing product" })`
- Variables: `product_name`, `tagline`, `logo`, `bg_gradient`
- Style: Product / Landing

### Documentation
- Search: `list_templates({ platform: "og_image", q: "docs documentation" })`
- Variables: `title`, `section`, `docs_logo`
- Style: Documentation / Technical

### Personal Site
- Search: `list_templates({ platform: "og_image", q: "personal portfolio" })`
- Variables: `name`, `title`, `avatar`, `tagline`
- Style: Personal / Creative

## Prompt Examples

### Tech Blog
```
generate_image({
  prompt: "OG image for a technical blog post, dark gradient background #0F1419 to #1A1A2E, large white title 'Building AI Agents with TypeScript', author 'Jane Doe' and date at bottom, site logo top-left, clean developer aesthetic, cyan accent color",
  platform: "og_image",
  locale: "en"
})
```

### SaaS Landing Page
```
generate_image({
  prompt: "OG image for a SaaS product, product name 'DataFlow' large and centered, tagline 'Real-time analytics for modern teams' below, abstract data visualization illustration, blue-purple gradient background, professional",
  platform: "og_image",
  locale: "en"
})
```

### Documentation Page
```
generate_image({
  prompt: "OG image for API documentation, dark background, monospace title 'REST API Reference', breadcrumb 'Docs > API > Reference' in small text, code bracket decorations, muted professional blue palette",
  platform: "og_image",
  locale: "en"
})
```

### Open Source Project
```
generate_image({
  prompt: "OG image for an open source project, project name 'rendshot' in bold, description 'HTML to Image API' below, GitHub star count placeholder, dark theme with green accent matching terminal aesthetic",
  platform: "og_image",
  locale: "en"
})
```

### Dynamic Template (reusable)
```
// Create once
create_template({
  name: "Blog OG Template",
  html: "<div style='background:linear-gradient(135deg,#0F1419,#1A237E);width:1200px;height:630px;display:flex;flex-direction:column;justify-content:center;padding:60px;color:white;font-family:Inter,sans-serif'><div style='font-size:20px;opacity:0.7;margin-bottom:16px'>{{site_name}}</div><div style='font-size:52px;font-weight:800;line-height:1.2'>{{title}}</div><div style='margin-top:auto;font-size:20px;opacity:0.7'>{{author}} · {{date}}</div></div>",
  variables: [
    { key: "title", type: "text", label: "Post Title", default: "Blog Post Title", maxLength: 80 },
    { key: "author", type: "text", label: "Author", default: "Author" },
    { key: "date", type: "text", label: "Date", default: "2026-01-01" },
    { key: "site_name", type: "text", label: "Site Name", default: "My Blog" }
  ],
  platform: "og_image",
  tags: ["blog", "og", "dynamic", "template"],
  visibility: "private"
})

// Use per page
generate_image({
  template_id: "tpl_blog_og",
  variables: { title: "Understanding RSC", author: "Jane", date: "2026-04-14", site_name: "DevBlog" },
  format: "jpg",
  quality: 85
})
```
