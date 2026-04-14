# WeChat Official Account Recommended Templates

Use `list_templates({ platform: "wechat_cover" })` 或 `list_templates({ platform: "wechat_thumb" })` to browse all available templates.

## 按账号类型

### 科技 / 互联网
- Search: `list_templates({ platform: "wechat_cover", q: "tech science" })`
- Variables: `title`, `subtitle`, `bg_color`, `icon`
- Style: 简约专业型

### 生活 / 美食
- Search: `list_templates({ platform: "wechat_cover", q: "lifestyle food" })`
- Variables: `title`, `main_image`, `overlay_color`
- Style: 图文并茂型

### 企业 / 品牌
- Search: `list_templates({ platform: "wechat_cover", q: "brand corporate" })`
- Variables: `title`, `company_logo`, `brand_color`
- Style: 品牌强化型

### 次条缩略图
- Search: `list_templates({ platform: "wechat_thumb" })`
- Variables: `icon`, `bg_color`
- Style: 纯图标/色块

## Prompt 示例

### 科技文章头条
```
generate_image({
  prompt: "微信公众号头条封面，科技主题，深蓝渐变背景，白色大标题'AI Agent 开发实战指南'，底部有淡蓝色光效装饰，简洁专业风格，无多余元素",
  platform: "wechat_cover",
  locale: "zh"
})
```

### 生活方式头条
```
generate_image({
  prompt: "微信公众号头条封面，温暖生活风格，奶油色背景，左侧标题'周末厨房·三道快手早餐'，右侧留出食物摄影区域，暖棕色调，手写风装饰元素",
  platform: "wechat_cover",
  locale: "zh"
})
```

### 行业报告头条
```
generate_image({
  prompt: "微信公众号头条封面，数据报告风格，深色背景白色标题'2026 SaaS 行业趋势报告'，简洁的上升趋势线图装饰，蓝灰色专业配色",
  platform: "wechat_cover",
  locale: "zh"
})
```

### 品牌公告
```
generate_image({
  prompt: "微信公众号头条封面，品牌公告风格，公司品牌蓝为主色，居中大标题'新产品发布'，副标题'重新定义开发者体验'，Logo 占位区域左上角",
  platform: "wechat_cover",
  locale: "zh"
})
```

### 次条缩略图
```
generate_image({
  prompt: "微信公众号次条缩略图，200x200正方形，蓝色渐变背景，中央一个白色简洁的代码括号图标 </>，无文字，干净简约",
  platform: "wechat_thumb",
  locale: "zh"
})
```
