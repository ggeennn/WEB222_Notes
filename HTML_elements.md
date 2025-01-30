# Common HTML Elements / 常见 HTML 元素

There are many HTML elements you'll learn and use, but the following is a good initial set to get you started.  
有许多 HTML 元素你将学习和使用，但以下是一个良好的初始集合，帮助你入门。

You can see an example page that uses every HTML element here.  
你可以在这里查看一个使用了所有 HTML 元素的示例页面。

## Metadata / 元数据

Information about the document vs. the document's content goes in various metadata elements:  
关于文档的信息与文档内容的区别在于各种元数据元素中：

- `<link>` - links from this document to external resources, such as CSS stylesheets  
  `<link>` - 从此文档链接到外部资源，例如 CSS 样式表。
  
- `<meta>` - metadata that can't be included via other elements  
  `<meta>` - 不能通过其他元素包含的元数据。
  
- `<title>` - the document's title  
  `<title>` - 文档的标题。

## Major Document Sections / 主要文档部分

- `<html>` - the document's root element, containing all other elements  
  `<html>` - 文档的根元素，包含所有其他元素。
  
- `<head>` - machine-readable metadata about the document  
  `<head>` - 关于文档的机器可读元数据。
  
- `<body>` - the document's content  
  `<body>` - 文档的内容。

## Content Sections / 内容部分

These are organizational blocks within the document, helping give structure to the content and provide clues to browsers, screen readers, and other software about how to present the content:  
这些是文档中的组织块，帮助为内容提供结构，并为浏览器、屏幕阅读器和其他软件提供关于如何呈现内容的线索：

- `<header>` - introductory material at the top of a document  
  `<header>` - 文档顶部的介绍性材料。
  
- `<nav>` - content related to navigation (a menu, index, links, etc)  
  `<nav>` - 与导航相关的内容（菜单、索引、链接等）。
  
- `<main>` - the main content of the document. For example, a news article's paragraphs vs. ads, links, navigation buttons, etc.  
  `<main>` - 文档的主要内容。例如，新闻文章的段落与广告、链接、导航按钮等的对比。
  
- `<h1>, <h2>, ..., <h6>` - (sub) headers for different sections of content  
  `<h1>, <h2>, ..., <h6>` - 不同内容部分的（子）标题。
  
- `<footer>` - end material (author, copyright, links)  
  `<footer>` - 结束材料（作者、版权、链接）。

## Text Content / 文本内容

We organize content into "boxes," some of which have unique layout characteristics.  
我们将内容组织成"盒子"，其中一些具有独特的布局特征。

- `<div>` - a generic container we use to attach CSS styles to a particular area of content  
  `<div>` - 一个通用容器我们用它来将 CSS 样式附加到特定内容区域。
  
- `<ol>` - an ordered list (1, 2, 3) of list items  
  `<ol>` - 有序列表（1, 2, 3）的列表项。
  
- `<ul>` - an unordered list (bullets) of list items  
  `<ul>` - 无序列表（项目符号）的列表项。
  
- `<li>` - a list item in an `<ul>` or `<ol>`  
  `<li>` - 在 `<ul>` 或 `<ol>` 中的列表项。
  
- `<p>` - a paragraph  
  `<p>` - 一个段落。
  
- `<blockquote>` - an extended quotation  
  `<blockquote>` - 一个扩展的引用。

## Inline Text / 行内文本

We also use elements within larger text content to indicate that certain words or phrases are to be shown differently:  
我们还在较大的文本内容中使用元素，以指示某些单词或短语应以不同的方式显示：

- `<a>` - an "anchor" element, which will produce a hyperlink, allowing users to click and navigate to some other document.  
  `<a>` - 一个"锚"元素，将生成一个超链接，允许用户点击并导航到其他文档。
  
- `<code>` - formats the text as computer code vs. regular text.  
  `<code>` - 将文本格式化为计算机代码与常规文本的对比。
  
- `<em>` - adds emphasis to the text (often in italics)  
  `<em>` - 为文本添加强调（通常为斜体）。
  
- `<span>` - another generic container, used to define CSS styles  
  `<span>` - 另一个通用容器，用于定义 CSS 样式。

## Multimedia / 多媒体

In addition to text, HTML5 also defines a number of rich media elements:  
除了文本，HTML5 还定义了一些丰富的媒体元素：

- `<img>` - an element used to embed images in a document.  
  `<img>` - 用于在文档中嵌入图像的元素。
  
- `<audio>` - an element used to embed sound in a document.  
  `<audio>` - 用于在文档中嵌入声音的元素。
  
- `<video>` - an element used to embed video in a document  
  `<video>` - 用于在文档中嵌入视频的元素。
  
- `<canvas>` - a graphical area (rectangle) used to draw with either 2D or 3D using JavaScript.  
  `<canvas>` - 一个图形区域（矩形），用于使用 JavaScript 进行 2D 或 3D 绘图。

## Scripting / 脚本

We create dynamic web content and applications through the use of scripting:  
我们通过使用脚本创建动态网页内容和应用程序：

- `<script>` - used to embed executable code in a document, typically JavaScript.  
  `<script>` - 用于在文档中嵌入可执行代码，通常是 JavaScript。