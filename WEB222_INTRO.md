# WEB222 - Week 1: Internet Architecture & JavaScript Basics 📚

## 学习目标 (Learning Objectives) 🎯
完成本周学习后，你应该能够：
1. 理解Internet和Web的基本概念和工作原理
2. 掌握JavaScript的基础语法和使用方法
3. 能够使用开发工具进行基础的Web开发

## 目录 (Table of Contents) 📑
1. [课程概述 (Course Overview)](#1-课程概述-course-overview)
2. [学习路径图 (Learning Path)](#2-学习路径图-learning-path)
3. [Web基础 (Web Fundamentals)](#3-web基础-web-fundamentals)
4. [JavaScript基础 (JavaScript Basics)](#4-javascript基础-javascript-basics)
5. [开发环境 (Development Environment)](#5-开发环境-development-environment)
6. [实践项目 (Practice Projects)](#6-实践项目-practice-projects)
7. [常见问题 (FAQ)](#7-常见问题-faq)
8. [学习资源 (Resources)](#8-学习资源-resources)

## 1. 课程概述 (Course Overview) 📝
### 1.1 课程简介
本周我们将学习：
- Web开发的基础架构 | Web Development Infrastructure
- JavaScript编程语言入门 | JavaScript Programming Basics

### 1.2 先修知识
- 基本的计算机操作能力
- 简单的英语阅读能力
- 基础的逻辑思维能力

### 1.3 学习建议
- 💡 理论学习：先理解概念，再动手实践
- 💻 实践操作：每个概念都要亲自尝试
- 📝 做好笔记：记录重点和难点
- ❓ 及时提问：遇到问题及时解决

## 2. 学习路径图 (Learning Path) 🗺️
```
Web开发基础知识树：
├── Internet基础 ⭐
│   ├── [必修] 网络基础
│   │   ├── Internet概念
│   │   ├── Web工作原理
│   │   └── HTTP/HTTPS协议
│   └── [选修] 网络安全
│       └── 基本安全概念
│
├── JavaScript基础 ⭐
│   ├── [必修] 语言基础
│   │   ├── 变量和数据类型
│   │   ├── 运算符和表达式
│   │   └── 控制结构
│   └── [选修] 高级特性
│       └── 执行环境
│
└── 开发工具 ⭐
    ├── [必修] 基础工具
    │   ├── 浏览器
    │   └── 编辑器
    └── [选修] 进阶工具
        └── Node.js
```

## 3. Web基础 (Web Fundamentals) 📝

### 3.1 Internet与Web概念 🟢
- 定义 | Definition
  ```
  Internet：全球互联的计算机网络系统
  Web：基于Internet的信息服务系统
  ```

- 💡 通俗理解 | Simple Explanation
  ```
  Internet就像城市的道路系统：
  ├── 马路 = 网络线路
  ├── 红绿灯 = 网络协议
  └── 车辆 = 数据包
  
  Web就像建在这个城市里的商店：
  ├── 商店 = 网站
  ├── 商品 = 网页内容
  └── 购物 = 浏览网页
  ```

- 📝 实践示例 | Practice Example
  ```javascript
  // 访问网站的过程
  1. 打开浏览器（像打开导航软件）
  2. 输入网址（像输入目的地）
  3. 等待加载（像等待路线规划）
  4. 查看内容（像到达目的地）
  ```

### 3.2 HTTP协议详解 🟡
- 定义 | Definition
  ```
  HTTP：网页内容传输协议
  HTTPS：加密的HTTP协议
  ```

- 💡 核心概念 | Key Concepts
  ```
  请求方法：
  ├── GET = 获取信息（像查看商品）
  ├── POST = 提交信息（像购买商品）
  ├── PUT = 更新信息（像修改订单）
  └── DELETE = 删除信息（像取消订单）
  
  状态码：
  ├── 2xx = 成功（订单完成）
  ├── 3xx = 重定向（转到新店铺）
  ├── 4xx = 客户端错误（填错信息）
  └── 5xx = 服务器错误（系统故障）
  ```

- 📝 实践示例 | Practice Example
  ```javascript
  // 1. 发送GET请求获取数据
  fetch('https://api.example.com/data')
    .then(response => {
      if (response.status === 200) {
        console.log('数据获取成功');
      } else {
        console.log('获取失败：', response.status);
      }
    })
    .catch(error => console.error('发生错误：', error));

  // 2. 发送POST请求提交数据
  fetch('https://api.example.com/submit', {
    method: 'POST',
    headers: {
      'Content-Type': 'application/json'
    },
    body: JSON.stringify({
      username: 'john_doe',
      email: 'john@example.com'
    })
  });
  ```

### 3.3 浏览器是如何工作的？(How Browsers Work) 🟡
- 💡 通俗理解 | Simple Explanation
  ```
  浏览器就像一个翻译官：
  ├── 收到网页文件（像收到外语书）
  ├── 翻译内容（看懂文字）
  ├── 排版美化（整理格式）
  └── 展示给你（让你看懂）
  ```

- 📝 主要组件 | Main Components
  ```
  浏览器的组成部分：
  ├── 地址栏（像导航栏）
  ├── 显示区域（像电视屏幕）
  ├── 书签栏（像收藏夹）
  └── 开发工具（像维修工具）
  ```

## 4. JavaScript基础 (JavaScript Basics) 📝

### 4.1 认识JavaScript 🟢
- 💡 什么是JavaScript？
  ```
  就像乐高积木：
  ├── 基础积木 = 基本语法
  ├── 搭建说明 = 编程规则
  └── 完成作品 = 程序功能
  ```

- 📝 为什么学JavaScript？
  ```
  因为JavaScript可以：
  ├── 让网页动起来（像给图片加动画）
  ├── 响应用户操作（像点击按钮）
  ├── 处理数据（像计算成绩）
  └── 制作游戏（像简单的网页游戏）
  ```

### 4.2 JavaScript基础语法 🟢

#### 4.2.1 变量和数据类型
```javascript
// 变量就像是一个盒子，可以存放不同的东西
let age = 16;              // 数字（年龄）
let name = "小明";         // 文本（名字）
let isStudent = true;      // 真/假（是否是学生）
let hobbies = ["读书", "打球", "游戏"];  // 列表（爱好）

// const用来存放不会改变的值
const PI = 3.14159;        // 圆周率永远不变
```

#### 4.2.2 基本运算
```javascript
// 1. 数学运算
let score1 = 85;
let score2 = 92;
let average = (score1 + score2) / 2;  // 计算平均分

// 2. 文本操作
let firstName = "小";
let lastName = "明";
let fullName = firstName + lastName;   // 连接姓名

// 3. 比较运算
let age = 16;
let canVote = age >= 18;              // 判断是否可以投票
```

### 4.3 实用小程序示例 🟢

#### 4.3.1 成绩计算器
```javascript
// 计算总分和平均分
let chinese = 89;
let math = 95;
let english = 90;

let total = chinese + math + english;
let average = total / 3;

console.log("总分：" + total);
console.log("平均分：" + average);
```

#### 4.3.2 简单游戏
```javascript
// 猜数字游戏
let secretNumber = 7;
let guess = 5;

if (guess === secretNumber) {
    console.log("恭喜你猜对了！");
} else if (guess < secretNumber) {
    console.log("猜小了，再试试！");
} else {
    console.log("猜大了，再试试！");
}
```

## 5. 开发工具入门 (Development Tools) 🛠️

### 5.1 浏览器开发工具 🟢
- 💡 为什么需要开发工具？
  ```
  就像修理工具箱：
  ├── 检查网页（像用放大镜）
  ├── 找出问题（像用测试仪）
  └── 修改调试（像用螺丝刀）
  ```

### 5.2 第一个程序 🟢
```javascript
// 1. 打开浏览器的开发者工具（F12）
// 2. 找到"控制台"(Console)标签
// 3. 输入下面的代码：

console.log("你好，世界！");
alert("这是我的第一个程序！");
```

## 6. 练习项目 (Practice Projects) 💻

### 6.1 简单计算器
```javascript
// 创建一个简单的计算器
function add(a, b) {
    return a + b;
}

function subtract(a, b) {
    return a - b;
}

// 测试计算器
console.log("3 + 5 = " + add(3, 5));
console.log("10 - 7 = " + subtract(10, 7));
```

### 6.2 个人介绍生成器
```javascript
// 创建一个自我介绍生成器
let myName = "小明";
let myAge = 16;
let myHobbies = ["读书", "打球", "编程"];

function generateIntroduction() {
    return "大家好！我叫" + myName + 
           "，今年" + myAge + "岁。" +
           "我的爱好是：" + myHobbies.join("、");
}

console.log(generateIntroduction());
```

## 7. 常见问题解答 (FAQ) ❓

1. 问：JavaScript很难学吗？
   - 答：不会很难！就像学习一门新的语言，循序渐进就可以了。

2. 问：我需要很多数学知识吗？
   - 答：基础的数学知识就够了，主要需要逻辑思维能力。

3. 问：犯错误了怎么办？
   - 答：这很正常！每个程序员都是在犯错中学习的。重要的是学会如何找出和修复错误。

## 8. 学习资源 (Resources) 📚

### 8.1 入门教程
- MDN Web Docs（中文版）
- W3School 中文教程
- 菜鸟教程

### 8.2 练习平台
- FreeCodeCamp（有中文版）
- CodePen（可以直接在线写代码）
- JavaScript.info（有中文版）

## 版本控制 (Version Control) 🔄
```markdown
更新日期：2024-01-15
版本号：v2.1
更新内容：
- 添加更多生活化例子
- 简化技术概念
- 增加实践项目
- 补充常见问题
```

[End of Document]