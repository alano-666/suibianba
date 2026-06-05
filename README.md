# 随便吧 🌿

> 把犹豫交给随机，把心情还给治愈

一个治愈系的选择困难症辅助小工具，支持微信内和浏览器运行。

## ✨ 功能

| 功能 | 说明 |
|------|------|
| 🎲 **随机数字** | 生成 1-100 的随机数，带滚动动画和历史记录 |
| 🎨 **随机颜色** | 60 种现代配色随机抽取，含名称、色值、穿搭场景标签 |
| 🎯 **自定义抽取** | 输入任意选项，随机帮你选一个，带预设模板 |
| 🤖 **AI 助手** | 向 AI 倾诉纠结，获得参考建议（当前为占位演示） |

## 🚀 如何使用

1. 直接双击 `index.html` 在浏览器中打开即可使用
2. 部署到 GitHub Pages 后可获得在线链接，微信也能打开

## 🔧 接入 AI API

AI 助手目前使用预设回复作为演示。要接入真实的 AI：

1. 打开 `index.html`，找到 `sendMessage()` 函数（约第 978 行）
2. 将 `TODO` 注释下方的占位代码替换为你的 API 调用
3. 注释中已预留了 Claude API 的调用示例

支持的 API 示例（任选一个）：

```javascript
// Claude API (Anthropic)
const response = await fetch('https://api.anthropic.com/v1/messages', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
    'x-api-key': 'YOUR_API_KEY',
    'anthropic-version': '2023-06-01'
  },
  body: JSON.stringify({
    model: 'claude-sonnet-4-6',
    max_tokens: 1024,
    messages: [{ role: 'user', content: text }]
  })
});
const data = await response.json();
aiBubble.textContent = data.content[0].text;
```

## 📁 文件结构

```
随便吧/
├── index.html   # 主文件（单文件包含所有 HTML/CSS/JS）
└── README.md    # 本说明
```

## 🎨 设计

- 淡蓝色治愈系渐变背景
- 毛玻璃效果卡片
- 移动端优先的响应式设计
- 微信内置浏览器兼容
