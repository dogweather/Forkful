---
changelog:
- 2024-02-01, gpt-4-0125-preview, translated from English
date: 2024-02-01 21:56:15.013458-07:00
description: "\u5728\u7F16\u7A0B\u4E2D\uFF0C\u65E5\u5FD7\u8BB0\u5F55\u6D89\u53CA\u5728\
  \u8FD0\u884C\u65F6\u8BB0\u5F55\u4E8B\u4EF6\u3001\u9519\u8BEF\u6216\u503C\u5F97\u6CE8\
  \u610F\u7684\u53D1\u751F\u60C5\u51B5\u3002\u7A0B\u5E8F\u5458\u8FD9\u6837\u505A\u662F\
  \u4E3A\u4E86\u8C03\u8BD5\u95EE\u9898\u3001\u76D1\u63A7\u6027\u80FD\u4EE5\u53CA\u4FDD\
  \u7559\u64CD\u4F5C\u6570\u636E\u7684\u8BB0\u5F55\uFF0C\u8FD9\u5BF9\u4E8E\u7EF4\u62A4\
  \u548C\u7406\u89E3\u751F\u4EA7\u4E2D\u8F6F\u4EF6\u7684\u884C\u4E3A\u81F3\u5173\u91CD\
  \u8981\u3002"
lastmod: '2024-03-13T22:44:47.210443-06:00'
model: gpt-4-0125-preview
summary: "\u5728\u7F16\u7A0B\u4E2D\uFF0C\u65E5\u5FD7\u8BB0\u5F55\u6D89\u53CA\u5728\
  \u8FD0\u884C\u65F6\u8BB0\u5F55\u4E8B\u4EF6\u3001\u9519\u8BEF\u6216\u503C\u5F97\u6CE8\
  \u610F\u7684\u53D1\u751F\u60C5\u51B5\u3002\u7A0B\u5E8F\u5458\u8FD9\u6837\u505A\u662F\
  \u4E3A\u4E86\u8C03\u8BD5\u95EE\u9898\u3001\u76D1\u63A7\u6027\u80FD\u4EE5\u53CA\u4FDD\
  \u7559\u64CD\u4F5C\u6570\u636E\u7684\u8BB0\u5F55\uFF0C\u8FD9\u5BF9\u4E8E\u7EF4\u62A4\
  \u548C\u7406\u89E3\u751F\u4EA7\u4E2D\u8F6F\u4EF6\u7684\u884C\u4E3A\u81F3\u5173\u91CD\
  \u8981\u3002."
title: "\u65E5\u5FD7\u8BB0\u5F55"
weight: 17
---

## 如何操作：
在Google Apps脚本中，可以使用各种方法进行日志记录，如`Logger`类和`console.log()`。`Logger`类是传统方式，适用于简单的调试和开发目的。根据最近的更新，`console.log()`提供了更多的灵活性和与Stackdriver日志记录的集成，为在Google Cloud平台监控您的Apps脚本提供了一个更健壮的解决方案。

**使用Logger：**

```javascript
function logSample() {
  Logger.log('这是一个简单的日志消息');
  
  var value = 5;
  Logger.log('值是：%s', value); //字符串格式化
}

// 查看日志：
// 1. 运行logSample函数。
// 2. 查看 -> 日志
```

**Logger输出示例：**

```
[22-04-20 10:00:00:000 PDT] 这是一个简单的日志消息
[22-04-20 10:00:00:001 PDT] 值是：5
```

**使用console.log()：**

```javascript
function consoleLogSample() {
  console.log('这条消息传至Stackdriver日志记录');
  const obj = {name: 'Jane', role: 'Developer'};
  console.info('记录一个对象：', obj);
}

// 日志可以在Google Cloud平台（GCP）控制台下的Stackdriver日志记录中查看
```

**console.log()输出示例：**

```
这条消息传至Stackdriver日志记录
记录一个对象：{name: "Jane", role: "Developer"}
```

通过将复杂应用程序转移到`console.log()`，开发者可以使用GCP提供的强大过滤器和工具高效地解析和分析日志，这是传统的Logger类所无法直接完成的。

## 深入了解：
Google Apps脚本中的日志记录已经显著演变。最初，`Logger`类是开发人员调试脚本的主要方法。它简单且足够用于基本脚本，但缺乏现代云应用程序所需的能力，比如搜索日志或随时间分析日志趋势。

`console.log()`的引入通过将Google Apps脚本日志记录与Google Cloud的Stackdriver日志记录（现在称为运营套件）集成，弥补了这一差距，为日志记录、监控和调试应用程序提供了一个集中化的平台。这不仅允许了大规模日志记录，还开启了高级日志管理功能，如基于日志的度量、实时日志分析以及与其他Google Cloud服务的集成。

虽然`Logger`仍在快速调试和在较小脚本中记录日志方面有其用处，但向使用`console.log()`的演进反映了开发可扩展的、云原生应用程序的更广泛趋势。这突显了谷歌致力于为开发者提供配合当今应用程序的复杂性和规模的工具。然而，新手应该意识到学习曲线略显陡峭，并且需要熟悉Google Cloud平台的概念。尽管如此，对希望充分利用云能力的开发者而言，此举是有利的。这种与云服务的对齐是软件开发中更广泛趋势的一部分，强调了云计算时代健壮、可扩展的日志机制的重要性。
