---
aliases:
- /zh/clojure/getting-the-current-date/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:09:13.360302-07:00
description: "\u5728\u7F16\u7A0B\u4E2D\u83B7\u53D6\u5F53\u524D\u65E5\u671F\u662F\u81F3\
  \u5173\u91CD\u8981\u7684\uFF0C\u539F\u56E0\u5305\u62EC\u8BB0\u5F55\u65E5\u5FD7\u3001\
  \u65F6\u95F4\u6233\u4E8B\u4EF6\u548C\u5B89\u6392\u4EFB\u52A1\u3002\u5728 Clojure\
  \ \u4E2D\uFF0C\u4E00\u4E2A\u57FA\u4E8E JVM \u7684 Lisp \u65B9\u8A00\uFF0C\u8FD9\u4E2A\
  \u4EFB\u52A1\u5229\u7528\u4E86 Java \u4E92\u64CD\u4F5C\u529F\u80FD\uFF0C\u5141\u8BB8\
  \u76F4\u63A5\u8BBF\u95EE\u4E30\u5BCC\u7684 Java \u65E5\u671F\u65F6\u95F4 API\u3002"
lastmod: 2024-02-18 23:08:58.837524
model: gpt-4-0125-preview
summary: "\u5728\u7F16\u7A0B\u4E2D\u83B7\u53D6\u5F53\u524D\u65E5\u671F\u662F\u81F3\
  \u5173\u91CD\u8981\u7684\uFF0C\u539F\u56E0\u5305\u62EC\u8BB0\u5F55\u65E5\u5FD7\u3001\
  \u65F6\u95F4\u6233\u4E8B\u4EF6\u548C\u5B89\u6392\u4EFB\u52A1\u3002\u5728 Clojure\
  \ \u4E2D\uFF0C\u4E00\u4E2A\u57FA\u4E8E JVM \u7684 Lisp \u65B9\u8A00\uFF0C\u8FD9\u4E2A\
  \u4EFB\u52A1\u5229\u7528\u4E86 Java \u4E92\u64CD\u4F5C\u529F\u80FD\uFF0C\u5141\u8BB8\
  \u76F4\u63A5\u8BBF\u95EE\u4E30\u5BCC\u7684 Java \u65E5\u671F\u65F6\u95F4 API\u3002"
title: "\u83B7\u53D6\u5F53\u524D\u65E5\u671F"
---

{{< edit_this_page >}}

## 什么 & 为什么？
在编程中获取当前日期是至关重要的，原因包括记录日志、时间戳事件和安排任务。在 Clojure 中，一个基于 JVM 的 Lisp 方言，这个任务利用了 Java 互操作功能，允许直接访问丰富的 Java 日期时间 API。

## 如何操作：

### 使用 Java 互操作
Clojure 与 Java 的无缝互操作性允许你直接利用 Java 日期时间 API。以下是获取当前日期的方法：

```clojure
(import java.time.LocalDate)

(defn get-current-date []
  (str (LocalDate/now)))

;; 示例输出
(get-current-date) ; "2023-04-15"
```

### 使用 clj-time 库
对于一个更符合 Clojure 习惯的解决方案，你可能会选择 `clj-time` 库，一个围绕 Joda-Time 的封装，虽然对于大多数新项目，建议使用内置的 Java 8 日期时间 API。然而，如果你偏好或需要 `clj-time`：

首先，将 `clj-time` 添加到你的项目依赖中。在你的 `project.clj` 中，包含：

```clojure
[clj-time "0.15.2"]
```

然后，使用它来获取当前日期：

```clojure
(require '[clj-time.core :as time])

(defn get-current-date-clj-time []
  (str (time/now)))

;; 示例输出
(get-current-date-clj-time) ; "2023-04-15T12:34:56.789Z"
```

这两种方法都提供了在 Clojure 中快速有效地获取当前日期的方式，利用了底层 Java 平台的力量或 Clojure 特定库的便利。
