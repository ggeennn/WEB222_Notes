# WEB222 - Week 3: Objects, Strings, Arrays & RegExp 📚

## 学习路径图 (Learning Path) 🗺️
```
Objects & OOP Basics
↓
String Operations
↓
Array Manipulation
↓
Regular Expressions
```

## 目录 (Table of Contents) 📑
1. [对象和面向对象编程基础](#1-对象和面向对象编程基础-objects-and-oop-basics)
2. [String 字符串](#2-string-字符串)
3. [Array 数组](#3-array-数组)
4. [RegExp 正则表达式](#4-regexp-正则表达式)
5. [实践练习](#5-实践练习-practice-exercises)

## 1. 对象和面向对象编程基础 (Objects and OOP Basics) 🟢

### 面向对象编程 (Object-Oriented Programming | 面向对象编程) 
- 定义 | Definition
  - 面向对象编程是一种编程范式，它将数据和功能组合成更高级的类型
  - OOP combines data and functionality into higher-order types that both contain data and allow us to work with that data
- 示例 | Example
  ```js
  // C语言风格
  char str[31];
  strlen(str);         // 使用函数处理数据

  // JavaScript面向对象风格
  let str = "Hello";   
  str.length;          // 数据和功能结合
  ```
- 💡实践提示 | Practice Tips
  - JavaScript中的对象将数据和方法组合在一起，使代码更直观
  - 理解面向对象可以帮助更好地使用JavaScript的内置对象

### C vs JavaScript对比 (C vs JavaScript Comparison) 🟢
- 定义 | Definition
  ```c
  // C语言方式
  const char name1[31] = "My name is Arnold";
  const char name2[31] = {'M','y',' ','n','a','m','e',' ','i','s',' ','A','r','n','o','l','d','\0'};
  
  // C语言的字符串操作
  strlen(str);         // 获取字符串长度
  strcpy(str2, str);   // 复制字符串
  strcmp(str2, str);   // 比较字符串
  strcat(str, "..."); // 连接字符串
  ```

### JavaScript String的优势 (JavaScript String Advantages) 🟢
- 特点 | Features
  - 更高级别的抽象（Higher level of abstraction）
  - 自动内存管理（Automatic memory management）
  - 字符串可以动态增长或缩小（Strings can grow or shrink dynamically）
  - Unicode支持（Full Unicode support）
```js
let unicode = "中文 español Deutsch English देवनागरी العربية português বাংলা русский 日本語 ਪੰਜਾਬੀ 한국어 தமிழ் עברית";
```

## 2. String 字符串 🟢

### String声明方式 (String Declaration | 字符串声明) 
- 定义 | Definition
  ```js
  // 字符串字面量
  let s = 'some text';    // 单引号
  let s1 = "some text";   // 双引号
  let s2 = `some text`;   // 模板字面量
  
  // String构造函数
  let s3 = new String("Some Text");
  ```
- 💡实践提示 | Practice Tips
  - 推荐使用字面量方式创建字符串
  - 模板字面量支持多行字符串和字符串插值

### String属性和方法 (String Properties and Methods) 
- 常用属性 | Common Properties
  - `length`: 字符串长度
- 常用方法 | Common Methods
  ```js
  // 字符访问
  str.charAt(1)        // 获取指定位置字符
  str[1]              // 使用索引访问
  
  // 字符串操作
  str.concat()        // 字符串连接
  str.padStart()      // 开头填充
  str.padEnd()        // 结尾填充
  
  // 搜索方法
  str.includes()      // 包含检查
  str.startsWith()    // 开始检查
  str.endsWith()      // 结束检查
  str.indexOf()       // 位置查找
  
  // 修改方法
  str.replace()       // 替换
  str.slice()         // 切片
  str.split()         // 分割
  str.toLowerCase()   // 转小写
  str.toUpperCase()   // 转大写
  str.trim()          // 去除空白
  ```

### 模板字面量 (Template Literals) 
- 定义 | Definition
  - 使用反引号(`)定义的字符串，支持多行和表达式插值
  ```js
  let a = 1;
  let s = `The value is ${1*6}`; // 使用${...}插入表达式
  ```

### 原始字符串与字符串对象 (Primitive Strings vs String Objects) 🟡
- 定义 | Definition
  - 使用 `let a = "Hi"` 创建的是一个原始字符串（Primitive String），它是不可变的，性能更好。
  - 使用 `let a = new String("Hi")` 创建的是一个字符串对象（String Object），虽然可以使用字符串的方法，但通常不推荐这样做，因为它会引入不必要的复杂性和性能开销。
  
- 示例 | Example
  ```js
  let primitiveString = "Hello"; // 原始字符串
  let stringObject = new String("Hello"); // 字符串对象

  console.log(typeof primitiveString); // 输出 "string"
  console.log(typeof stringObject);     // 输出 "object"
  ```

- 💡实践提示 | Practice Tips
  - 尽量使用原始字符串，避免使用字符串对象，除非有特殊需求。
  - 原始字符串在内存中占用更少的空间，性能更优。

### **字符串对象的好处 | Benefits of String Objects**
  - 可以附加自定义方法和属性，增强功能
    ```js
    let strObj = new String("Hello");
    strObj.customMethod = function() {
        return this.valueOf() + " World!"; // 使用valueOf()获取原始字符串
    };
    console.log(strObj.customMethod()); // 输出 "Hello World!"
    ```
  - 适用于需要对象特性（如引用传递）的场景
    ```js
    function modifyString(str) {
        str.value = "Modified String"; // 修改对象属性
    }
    let myString = new String("Original String");
    modifyString(myString);
    console.log(myString.value); // 输出 "Modified String"
    ```
  - 允许使用对象的特性，例如可以作为对象传递给函数
    ```js
    function printString(obj) {
        console.log(obj); // 可以直接打印字符串对象
    }
    let stringObj = new String("Hello");
    printString(stringObj); // 输出 String对象
    ```

## 3. Array 数组 🟢

### Array声明和基础操作 (Array Declaration and Basic Operations)
- 定义方式 | Definition Methods
  ```js
  let arr = new Array(1, 2, 3);  // 构造函数
  let arr2 = [1, 2, 3];          // 数组字面量
  ```
- 特点 | Features
  - 可以包含任意类型的数据
  - 大小可动态改变
  - 支持稀疏数组（有空隙的数组）

### Array属性和方法 (Array Properties and Methods)
- 常用属性 | Common Properties
  - `length`: 数组长度
- 修改数组的方法 | Methods that modify array
  ```js
  arr.push()     // 末尾添加元素
  arr.pop()      // 删除末尾元素
  arr.unshift()  // 开头添加元素
  arr.shift()    // 删除开头元素
  ```
- 不修改数组的方法 | Methods that don't modify array
  ```js
  arr.concat()   // 连接数组
  arr.includes() // 包含检查
  arr.indexOf()  // 查找位置
  arr.join()     // 连接成字符串
  ```

### Array迭代方法 (Array Iteration Methods) 🟡
- 常用迭代方法 | Common Iteration Methods
  ```js
  arr.forEach()  // 遍历数组
  arr.map()      // 映射数组
  arr.filter()   // 过滤数组
  arr.find()     // 查找元素
  arr.every()    // 全部满足条件
  ```

### 解构赋值 (Destructuring Assignment) 🟡
- 定义 | Definition
  - 一种从数组中提取值并赋给变量的语法
  ```js
  let [x, y] = [1, 2];  // x=1, y=2
  let [a, , c] = [1, 2, 3];  // 跳过元素
  ```

### JavaScript Array的特殊性质 (JavaScript Array Special Features) 🟡
- 定义 | Definition
  - JavaScript的Array实际上是一个特殊的Map（对象）
  - 使用数字作为键（索引）的特殊映射结构
- 示例 | Example
  ```js
  let arr = [];        // 空数组
  arr[5] = 56;        // 直接设置索引5的值
  console.log(arr.length);  // 输出6
  ```
- 💡实践提示 | Practice Tips
  - 可以有"空洞"（holes）
  - length属性会自动更新
  - 可以使用非连续的索引

### Array迭代方法详解 (Array Iteration Methods in Detail) 🟡
- 示例 | Examples
  ```js
  // forEach示例
  let list = [1, 2, 3, 4];
  list.forEach(function(element) {
    console.log(element);
  });

  // map示例
  let listCopy = list.map(function(element) {
    return element + 3;
  });

  // 对比for循环和forEach
  // 使用for循环
  let listCopy1 = [];
  for(let i = 0; i < list.length; i++) {
    let element = list[i];
    element += 3;
    listCopy1.push(element);
  }

  // 使用forEach
  let listCopy2 = [];
  list.forEach(function(element) {
    listCopy2.push(element + 3);
  });
  ```
- 💡实践提示 | Practice Tips
  - 迭代方法可以避免索引错误
  - 代码更简洁易读
  - 更符合函数式编程思想

## 4. RegExp 正则表达式 🔴

### RegExp基础 (RegExp Basics)
- 定义方式 | Definition Methods
  ```js
  let regex = /pattern/;              // 字面量
  let regex2 = new RegExp("pattern"); // 构造函数
  ```

### 常用正则表达式模式 (Common RegExp Patterns)
- 字符类 | Character Classes
  ```js
  \d        // 数字 [0-9]
  \w        // 单词字符 [A-Za-z0-9_]
  \s        // 空白字符
  [aeiou]   // 自定义字符集
  [^aeiou]  // 否定字符集
  ```
- 重复 | Repetition
  ```js
  ?         // 零次或一次
  *         // 零次或多次
  +         // 一次或多次
  {n}       // 精确n次
  {n,m}     // n到m次
  ```

### RegExp方法 (RegExp Methods)
- 常用方法 | Common Methods
  ```js
  regex.test(string)     // 测试匹配
  string.match(regex)    // 查找匹配
  string.replace(regex)  // 替换匹配
  string.split(regex)    // 分割字符串
  ```

### RegExp高级搜索标志 (RegExp Advanced Search Flags) 🔴
- 定义 | Definition
  ```js
  let regex = /pattern/gi;  // 使用g和i标志
  let regex2 = new RegExp("pattern", "gi");
  ```
- 常用标志 | Common Flags
  - `g`: 全局匹配（Global match）
  - `i`: 忽略大小写（Case-insensitive）
  - `m`: 多行匹配（Multiline match）
- 💡实践提示 | Practice Tips
  - 全局匹配会查找所有匹配项
  - 忽略大小写适用于不区分大小写的搜索
  - 多行匹配影响^和$的行为

## 5. 实践练习 (Practice Exercises) 💻

### 基础练习 (Basic Exercises) 🟢
1. 编写函数显示字符串数组
2. 实现简单的堆栈操作
3. 创建数字范围数组
4. 为数字添加美元符号

### 进阶练习 (Advanced Exercises) 🟡
1. 字符串清理
2. 数组元素测量
3. 查找特定元素
4. 年龄检查
5. 密码验证

### 综合练习 (Comprehensive Exercise) 🔴
处理CSV格式数据，包括：
1. 分割行
2. 提取字段
3. 清理数据
4. 格式转换
5. 数据重组

## FAQ (常见问题) ❓
1. JavaScript中的String和Array有什么区别？
   - String是不可变的，Array是可变的
   - String专门用于文本处理，Array用于列表数据
   
2. 为什么要使用正则表达式？
   - 提供强大的文本模式匹配和处理能力
   - 可以简化复杂的字符串操作

## 学习建议 (Study Tips) 💡
1. 多练习数组的迭代方法
2. 从简单的正则表达式开始学习
3. 结合实际项目练习字符串处理
4. 注意String的不可变性

[End of Document] 