# html2canvas

[![GitHub stars](https://img.shields.io/github/stars/niklasvh/html2canvas.svg?style=social)](https://github.com/niklasvh/html2canvas)
[![npm version](https://img.shields.io/npm/v/html2canvas.svg)](https://www.npmjs.com/package/html2canvas)
[![npm downloads](https://img.shields.io/npm/dm/html2canvas.svg)](https://www.npmjs.com/package/html2canvas)
[![MIT License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

> **Screenshots with JavaScript** - 使用 JavaScript 将 HTML 元素渲染为 Canvas 图像

## 简介

html2canvas 是一个 JavaScript 库，它允许你在客户端（浏览器端）将 HTML 元素"截图"为 Canvas 图像。该脚本通过读取 DOM 和元素的样式信息，将其绘制到 Canvas 上，而不会实际截取屏幕，而是在用户浏览器中构建相同页面的表示形式。

## 特性

- 🎨 支持大多数 HTML 元素
- 🖼️ 将 HTML/CSS 渲染为 Canvas 图像
- 📱 响应式设计支持
- 🔧 可配置的渲染选项
- 🌐 跨浏览器兼容
- 📦 支持 NPM 和 Yarn 安装

## 快速开始

### 安装

#### 使用 NPM
```bash
npm install --save html2canvas
```

#### 使用 Yarn
```bash
yarn add html2canvas
```

#### 直接下载
- [html2canvas.js](/dist/html2canvas.js) (开发版本)
- [html2canvas.min.js](/dist/html2canvas.min.js) (压缩版本，约 24KB gzipped)

### 基本用法

```html
<!-- HTML -->
<div id="capture" style="padding: 10px; background: #f5da55">
    <h4 style="color: #000;">Hello world!</h4>
</div>
```

```javascript
// JavaScript
html2canvas(document.querySelector("#capture")).then(canvas => {
    document.body.appendChild(canvas)
});
```

### CDN 使用

```html
<script src="https://html2canvas.hertzen.com/dist/html2canvas.min.js"></script>
```

## 文档

详细文档和使用指南请访问：
- [完整文档](/documentation)
- [配置选项](/configuration)
- [常见问题 FAQ](/faq)
- [功能特性](/features)
- [入门指南](/getting-started)

## 示例

### 基础截图
```javascript
html2canvas(document.body).then(function(canvas) {
    document.body.appendChild(canvas);
});
```

### 带配置选项
```javascript
html2canvas(document.body, {
    width: window.innerWidth,
    height: window.innerHeight,
    scale: window.devicePixelRatio,
    useCORS: true
}).then(function(canvas) {
    document.body.appendChild(canvas);
});
```

### 导出为图片
```javascript
html2canvas(document.querySelector("#capture")).then(canvas => {
    // 转换为图片 URL
    const imgURL = canvas.toDataURL("image/png");
    
    // 或下载图片
    const link = document.createElement('a');
    link.download = 'screenshot.png';
    link.href = canvas.toDataURL("image/png");
    link.click();
});
```

## 配置选项

| 选项 | 类型 | 默认值 | 说明 |
|------|------|--------|------|
| `width` | Number | 元素宽度 | 画布宽度 |
| `height` | Number | 元素高度 | 画布高度 |
| `scale` | Number | devicePixelRatio | 缩放比例 |
| `useCORS` | Boolean | false | 是否允许跨域图片 |
| `backgroundColor` | String | #ffffff | 背景颜色 |
| `ignoreElements` | String | .data-html2canvas-ignore | 忽略的选择器 |
| `logging` | Boolean | true | 是否启用日志 |

## 浏览器支持

- Chrome
- Firefox 3.5+
- IE9+
- Safari
- Opera
- Edge

## 注意事项

- html2canvas 不会实际截取屏幕，而是在浏览器中重新渲染页面
- 某些 CSS 属性可能不被完全支持
- 跨域图片需要服务器支持 CORS
- 复杂页面可能影响性能

## 项目结构

```
/
├── dist/                    # 编译后的库文件
│   ├── html2canvas.js       # 开发版本
│   └── html2canvas.min.js   # 压缩版本
├── documentation/           # 文档页面
├── getting-started/         # 入门指南
├── features/                # 功能特性
├── configuration/           # 配置说明
├── faq/                     # 常见问题
├── proxy/                   # 代理相关
├── index.html               # 主页
└── README.md                # 项目说明
```

## 相关链接

- [官方网站](https://html2canvas.hertzen.com)
- [GitHub 仓库](https://github.com/niklasvh/html2canvas)
- [NPM 包](https://www.npmjs.com/package/html2canvas)
- [作者网站](https://hertzen.com)

## 许可证

MIT License © [Niklas von Hertzen](https://hertzen.com)

## 贡献

欢迎提交 Issue 和 Pull Request！

---

**Created by Niklas von Hertzen** - Licensed under the MIT License
