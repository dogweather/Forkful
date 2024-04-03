---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:30:34.274664-07:00
description: "\u5728 Fish Shell \u4E2D\u7F16\u5199\u6D4B\u8BD5\u6D89\u53CA\u5230\u521B\
  \u5EFA\u811A\u672C\uFF0C\u8FD9\u4E9B\u811A\u672C\u4F1A\u81EA\u52A8\u8FD0\u884C\u4F60\
  \u7684\u4EE3\u7801\u4EE5\u9A8C\u8BC1\u5176\u884C\u4E3A\u662F\u5426\u7B26\u5408\u9884\
  \u671F\u7ED3\u679C\u3002\u8FD9\u79CD\u505A\u6CD5\u81F3\u5173\u91CD\u8981\uFF0C\u56E0\
  \u4E3A\u5B83\u786E\u4FDD\u4F60\u7684 Shell \u811A\u672C\u6309\u9884\u671F\u5DE5\u4F5C\
  \uFF0C\u80FD\u591F\u53CA\u65E9\u53D1\u73B0\u9519\u8BEF\u5E76\u7B80\u5316\u7EF4\u62A4\
  \u5DE5\u4F5C\u3002"
lastmod: '2024-03-13T22:44:48.269597-06:00'
model: gpt-4-0125-preview
summary: "\u5728 Fish Shell \u4E2D\u7F16\u5199\u6D4B\u8BD5\u6D89\u53CA\u5230\u521B\
  \u5EFA\u811A\u672C\uFF0C\u8FD9\u4E9B\u811A\u672C\u4F1A\u81EA\u52A8\u8FD0\u884C\u4F60\
  \u7684\u4EE3\u7801\u4EE5\u9A8C\u8BC1\u5176\u884C\u4E3A\u662F\u5426\u7B26\u5408\u9884\
  \u671F\u7ED3\u679C\u3002\u8FD9\u79CD\u505A\u6CD5\u81F3\u5173\u91CD\u8981\uFF0C\u56E0\
  \u4E3A\u5B83\u786E\u4FDD\u4F60\u7684 Shell \u811A\u672C\u6309\u9884\u671F\u5DE5\u4F5C\
  \uFF0C\u80FD\u591F\u53CA\u65E9\u53D1\u73B0\u9519\u8BEF\u5E76\u7B80\u5316\u7EF4\u62A4\
  \u5DE5\u4F5C\u3002."
title: "\u7F16\u5199\u6D4B\u8BD5"
weight: 36
---

## 如何操作：
Fish 没有像一些其他编程环境那样内置的测试框架。然而，你可以编写使用断言来检查函数行为的简单测试脚本。此外，你可以利用第三方工具如 `fishtape` 来获得更全面的测试套件。

### 示例 1：基本测试脚本
我们从一个在 Fish 中计算两个数之和的基本函数开始：

```fish
function add --description 'Add two numbers'
    set -l sum (math $argv[1] + $argv[2])
    echo $sum
end
```

你可以为这个函数编写一个基本测试脚本，如下所示：

```fish
function test_add
    set -l result (add 3 4)
    if test $result -eq 7
        echo "test_add passed"
    else
        echo "test_add failed"
    end
end

test_add
```

运行这个脚本将输出：

```
test_add passed
```

### 示例 2：使用 Fishtape
为了得到一个更健壮的测试解决方案，你可以使用 `fishtape`，这是一个为 Fish 生成 TAP 的测试运行器。

首先，如果你还没有安装 `fishtape`，则安装它：

```fish
fisher install jorgebucaran/fishtape
```

接下来，为你的 `add` 函数创建一个测试文件，例如 `add_test.fish`：

```fish
test "Adding 3 and 4 yields 7"
    set result (add 3 4)
    echo "$result" | fishtape
end
```

使用以下命令运行测试：

```fish
fishtape add_test.fish
```

样本输出可能如下所示：

```
TAP version 13
# Adding 3 and 4 yields 7
ok 1 - test_add passed
```

这告诉你测试成功通过了。`fishtape` 允许你构建更详细的测试并提供有用的输出，便于调试并为你的 Fish 脚本提供全面的测试覆盖。
