---
title:                "下载网页"
date:                  2024-01-20T17:44:30.259986-07:00
model:                 gpt-4-1106-preview
simple_title:         "下载网页"
programming_language: "Javascript"
category:             "Javascript"
tag:                  "HTML and the Web"
isCJKLanguage:        true
editURL:              "https://github.com/dogweather/forkful/blob/master/content/zh/javascript/downloading-a-web-page.md"
---

{{< edit_this_page >}}

## What & Why? (是什么？为什么？)
下载网页意味着获取网页上的内容并且保存到你的设备上。程序员通常这么做来分析或者处理网页数据，或者是创建网页的离线版本。

## How to: (如何操作：)
使用JavaScript，你可以轻松下载网页。以下例子展示了如何使用`fetch`API和Node.js中的`https`模块来实现。

```Javascript
// 在浏览器中使用Fetch API
fetch('https://example.com')
  .then(response => response.text())
  .then(data => console.log(data))
  .catch(error => console.error(error));

// 在Node.js中使用https模块
const https = require('https');
const fs = require('fs');

https.get('https://example.com', (res) => {
  let data = '';
  res.on('data', (chunk) => {
    data += chunk;
  });
  res.on('end', () => {
    fs.writeFileSync('example.html', data);
  });
}).on('error', (err) => {
  console.error(err.message);
});
```

输出会是`example.com`的HTML源码，存放在控制台或`example.html`文件中。

## Deep Dive (深入了解)
早期，下载网页更多是通过服务器端脚本来完成的，比如使用PHP的`file_get_contents`或者Python的`urllib`。随着JavaScript的成熟，特别是Node.js的出现，JavaScript也能胜任这个任务。 `fetch`API是现在浏览器中流行的选择，因为它基于Promise，简化了异步操作。在Node.js中，之前通常使用`request`库，但自从`https`模块的改进后，人们开始更多用它来处理HTTP请求。备选方案还包括了`axios`等库，这些库可以提供更多功能并简化错误处理。

下载网页时，确保了解目标网站的`robots.txt`文件和服务条款，避免违反了爬虫协议。

## See Also (另请参阅)
- MDN Web Docs上的Fetch API：https://developer.mozilla.org/zh-CN/docs/Web/API/Fetch_API
- Node.js官方文档中的HTTPS模块：https://nodejs.org/api/https.html
- Axios库：https://github.com/axios/axios
