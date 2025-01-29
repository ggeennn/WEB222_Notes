# WEB222 - Week 5 - HTML Fundamentals 🌐
==================================
READ UNTIL:
HTML Document
==================================

## 学习路径图 (Learning Path) 📋
1. 开发环境搭建 (Development Environment Setup)
2. HTML基础概念 (HTML Basic Concepts)
3. HTML文档结构 (HTML Document Structure)
4. HTML常用元素 (Common HTML Elements)
5. HTML多媒体与脚本 (HTML Multimedia and Scripting)

## 目录 (Table of Contents) 📑
- [1. 开发环境搭建](#1-开发环境搭建-development-environment-setup)
- [2. HTML基础概念](#2-html基础概念-html-basic-concepts)
- [3. HTML文档结构](#3-html文档结构-html-document-structure)
- [4. HTML常用元素](#4-html常用元素-common-html-elements)
- [5. HTML多媒体与脚本](#5-html多媒体与脚本-html-multimedia-and-scripting)

## 1. 开发环境搭建 (Development Environment Setup) 🟢

### 开发环境三要素 (Three Essential Components) 
- 定义 | Definition
  - 中文解释：Web开发需要的三个基本软件组件
  - English Definition: Three basic software components needed for web development

- 组件清单 | Component List
  1. 代码编辑器 (Code Editor)
     - Visual Studio Code
     - 特点：免费、开源、跨平台
  
  2. Web浏览器 (Web Browser)
     - Chrome
     - Firefox
     - Edge
     - Safari
     - Opera
  
  3. Web服务器 (Web Server)
     - Node.js based HTTP server
     - 使用npx serve命令启动

### Web服务器设置 (Web Server Setup) 🟢
- 步骤 | Steps
  1. 安装Node.js
  2. 创建项目目录
  3. 使用npx serve启动服务器

- 示例 | Example
```bash
cd my-website
npx serve
# 服务器将在 http://localhost:3000 启动
```

- 💡服务器特点
  - 使用HTTP协议
  - 默认端口3000
  - localhost (127.0.0.1) 本地访问

## 2. HTML基础概念 (HTML Basic Concepts) 🟢

### HTML (HyperText Markup Language) 
- 定义 | Definition
  - 中文解释：超文本标记语言，用于构建和呈现网页内容的标准标记语言
  - English Definition: Standard markup language for creating and presenting web pages

### HTML核心概念 (Core Concepts) 🟢
1. 内容 (Content)
   - 定义：文档中的实际文本内容
   - 特点：可以直接书写

2. 标签 (Tag) 
   - 定义：用 `<` 和 `>` 包围的特殊文本
   - 示例：`<p>`, `<img>`

3. 元素 (Element)
   - 定义：从开始标签到结束标签的所有内容
   - 示例：`<h1>Chapter 1</h1>`

4. 属性 (Attribute)
   - 定义：元素的额外特性
   - 格式：`name` 或 `name="value"`
   - 示例：`<p id="error-message" hidden>`

5. 实体 (Entity)
   - 定义：以 `&` 开始，`;` 结束的特殊字符
   - 示例：
     - `&lt;` 表示 `<`
     - `&nbsp;` 表示空格
     - `&amp;` 表示 `&`

## 3. HTML文档结构 (HTML Document Structure) 🟢

### HTML5基本结构 (HTML5 Basic Structure)
```html
<!doctype html>
<html>
    <head>
        <meta charset="utf-8">
        <title>My Web Page</title>
    </head>
    <body>
        <!-- 这是注释 -->
        <h1>Hello World!</h1>
    </body>
</html>
```

### 文档结构解析 (Document Structure Analysis) 🟢
1. `<!doctype html>`
   - 定义：声明文档类型为HTML5
   - 作用：告诉浏览器如何解释和渲染文档

2. `<html>`
   - 定义：文档的根元素
   - 作用：包含所有其他HTML元素

3. `<head>`
   - 定义：文档的元数据部分
   - 作用：提供关于文档的信息

4. `<meta charset="utf-8">`
   - 定义：定义文档的字符编码
   - 作用：确保文本正确显示

5. `<title>`
   - 定义：文档的标题
   - 作用：显示在浏览器标题栏

6. `<body>`
   - 定义：文档的主体部分
   - 作用：包含所有可见内容

## 4. HTML常用元素 (Common HTML Elements) 🟡

### 元数据元素 (Metadata Elements)
- `<link>`：链接外部资源
- `<meta>`：定义元数据
- `<title>`：定义文档标题

### 主要文档区块 (Major Document Sections)
- `<html>`：根元素
- `<head>`：文档头部
- `<body>`：文档主体

### 内容区块 (Content Sections) 
- `<header>`：页眉
- `<nav>`：导航
- `<main>`：主要内容
- `<h1>` 到 `<h6>`：标题层级
- `<footer>`：页脚

### 文本内容 (Text Content)
- `<div>`：通用容器
- `<ol>`：有序列表
- `<ul>`：无序列表
- `<li>`：列表项
- `<p>`：段落
- `<blockquote>`：引用块

### 内联文本 (Inline Text)
- `<a>`：超链接
- `<code>`：代码
- `<em>`：强调
- `<span>`：内联容器

## 5. HTML多媒体与脚本 (HTML Multimedia and Scripting) 🟡

### 多媒体元素 (Multimedia Elements)
- `<img>`：图片
  - 用途：嵌入图像
  - 属性：src, alt, width, height

- `<audio>`：音频
  - 用途：嵌入音频
  - 属性：src, controls, autoplay

- `<video>`：视频
  - 用途：嵌入视频
  - 属性：src, controls, width, height

- `<canvas>`：画布
  - 用途：绘制图形
  - 特点：需要JavaScript操作

### 脚本元素 (Scripting Elements)
- `<script>`
  - 用途：嵌入或引用JavaScript代码
  - 属性：src, type, async, defer

## 6. 实践示例 (Practice Examples) 💻

### 基本HTML页面创建
1. 创建目录：`my-website`
2. 创建文件：`index.html`
3. 启动服务器：`npx serve`
4. 访问页面：`http://localhost:3000`

### 示例代码
```html
<!doctype html>
<html>
    <head>
        <meta charset="utf-8">
        <title>My First Web Page</title>
    </head>
    <body>
        <h1>Welcome to My Website</h1>
        <p>This is my first HTML page!</p>
    </body>
</html>
```

## 7. 学习建议 (Study Tips) 💡

1. 环境配置
   - 确保所有必要软件已安装
   - 熟悉开发工具的基本使用

2. HTML基础
   - 从基本结构开始学习
   - 理解元素的语义化使用
   - 练习编写规范的HTML代码

3. 实践技巧
   - 多写代码
   - 使用浏览器开发者工具
   - 验证HTML代码的有效性

4. 进阶学习
   - 学习更多HTML5特性
   - 关注Web标准和最佳实践
   - 结合CSS和JavaScript

## 推荐阅读 (Suggested Readings) 📚

- [HTML: HyperText Markup Language on MDN](https://developer.mozilla.org/en-US/docs/Web/HTML)
- [HTML Basics](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/HTML_basics)
- [Learning HTML: Guides and Tutorials](https://developer.mozilla.org/en-US/docs/Learn/HTML)
- [HTML Reference](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference) 