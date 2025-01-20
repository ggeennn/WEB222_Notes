# WEB222 - Week 2: Functions & Scope 📚

## 学习目标 (Learning Objectives) 🎯
完成本周学习后，你应该能够：
1. 理解JavaScript函数的基本概念和使用方法
2. 掌握函数声明和表达式的不同写法
3. 理解作用域和闭包的概念
4. 能够使用内置函数进行基础编程

## 项目目录结构 (Project Directory Structure) 📁
```
project/
├── src/                        // 源代码目录
│   ├── solutions.js            // 解决方案实现文件
│   ├── problem-00.test.js      // 测试用例文件
│   ├── problem-01.test.js      // 测试用例文件
│   └── ... (其他测试文件)
├── node_modules/               // npm 依赖包目录
├── .vscode/                    // VS Code 配置目录
├── package.json                // 项目配置文件
├── package-lock.json           // 依赖版本锁定文件
├── .eslintrc.js               // ESLint 配置文件
├── .prettierrc.js             // Prettier 配置文件
├── .gitignore                 // Git 忽略文件配置
└── LICENSE                    // 项目许可证文件
```

### 目录结构详解 (Directory Structure Explanation) 📚

#### 1. 核心文件 (Core Files) 🟢
- **src/solutions.js**: 
  - 主要的代码实现文件
  - 包含所有问题的解决方案函数
  - 这是你需要编辑的主要文件

- **src/problem-XX.test.js**: 
  - 测试文件，用于验证你的解决方案
  - 每个文件对应一个特定的问题
  - 使用 Jest 测试框架编写
  - 不应该修改这些文件

#### 2. 配置文件 (Configuration Files) 🟡
- **package.json**:
  - 项目的核心配置文件
  - 定义项目的元数据（名称、版本等）
  - 列出项目依赖
  - 定义 npm 脚本命令
  ```json
  主要脚本命令：
  - "test": 运行所有测试
  - "test-watch": 以监视模式运行测试
  - "prettier": 格式化代码
  - "eslint": 运行代码检查
  ```

- **.eslintrc.js**: 
  - ESLint 代码检查工具的配置
  - 定义代码规范和规则

- **.prettierrc.js**:
  - Prettier 代码格式化工具的配置
  - 确保代码风格统一

