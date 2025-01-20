# WEB222 - Week 1: Internet Architecture & JavaScript Basics 📚

## 学习目标 (Learning Objectives) 🎯
完成本周学习后，你应该能够：
1. 理解Internet和Web的区别与联系
2. 掌握基本的网络协议知识
3. 了解JavaScript的基础语法
4. 能够使用开发工具进行简单的Web开发

## 目录 (Table of Contents) 📑
1. [Internet基础 (Internet Basics)](#1-internet基础-internet-basics)
2. [Web技术 (Web Technologies)](#2-web技术-web-technologies)
3. [JavaScript入门 (JavaScript Introduction)](#3-javascript入门-javascript-introduction)
4. [开发环境 (Development Environment)](#4-开发环境-development-environment)
5. [实践练习 (Practice Exercises)](#5-实践练习-practice-exercises)

## 1. Internet基础 (Internet Basics) 🟢

### 1.1 Internet与Web的区别 (Internet vs Web)
- 定义 | Definition
  ```
  Internet：全球互联的计算机网络系统
  Web：基于Internet的信息服务系统，使用HTTP协议
  ```

- 💡 通俗理解 | Simple Explanation
  ```
  Internet就像城市的道路系统：
  ├── 道路 = 网络基础设施
  ├── 交通规则 = 网络协议
  └── 车辆 = 数据包
  
  Web就像建在这个城市里的商店：
  ├── 商店 = 网站
  ├── 商品 = 网页内容
  └── 购物 = 浏览网页
  ```

### 1.2 网络协议 (Network Protocols) 🟡
- IP协议 | IP Protocol
  ```
  IPv4：32位地址（如：192.168.1.1）
  IPv6：128位地址（更长的地址格式）
  ```

- DNS系统 | DNS System
  ```
  常用DNS服务器：
  ├── OpenDNS: 208.67.222.222
  ├── Cloudflare: 1.1.1.1
  └── Google: 8.8.8.8
  ```

### 1.3 HTTP/HTTPS协议 🟡
```javascript
// HTTP请求方法
GET     // 获取资源
POST    // 提交数据
PUT     // 更新资源
DELETE  // 删除资源

// HTTP状态码
200  // 成功
404  // 未找到
500  // 服务器错误
```

## 2. Web技术 (Web Technologies) 🟢

### 2.1 Web平台特性 (Web Platform Features)
- 💡 核心优势 | Key Advantages
  ```
  Web平台的特点：
  ├── 无需安装 = 直接访问
  ├── 跨平台 = 到处运行
  ├── 自动更新 = 永远最新
  └── 链接性 = 互联互通
  ```

### 2.2 前端技术栈 (Front-end Stack)
```
核心技术：
├── HTML5 = 结构
├── CSS = 样式
├── JavaScript = 交互
├── DOM = 文档对象模型
└── Web APIs = 浏览器功能接口

扩展技术：
├── 框架（React等）
├── 库（Bootstrap等）
└── 工具（webpack等）
```

### 2.3 URL结构 (URL Structure) 🟢
- 定义 | Definition
  ```
  URL (Uniform Resource Locator)：统一资源定位符，用于定位Web资源
  ```

- 💡 URL组成部分 | URL Components
  ```
  以 https://www.senecacollege.ca/cgi-bin/subject?s1=WEB222 为例：
  
  ├── 协议 (Protocol) = https:
  ├── 域名 (Domain) = www.senecacollege.ca
  ├── 路径 (Path) = /cgi-bin/subject
  └── 查询参数 (Query) = ?s1=WEB222
  ```

## 3. JavaScript入门 (JavaScript Introduction) 🟢

### 3.1 基础语法 (Basic Syntax)
```javascript
// 1. 变量声明
let name = "John";          // 变量
const PI = 3.14159;         // 常量

// 2. 数据类型
let string = "Hello";       // 字符串
let number = 42;            // 数字
let boolean = true;         // 布尔值
let array = [1, 2, 3];      // 数组
let object = {              // 对象
    name: "John",
    age: 30
};
```

### 3.2 运算符 (Operators) 🟡
- 基本运算符 | Basic Operators
  ```javascript
  // 算术运算符
  + - * /    // 加减乘除
  %          // 取余
  ++         // 递增
  --         // 递减
  
  // 比较运算符
  === !==    // 严格相等/不等
  == !=      // 相等/不等（类型转换）
  > < >= <=  // 大于/小于/大于等于/小于等于
  
  // 逻辑运算符
  && || !    // 与/或/非
  ```

### 3.3 控制结构 (Control Structures) 🟢
```javascript
// 1. 条件语句
if (condition) {
    // 代码块
} else if (another_condition) {
    // 代码块
} else {
    // 代码块
}

// 2. 循环语句
for (let i = 0; i < 5; i++) {
    // 重复执行的代码
}

while (condition) {
    // 重复执行的代码
}
```

## 4. 开发环境 (Development Environment) 🟢

### 4.1 浏览器开发工具 (Browser Dev Tools)
- 💡 主要功能 | Main Features
  ```
  开发者工具功能：
  ├── Elements = 检查HTML/CSS
  ├── Console = 运行JavaScript
  ├── Network = 监控网络请求
  ├── Sources = 调试代码
  └── Application = 管理存储
  ```

### 4.2 代码编辑器 (Code Editor)
```
推荐编辑器：
├── Visual Studio Code
├── Sublime Text
└── WebStorm
```

## 5. 实践练习 (Practice Exercises) 💻

### 5.1 基础练习 (Basic Exercises) 🟢
```javascript
// 1. 创建域名变量
let label = "senecacollege";
let tld = "ca";
let domainName = label + "." + tld;

// 2. 检查域名
let isSeneca = domainName === "senecacollege.ca";
let isNotSeneca = !isSeneca;

// 3. IP地址处理
let byte1 = 192;
let byte2 = 168;
let byte3 = 1;
let byte4 = 1;

// 计算无符号整数形式的IP地址
// 这里使用左移运算符将每个字节移到正确的位置
// byte1 << 24 将 byte1 左移 24 位，byte2 << 16 左移 16 位，
// byte3 << 8 左移 8 位，byte4 不左移，
// 然后使用按位或运算符 | 将它们组合成一个整数。
// 注意：由于 JavaScript 中的位运算符会将数字视为 32 位有符号整数，
// 如果结果超出范围，可能会导致负数输出。
// 为了避免这个问题，使用无符号右移运算符 >>> 0 将结果转换为无符号整数。
let ipInt = (byte1 << 24) | (byte2 << 16) | (byte3 << 8) | byte4 >>> 0;

console.log("7.", ipInt); // 输出无符号整数形式的IP地址
```

### 5.2 进阶练习 (Advanced Exercises) 🟡
```javascript
// 1. 温度转换
function celsiusToFahrenheit(celsius) {
    return (celsius * 9/5) + 32;
}

// 2. 时间计算
function secondsToTime(seconds) {
    let minutes = Math.floor(seconds / 60);
    let hours = Math.floor(minutes / 60);
    minutes = minutes % 60;
    return `${hours}小时${minutes}分钟`;
}
```

## 6. 推荐阅读 (Suggested Readings) 📚

### 6.1 基础教程
- [MDN - How does the Internet work?](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/How_does_the_Internet_work)
- [MDN - JavaScript Guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide)

### 6.2 进阶资源
- [HTTP Basic Introduction](https://dev.opera.com/articles/http-basic-introduction/)
- [JavaScript.info](https://javascript.info/)

## 版本控制 (Version Control) 🔄
```markdown
更新日期：2024-01-15
版本号：v1.0
更新内容：
- 初始化文档结构
- 添加基础概念解释
- 补充代码示例
- 添加练习题
```

[End of Document] 