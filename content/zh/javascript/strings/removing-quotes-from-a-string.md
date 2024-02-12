---
title:                "从字符串中移除引号"
aliases:
- zh/javascript/removing-quotes-from-a-string.md
date:                  2024-01-26T03:40:18.955661-07:00
model:                 gpt-4-0125-preview
simple_title:         "从字符串中移除引号"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/zh/javascript/removing-quotes-from-a-string.md"
---

{{< edit_this_page >}}

## 是什么 & 为什么?
从字符串中剥离引号意味着摆脱那些可能会干扰你的代码的讨厌的引号符号，特别是当你在解析数据或构建JSON对象时。程序员这样做是为了清理输入，避免语法错误，并使字符串与代码的其他部分更好地协作。

## 如何操作:
想象一下，你有一个被双引号包裹的字符串，就像`"\"你好，世界！\""`，你想要纯净的、未加引号的文本。这里有一个快速的JavaScript代码片段，可以解放你的字符串，脱离引号的束缚：

```javascript
let quotedString = "\"你好，世界！\"";
let unquotedString = quotedString.replace(/^"|"$/g, '');
console.log(unquotedString); // 输出: 你好，世界！
```

如果你处理的是单引号怎么办？只需稍微修改一下正则表达式：

```javascript
let singleQuotedString = "'你好，世界！'";
let unquotedString = singleQuotedString.replace(/^'|'$/g, '');
console.log(unquotedString); // 输出: 你好，世界！
```

或者如果你的字符串是双引号和单引号的混合体呢？没问题：

```javascript
let mixedQuotedString = "\"'你好，世界！'\"";
let unquotedString = mixedQuotedString.replace(/^["']|["']$/g, '');
console.log(unquotedString); // 输出: '你好，世界！'
```

## 深入探讨
在JSON成为主流之前，转义引号是一种使用反斜杠和技巧的狂野西部方式。早期的编程语言并不总是能很好地处理引号，这意味着需要大量的手动字符串操作。现在，随着标准化的数据格式的出现，去除引号通常是关于在它们被作为JSON处理或存储文本时，清理输入以避免格式冲突。

`.replace()`的替代方法？当然！你可以在引号上分割和加入字符串，如果你对引号的位置很确定，可以使用slice，或者甚至使用正则表达式匹配来提取所需的文本。这完全取决于上下文。

但不要忘记边缘情况：引号内的引号、转义的引号和国际字符。将你的字符串视为一个充满异常的潜在雷区，并小心行事。现代JavaScript引擎针对正则表达式操作进行了优化，因此它们通常是首选，但总是值得检查性能以便处理重数据处理任务。

## 另请参阅
深入了解字符串操作和正则表达式：

- Mozilla开发者网络关于String.replace()的文章：https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replace
- Regex101以测试你的正则表达式模式：https://regex101.com/
- JSON.org了解为什么在现代Web开发中我们要处理这么多引号：http://json.org/
