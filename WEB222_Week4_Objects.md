# WEB222 - Week 4 - Objects in JavaScript 🔍

==============================================
READ UNTIL: 
Complex Property Types: Object, Function
==============================================


## 学习路径图 (Learning Path) 📋
1. Objects基础概念 (Basic Object Concepts)
2. Object属性操作 (Object Property Operations)
3. Object的高级应用 (Advanced Object Applications)
4. 构造函数 (Constructor Functions)
5. 原型继承 (Prototype Inheritance)
6. 类语法 (Class Syntax)

## 目录 (Table of Contents) 📑
- [1. Objects基础概念](#1-objects基础概念-basic-object-concepts)
- [2. Object属性操作](#2-object属性操作-object-property-operations)
- [3. Object的高级应用](#3-object的高级应用-advanced-object-applications)
- [4. 构造函数](#4-构造函数-constructor-functions)
- [5. 原型继承](#5-原型继承-prototype-inheritance)
- [6. 类语法](#6-类语法-class-syntax)
- [7. 实践示例](#7-实践示例-practice-examples)
- [8. 学习建议](#8-学习建议-study-tips)

## 1. Objects基础概念 (Basic Object Concepts) 🟢

### Object (对象) 
- 定义 | Definition
  - 中文解释：Object是JavaScript中的一种数据结构，由键值对(key-value pairs)组成的集合，也被称为关联数组或字典
  - English Definition: An Object in JavaScript is a map (also known as an associative array or dictionary) composed of key-value pairs called properties

- 特点 | Characteristics
  - 每个键(key)必须是唯一的字符串
  - 值(value)可以是任何JavaScript数据类型
  - 属性可以动态添加和删除
  - 使用花括号 `{}` 创建

### Object字面量 (Object Literals) 🟢
- 定义 | Definition
  - 中文解释：使用花括号直接创建对象的语法
  - English Definition: Syntax using curly braces to directly create objects

- 示例 | Example
```javascript
// 空对象 | Empty object
let o = {};

// 带属性的对象 | Object with properties
let person = { name: 'Tim Wu' };

// 多行属性对象 | Multi-line property object
let campus = {
    name: 'Seneca@York',
    lat: 43.7714,
    lng: -79.4988
};
```

## 2. Object属性操作 (Object Property Operations) 🟢

### 访问属性 (Accessing Properties) 
- 方法 | Methods
  1. 点操作符 (Dot Operator) `.`
  2. 方括号操作符 (Bracket Operator) `[]`

- 示例 | Example
```javascript
let person = { name: 'Tim Wu' };
console.log(person.name);      // 使用点操作符
console.log(person['name']);   // 使用方括号操作符
```
### 方括号操作符 (Bracket Operator) `[]`
- 方括号操作符用于通过字符串或变量访问对象的属性。

#### 特殊情况
1. **动态属性访问**: 当属性名称在运行时未知时，可以使用变量来访问属性。例如：
   ```javascript
   let currentUsername = 'Alice';
   let users = { Alice: { age: 25 }, Bob: { age: 30 } };
   console.log(users[currentUsername].age); // 输出: 25
   ```
2. **访问保留关键字**: 如果属性名称是 JavaScript 的保留关键字，必须使用方括号操作符。例如：
   ```javascript
   let obj = { 'for': 'value' };
   console.log(obj['for']); // 输出: value
   ```
3. **属性名称包含特殊字符**: 当属性名称包含空格、符号或其他特殊字符时，必须使用方括号。例如：
   ```javascript
   let obj = { 'first name': 'Alice', 'age!': 25 };
   console.log(obj['first name']); // 输出: Alice
   console.log(obj['age!']); // 输出: 25
   ```
4. **数字开头的属性名称**: 如果属性名称以数字开头，也需要使用方括号。例如：
   ```javascript
   let obj = { '1stPlace': 'Alice', '2ndPlace': 'Bob' };
   console.log(obj['1stPlace']); // 输出: Alice
   ```
### 总结
- 方括号操作符在需要动态访问属性、处理保留关键字、特殊字符或数字开头的属性名称时非常有用。

### 解构赋值 (Destructuring Assignment) 🟡
- 定义 | Definition
  - 中文解释：从对象中提取属性值并赋给变量的简洁语法
  - English Definition: Syntax for extracting property values from objects and assigning them to variables

- 示例 | Example
```javascript
let senecaNewnham = {
    address: '1750 Finch Ave. East',
    lat: 43.7960,
    lng: -79.3486
};

// 解构只需要的属性
let {lat, lng} = senecaNewnham;
```
#### 处理对象属性访问的安全性
在访问对象的属性时，可能会遇到对象为 `null` 或 `undefined` 的情况。JavaScript 提供了几种方法来安全地访问对象属性：
1. **版本 1**: 检查对象是否存在
   ```javascript
   let room = gameLevel.rooms.R31347;
   if(room) {
       // 只有在 room 为真值时才访问
   }
   ```
2. **版本 2**: 检查对象及其属性
   ```javascript
   if(room && room.monster) {
       // 只有在 room 为真值且 room.monster 存在时才访问
   }
   ```
3. **版本 3**: 使用可选链操作符
   ```javascript
   if(room?.monster) {
       // 与版本 2 相同，但使用 ?. 语法
   }
   ```
- **总结**: 使用这些方法可以避免在访问对象属性时出现错误，确保代码的安全性和健壮性。

## 3. Object的高级应用 (Advanced Object Applications) 🟡

### 可选参数处理 (Optional Parameters) 
- 定义 | Definition
  - 中文解释：使用对象作为函数参数来处理可选配置的模式
  - English Definition: Pattern using objects as function parameters to handle optional configurations

- 示例 | Example
```javascript
function initGame(options = {}) {
    let score = options.score || 0;
    let level = options.level || 1;
    let inventory = options.inventory || [];
}
```
### 使用解构赋值处理函数参数
```javascript
function processStudent(student) {
    let { name, studentId, username, email } = student;
    // 使用从 student 对象中解构出来的值
    console.log(`Name: ${name}, ID: ${studentId}, Username: ${username}, Email: ${email}`);
}

processStudent({
    name: 'Tim Wu',
    studentId: '10341346',
    username: 'timw',
    email: 'timw@myseneca.ca'
});
```
- **优点**:
  - **可读性**: 使用对象作为参数可以提高代码的可读性。
  - **灵活性**: 方便添加或删除参数。
  - **避免位置依赖**: 调用者不必记住参数的顺序。

### 属性集合追踪 (Property Set Tracking) 
- 示例 | Example
```javascript
let characterCounts = {};
let sentence = "Hello";

for(let char of sentence) {
    characterCounts[char] = (characterCounts[char] || 0) + 1;
}
```

## 4. 构造函数 (Constructor Functions) 🟡

### Constructor Function
- 定义 | Definition
  - 中文解释：用于创建具有相同结构的多个对象的特殊函数
  - English Definition: Special functions used to create multiple objects with the same structure

- 特点 | Characteristics
  - 函数名首字母大写
  - 使用 `new` 关键字调用
  - 内部使用 `this` 关键字

- 示例 | Example
```javascript
function User(id, name) {
    this.id = id;
    this.name = name;
}

let user1 = new User(1, 'Sam Smith');
```

## 5. 原型继承 (Prototype Inheritance) 🔴

### Prototype (原型)
- 定义 | Definition
  - 中文解释：JavaScript中实现对象之间共享属性和方法的机制
  - English Definition: Mechanism in JavaScript for sharing properties and methods between objects

- 示例 | Example
```javascript
function User(id, name) {
    this.id = id;
    this.name = name;
}

User.prototype.toString = function() {
    return `${this.name} (#${this.id})`;
};
```

## 6. 类语法 (Class Syntax) 🟡

### Class
- 定义 | Definition
  - 中文解释：ES6引入的创建对象的新语法，但底层仍使用原型继承
  - English Definition: New syntax introduced in ES6 for creating objects, still using prototypal inheritance underneath

- 示例 | Example
```javascript
class User {
    constructor(id, name) {
        this.id = id;
        this.name = name;
    }

    toString() {
        return `${this.name} (#${this.id})`;
    }
}
```

### 继承 (Inheritance)
```javascript
class Student extends User {
    constructor(id, name, email) {
        super(id, name);
        this.email = email;
    }
}
```

## 7. 实践示例 (Practice Examples) 💻

### Morse Code Translator
- 项目目标：创建一个摩尔斯电码转换器
- 实现功能：
  - 文本转摩尔斯码
  - 摩尔斯码转文本
  - 使用对象存储映射关系

## 8. 学习建议 (Study Tips) 💡

1. 循序渐进
   - 先掌握基本的对象字面量语法
   - 理解属性的访问和修改
   - 再学习构造函数和原型
   - 最后掌握类语法

2. 实践要点
   - 多写代码示例
   - 使用控制台调试
   - 尝试不同的对象操作方法

3. 注意事项
   - 理解 `this` 关键字的上下文
   - 注意属性的存在性检查
   - 合理使用解构赋值

## 推荐阅读 (Suggested Readings) 📚

- [Object-oriented JavaScript for beginners](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Object-oriented_JS)
- [ExploringJS, Chapter 17. Objects and Inheritance](http://exploringjs.com/es5/ch17.html)
- [ExploringJS, Chapter 20. Dates](http://exploringjs.com/es5/ch20.html)
- [ExploringJS, Chapter 21. Math](http://exploringjs.com/es5/ch21.html) 