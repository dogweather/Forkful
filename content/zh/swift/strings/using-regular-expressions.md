---
title:                "使用正则表达式"
date:                  2024-02-03T19:18:26.113268-07:00
model:                 gpt-4-0125-preview
simple_title:         "使用正则表达式"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/zh/swift/using-regular-expressions.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## 是什么 & 为什么?
正则表达式（或称regex）是形成搜索模式的字符序列，常用于字符串匹配或操纵任务。程序员利用它们进行从数据验证和解析到转换的各种任务，使它们成为各种编程语言中文本处理和操纵任务不可或缺的工具，包括Swift。

## 如何操作:
Swift对正则表达式的原生支持使用了`NSRegularExpression`类，以及String类的范围和替换方法。下面是一个例子，展示了如何使用正则表达式在文本块中查找并高亮电子邮件地址:

```swift
import Foundation

let text = "Contact us at support@example.com or feedback@example.org for more information."
let regexPattern = "[A-Z0-9a-z._%+-]+@[A-Za-z0-9.-]+\\.[A-Za-z]{2,}"

do {
    let regex = try NSRegularExpression(pattern: regexPattern)
    let matches = regex.matches(in: text, range: NSRange(text.startIndex..., in: text))

    if !matches.isEmpty {
        for match in matches {
            let range = Range(match.range, in: text)!
            print("Found: \(text[range])")
        }
    } else {
        print("No matches found.")
    }
} catch {
    print("Regex error: \(error.localizedDescription)")
}

// 样例输出:
// Found: support@example.com
// Found: feedback@example.org
```

对于更复杂或注重便利性的场景，你可以使用第三方库，如SwiftRegex，它简化了语法并扩展了可能性。尽管Swift的标准库很强大，一些开发者还是更喜欢这些库，因为它们的语法简洁且有额外的特性。这里是一个使用假想的第三方库执行类似任务的方式:

```swift
// 假设有一个叫做SwiftRegex的库已经被引入
let text = "Reach out at hello@world.com or visit our website."
let emailPattern = "[A-Z0-9a-z._%+-]+@[A-Za-z0-9.-]+\\.[A-Za-z]{2,}"

let emails = text.matches(for: emailPattern) // SwiftRegex提供的假想方法
if emails.isEmpty {
    print("No email addresses found.")
} else {
    emails.forEach { email in
        print("Found: \(email)")
    }
}

// 假想输出，假设`matches(for:)`方法在SwiftRegex中存在:
// Found: hello@world.com
```

这个例子展示了如何使用第三方正则表达式包来简化在字符串内找到匹配项的过程，假设像`matches(for:)`这样的便利方法存在。重要的是要参考相应的第三方库文档以获得准确的语法和方法可用性。
