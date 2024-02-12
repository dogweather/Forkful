---
title:                "使用基本认证发送 HTTP 请求"
aliases:
- /zh/typescript/sending-an-http-request-with-basic-authentication/
date:                  2024-01-20T18:02:35.587785-07:00
model:                 gpt-4-1106-preview
simple_title:         "使用基本认证发送 HTTP 请求"

tag:                  "HTML and the Web"
isCJKLanguage:        true
editURL:              "https://github.com/dogweather/forkful/blob/master/content/zh/typescript/sending-an-http-request-with-basic-authentication.md"
---

{{< edit_this_page >}}

## What & Why? (什么及为什么?)
在TypeScript中，发送带有基本认证的HTTP请求，意味着将用户名和密码加密后作为请求头部发送，以实现用户认证。程序员这样做是为了安全地访问受保护的资源。

## How to: (如何操作:)
```TypeScript
import axios from 'axios';

const url = 'https://api.example.com/data';
const username = 'yourUsername';
const password = 'yourPassword';

const basicAuth = 'Basic ' + btoa(username + ':' + password);

axios.get(url, {
  headers: { 'Authorization': basicAuth }
})
.then(response => {
  console.log('Data retrieved:', response.data);
})
.catch(error => {
  console.error('Error fetching data:', error);
});
```

Sample output:
```
Data retrieved: { /* ...response data... */ }
```

## Deep Dive (深入探讨)
发送带基本认证的HTTP请求是早期认证方式。它简单但不是最安全的，因为基本认证可被中间人攻击。所以，总是在HTTPS上使用它。现在，有更安全的替代方法，如OAuth和JWT。在构建`axios`请求时，要编码用户名和密码，使用`btoa`函数。然而，最近的浏览器环境和Node.js有内置方法处理这种编码问题。

## See Also (另请参阅)
- MDN 关于 HTTP 基本认证: https://developer.mozilla.org/en-US/docs/Web/HTTP/Authentication
- Node.js 如何处理基本认证: https://nodejs.dev/learn/authenticating-nodejs-requests
- HTTP 安全最佳实践: https://owasp.org/www-project-top-ten/
- `axios` 库文档: https://axios-http.com/docs/intro
- JWT 认证机制: https://jwt.io/introduction/
- OAuth 官方网站: https://oauth.net/
