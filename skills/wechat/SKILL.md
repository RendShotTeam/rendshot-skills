---
name: wechat
description: "Create WeChat Official Account (微信公众号) article covers and thumbnails. Use when the user mentions: '微信', '公众号', '微信公众号', 'WeChat', '公众号封面', '文章封面', '头条封面', '次条封面', or wants to create cover images for WeChat articles. Combines platform content strategy, visual design best practices, and Rendshot image generation."
---

# WeChat Official Account Cover Generator

Create article cover images and thumbnails optimized for WeChat Official Account articles.

## Workflow

### Step 1: Understand the Article Context

Ask (if not provided):
- Article topic and title?
- Position in push? (头条/次条/三条)
- Account type? (个人号/企业号/媒体号)
- Content style? (干货/故事/新闻/观点)

### Step 2: Apply Content Strategy

Read [references/algorithm.md](references/algorithm.md) for:
- Cover position impact (头条 vs 次条)
- Open rate optimization
- Title + cover coordination strategy
- WeChat content ecosystem rules

### Step 3: Apply Visual Style

Read [references/design-style.md](references/design-style.md) for:
- Style by account type and content category
- Color palette for WeChat's UI context
- Typography rules for cover legibility
- Thumbnail (200x200) design at small size

### Step 4: Generate with Rendshot

**头条封面 (900x383):**
```
generate_image({
  prompt: "微信公众号头条封面，标题'2026年值得关注的10个AI趋势'，深蓝科技感背景，白色大标题居中，底部渐变，简洁专业风格",
  platform: "wechat_cover",
  locale: "zh"
})
```

**次条缩略图 (200x200):**
```
generate_image({
  prompt: "微信公众号次条缩略图，简洁图标风格，中央一个AI芯片图标，蓝色渐变背景，无文字",
  platform: "wechat_thumb",
  locale: "zh"
})
```

**Using templates:**
```
list_templates({ platform: "wechat_cover", q: "tech article" })
get_template({ template_id: "tpl_xxx" })
generate_image({ template_id: "tpl_xxx", variables: { ... } })
```

### Step 5: Save for Account Consistency

```
create_template({
  name: "科技公众号头条封面",
  html: "<returned html>",
  variables: [...],
  platform: "wechat_cover",
  tags: ["tech", "wechat", "article"]
})
```

## Format Quick Reference

| Format | Platform preset | Size | Use case |
|--------|----------------|------|----------|
| 头条封面 | `wechat_cover` | 900x383 | First article cover (2.35:1) |
| 次条缩略图 | `wechat_thumb` | 200x200 | Secondary article thumbnail |

## Key Principles

- **头条封面决定打开率**: 900x383 封面是用户在对话列表/朋友圈看到的第一视觉，直接影响点击。
- **次条靠图标**: 200x200 极小尺寸，不要放文字，用图标/色块/表情传达主题。
- **适配深色/浅色模式**: 微信支持深色模式，避免纯白背景（深色下刺眼）。
- **标题与封面互补**: 封面传达情绪/视觉，标题传达信息，不要重复。
- **品牌一致性**: 公众号封面是系列化的，保持色调/字体/排版风格统一。

## References

- [Content strategy and open rate](references/algorithm.md) — WeChat ecosystem, open rate factors, position strategy
- [Visual design guide](references/design-style.md) — cover styles, color palettes, typography, dark mode
- [Recommended templates](references/templates.md) — curated templates by account type