#### 3. 依赖管理 (Dependency Management) 🟡
- **node_modules/**:
  - 存放所有 npm 安装的依赖包
  - 不应该提交到版本控制系统

- **package-lock.json**:
  - 锁定依赖包的具体版本
  - 确保团队成员使用相同的依赖版本

#### 4. 开发工具配置 (Development Tools) 🟢
- **.vscode/**:
  - Visual Studio Code 编辑器配置
  - 可能包含调试配置和编辑器设置

- **.gitignore**:
  - 指定 Git 版本控制要忽略的文件
  - 通常包含 node_modules/ 和构建输出

### 项目依赖说明 (Project Dependencies) 🟡
主要开发依赖包括：
- **jest**: JavaScript 测试框架
- **eslint**: 代码质量检查工具
- **prettier**: 代码格式化工具
- **其他工具包**: 用于构建、复制文件等任务

### 使用方法 (Usage) 🟢
1. 安装依赖：
   ```bash
   npm install
   ```

2. 运行测试：
   ```bash
   npm test
   ```

3. 格式化代码：
   ```bash
   npm run prettier
   ```

4. 检查代码质量：
   ```bash
   npm run eslint
   ```

## 目录 (Table of Contents) 📑
1. [函数基础 (Function Basics)](#1-函数基础-function-basics)
2. [函数类型 (Function Types)](#2-函数类型-function-types)
3. [作用域 (Scope)](#3-作用域-scope)
4. [闭包 (Closures)](#4-闭包-closures)
5. [内置函数 (Built-in Functions)](#5-内置函数-built-in-functions)
6. [实践练习 (Practice Exercises)](#6-实践练习-practice-exercises)

## 1. 函数基础 (Function Basics) 🟢

### 1.1 什么是函数 (What is a Function)
- 定义 | Definition
  ```
  函数是一个子程序，可以被程序的其他部分调用
  A function is a subprogram that can be called by other parts of the program
  ```

- 💡 通俗理解 | Simple Explanation
  ```
  函数就像是一个工具箱：
  ├── 输入（参数）= 原材料
  ├── 处理过程 = 加工步骤
  └── 输出（返回值）= 成品
  ```

### 1.2 函数的基本组成 🟢
```javascript
// 基本函数结构
function 函数名(参数1, 参数2) {
    // 函数体
    return 返回值;
}

// 示例：计算正方形面积
function calculateSquareArea(side) {
    return side * side;
}
```

## 2. 函数类型 (Function Types) 🟡

### 2.1 函数声明 (Function Declaration) 
```javascript
// 1. 基本声明
function noop() {
    // 无操作函数
}

// 2. 带参数的声明
function add(a, b) {
    return a + b;
}
```

### 2.2 函数表达式 (Function Expression)
```javascript
// 1. 匿名函数表达式
let square = function(n) {
    return n * n;
};

// 2. 命名函数表达式
let factorial = function calc(n) {
    if (n <= 1) return 1;
    return n * calc(n - 1);
};
```

### 2.3 箭头函数 (Arrow Function) 🟡
```javascript
// 1. 基本箭头函数
let add = (a, b) => a + b;

// 2. 带函数体的箭头函数
let greet = name => {
    let message = `Hello, ${name}!`;
    return message;
};
```

## 3. 作用域 (Scope) 🟡

### 3.1 作用域类型 (Scope Types)
- 定义 | Definition
  ```
  作用域定义了变量在代码中的可访问范围
  Scope defines where variables can be accessed in code
  ```

- 💡 通俗理解 | Simple Explanation
  ```
  作用域就像是变量的活动范围：
  ├── 全局作用域 = 整个游乐场都能玩
  ├── 函数作用域 = 只能在某个游乐设施玩
  └── 块级作用域 = 只能在指定区域玩
  ```

### 3.2 变量声明与作用域 🟢
```javascript
// 1. var声明（函数作用域）
var globalVar = "我在任何地方都可见";

// 2. let声明（块级作用域）
let blockVar = "我只在块内可见";

// 3. const声明（块级作用域）
const CONSTANT = "我是常量，值不能改变";

// 示例：作用域差异
function scopeDemo() {
    var functionScoped = "函数作用域";
    
    if (true) {
        let blockScoped = "块级作用域";
        var stillFunctionScoped = "仍然是函数作用域";
    }
    
    console.log(functionScoped);         // 正常工作
    console.log(stillFunctionScoped);    // 正常工作
    console.log(blockScoped);           // 错误！不可访问
}
```

## 4. 闭包 (Closures) 🔴

### 4.1 闭包概念 (Closure Concept)
- 定义 | Definition
  ```
  闭包是一个函数和其周围状态（词法环境）的引用的组合
  A closure is a function bundled with its lexical environment
  ```

- 💡 通俗理解 | Simple Explanation
  ```
  闭包就像是带有记忆的函数：
  ├── 外部环境 = 记忆的内容
  ├── 内部函数 = 使用这些记忆的工具
  └── 持久化 = 保持记忆不丢失
  ```

### 4.2 闭包示例 (Closure Examples)
```javascript
// 1. 基本闭包示例
function createCounter() {
    let count = 0;  // 私有变量
    
    return {
        increment: function() { 
            return ++count; 
        },
        getCount: function() { 
            return count; 
        }
    };
}

const counter = createCounter();
console.log(counter.increment()); // 1
console.log(counter.increment()); // 2
console.log(counter.getCount()); // 2

// 2. 实用闭包示例
function createGreeting(greeting) {
    return function(name) {
        return `${greeting}, ${name}!`;
    };
}

const sayHello = createGreeting("Hello");
const sayHi = createGreeting("Hi");

console.log(sayHello("John")); // "Hello, John!"
console.log(sayHi("Mary"));    // "Hi, Mary!"
```

## 5. 内置函数 (Built-in Functions) 🟢

### 5.1 常用全局函数 (Common Global Functions)
```javascript
// 1. 数值转换
parseInt("123");      // 字符串转整数
parseFloat("12.34"); // 字符串转浮点数
isNaN(NaN);         // 检查是否为NaN
isFinite(123);      // 检查是否为有限数值

// 2. URI处理
encodeURI("Hello World");        // 编码URI
decodeURI("Hello%20World");      // 解码URI
encodeURIComponent("?name=john"); // 编码URI组件
decodeURIComponent("%3Fname%3Djohn"); // 解码URI组件
```

### 5.2 常用对象方法 (Common Object Methods) 
```javascript
// 1. 控制台方法
console.log("普通信息");
console.warn("警告信息");
console.error("错误信息");
console.table([{name: "John", age: 30}]); // 表格形式显示

// 2. 数学方法
Math.abs(-5);     // 绝对值
Math.max(1, 2, 3); // 最大值
Math.min(1, 2, 3); // 最小值
Math.round(3.6);   // 四舍五入

// 3. 日期方法
Date.now();         // 当前时间戳
new Date().getTime(); // 获取时间戳
```

## 6. 实践练习 (Practice Exercises) 💻

### 6.1 参数处理练习 (Parameter Handling) 🟢
- 定义 | Definition
  ```
  JavaScript函数可以灵活处理任意数量的参数
  JavaScript functions can handle any number of arguments
  ```

- 💡 通俗理解 | Simple Explanation
  ```
  参数处理就像收快递：
  ├── arguments = 所有快递的集合
  ├── 默认参数 = 如果没收到就用备用的
  └── 剩余参数 = 额外收到的都放一起
  ```

#### 6.1.1 arguments对象
```javascript
// 使用arguments处理任意数量参数
function sum() {
    let total = 0;
    for(let i = 0; i < arguments.length; i++) {
        total += arguments[i];
    }
    return total;
}

console.log(sum(1, 2, 3));      // 6
console.log(sum(1, 2, 3, 4));   // 10
```

#### 6.1.2 默认参数
```javascript
// 使用默认参数值
function greet(name = "Guest", greeting = "Hello") {
    return `${greeting}, ${name}!`;
}

console.log(greet());           // "Hello, Guest!"
console.log(greet("John"));     // "Hello, John!"
console.log(greet("Mary", "Hi")); // "Hi, Mary!"
```

#### 6.1.3 剩余参数
```javascript
// 使用...rest语法
function multiply(multiplier, ...numbers) {
    return numbers.map(n => n * multiplier);
}

console.log(multiply(2, 1, 2, 3));    // [2, 4, 6]
console.log(multiply(3, 5, 10));      // [15, 30]
```

### 6.2 实用函数练习 (Practical Exercises) 🟡

#### 6.2.1 基础数学函数
```javascript
// 1. 计算给定数字的阶乘
function factorial(n) {
    if (n <= 1) return 1;
    return n * factorial(n - 1);
}

// 2. 检查数字是否为质数
function isPrime(num) {
    if (num <= 1) return false;
    for (let i = 2; i <= Math.sqrt(num); i++) {
        if (num % i === 0) return false;
    }
    return true;
}
```

#### 6.2.2 字符串处理函数
```javascript
// 1. URL查询字符串生成器
function buildQueryString(...params) {
    return "?" + params
        .map(param => encodeURIComponent(param))
        .join("&");
}

// 2. 字符串反转
function reverseString(str) {
    return str.split("").reverse().join("");
}
```

### 6.3 高级练习 (Advanced Exercises) 🔴

#### 6.3.1 闭包应用
```javascript
// 创建私有计数器
function createPrivateCounter(initialValue = 0) {
    let count = initialValue;
    
    return {
        increment() { return ++count; },
        decrement() { return --count; },
        getValue() { return count; },
        reset() { count = initialValue; return count; }
    };
}

const counter = createPrivateCounter(10);
console.log(counter.increment()); // 11
console.log(counter.decrement()); // 10
console.log(counter.getValue());  // 10
```

#### 6.3.2 函数组合
```javascript
// 函数组合器
function compose(...functions) {
    return function(x) {
        return functions.reduceRight((acc, fn) => fn(acc), x);
    };
}

const addOne = x => x + 1;
const double = x => x * 2;
const square = x => x * x;

const compute = compose(square, double, addOne);
console.log(compute(3)); // ((3 + 1) * 2)² = 64
```

## 7. 推荐阅读 (Suggested Readings) 📚

### 7.1 基础教程
- MDN Web Docs
  - [Functions Guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions)
  - [Functions Reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions)

### 7.2 进阶阅读
- [Exploring JS - Chapter 15: Functions](http://exploringjs.com/es5/ch15.html)
- [Exploring JS - Chapter 16: Variables, Scopes, and Closures](http://exploringjs.com/es5/ch16.html)
- [Eloquent JavaScript - Chapter 3: Functions](https://eloquentjavascript.net/03_functions.html)

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