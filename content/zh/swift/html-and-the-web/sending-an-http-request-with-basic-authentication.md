---
date: 2024-01-20 18:02:53.456488-07:00
description: "\u6211\u4EEC\u7ECF\u5E38\u9700\u8981\u8BA9\u5E94\u7528\u7A0B\u5E8F\u901A\
  \u8FC7\u7F51\u7EDC\u4E0E\u670D\u52A1\u5668\u4EA4\u4E92\uFF0C\u53D1\u9001HTTP\u8BF7\
  \u6C42\u662F\u5176\u4E2D\u7684\u57FA\u672C\u65B9\u5F0F\u3002\u4F7F\u7528\u57FA\u672C\
  \u8BA4\u8BC1\uFF08basic authentication\uFF09\u53EF\u4EE5\u5FEB\u901F\u7B80\u5355\
  \u5730\u9A8C\u8BC1\u7528\u6237\u8EAB\u4EFD\uFF0C\u786E\u4FDD\u6570\u636E\u7684\u5B89\
  \u5168\u4EA4\u6362\u3002"
isCJKLanguage: true
lastmod: '2024-03-13T22:44:48.157347-06:00'
model: gpt-4-1106-preview
summary: "\u6211\u4EEC\u7ECF\u5E38\u9700\u8981\u8BA9\u5E94\u7528\u7A0B\u5E8F\u901A\
  \u8FC7\u7F51\u7EDC\u4E0E\u670D\u52A1\u5668\u4EA4\u4E92\uFF0C\u53D1\u9001HTTP\u8BF7\
  \u6C42\u662F\u5176\u4E2D\u7684\u57FA\u672C\u65B9\u5F0F\u3002\u4F7F\u7528\u57FA\u672C\
  \u8BA4\u8BC1\uFF08basic authentication\uFF09\u53EF\u4EE5\u5FEB\u901F\u7B80\u5355\
  \u5730\u9A8C\u8BC1\u7528\u6237\u8EAB\u4EFD\uFF0C\u786E\u4FDD\u6570\u636E\u7684\u5B89\
  \u5168\u4EA4\u6362\u3002."
title: "\u4F7F\u7528\u57FA\u672C\u8BA4\u8BC1\u53D1\u9001 HTTP \u8BF7\u6C42"
weight: 45
---

## How to (如何执行)
以下是使用Swift（最新版本）发送带有基本认证的HTTP请求的简单代码示例。

```Swift
import Foundation

// 准备URL和认证信息
if let url = URL(string: "https://your-api-endpoint.com/data") {
    var request = URLRequest(url: url)
    let username = "user"
    let password = "pass"
    let loginString = "\(username):\(password)"
    
    // 将认证信息转为base64
    if let loginData = loginString.data(using: .utf8) {
        let base64LoginString = loginData.base64EncodedString()
        
        // 在请求头里添加认证信息
        request.setValue("Basic \(base64LoginString)", forHTTPHeaderField: "Authorization")
        
        // 执行请求
        URLSession.shared.dataTask(with: request) { (data, response, error) in
            // 确保没有发生错误
            if let error = error {
                print("请求发送错误: \(error)")
                return
            }
            
            // 确定我们得到了数据
            if let data = data, let dataString = String(data: data, encoding: .utf8) {
                print("服务器响应:\n\(dataString)")
            }
        }.resume()
    }
}
```

## Deep Dive (深入了解)
基本认证是HTTP协议中一种老旧但广泛支持的简单认证形式。它通过发送用户名和密码的Base64编码形式来验证用户身份。虽然基本认证很方便，但因为它不是特别安全（比如在非HTTPS连接中容易遭到中间人攻击），所以它通常不适用于敏感数据的传输。更安全的做法是使用令牌（token-based authentication）或OAuth等更复杂的认证机制。在Swift中实现基本认证主要是通过URLRequest对象进行的，它允许你设置请求的各种参数，包括HTTP头部。

## See Also (相关链接)
- [Swift Documentation](https://swift.org/documentation/)
- [Apple's URLSession Tutorial](https://developer.apple.com/documentation/foundation/urlsession)
- [HTTP Basic Authentication Scheme RFC](https://tools.ietf.org/html/rfc7617)
