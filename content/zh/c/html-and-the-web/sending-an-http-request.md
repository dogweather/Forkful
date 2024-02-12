---
title:                "发送HTTP请求"
date:                  2024-02-03T18:08:25.059773-07:00
model:                 gpt-4-0125-preview
simple_title:         "发送HTTP请求"
tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/zh/c/sending-an-http-request.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## 什么 & 为什么？

发送HTTP请求包括创建并向Web服务器发送请求，以检索或提交数据。程序员在C语言中执行此操作是为了与Web API交互、下载网页或直接从其应用程序中与其他网络服务进行通信。

## 如何操作：

要在C语言中发送HTTP请求，通常需要依赖诸如libcurl之类的库，因为C语言没有内置对网络协议的支持。这里有一个使用libcurl执行GET请求的简单示例：

首先，确保您的系统上安装了libcurl。然后，在源文件中包含必要的头文件并链接libcurl库：

```c
#include <stdio.h>
#include <curl/curl.h>

int main(void) {
    CURL *curl;
    CURLcode res;

    curl = curl_easy_init(); // 初始化一个libcurl句柄
    if(curl) {
        // 设置接收libcurl句柄的URL
        curl_easy_setopt(curl, CURLOPT_URL, "http://example.com");
        // 定义一个回调以获取数据
        curl_easy_setopt(curl, CURLOPT_WRITEFUNCTION, NULL); 
        
        // 执行请求，res将获取返回代码
        res = curl_easy_perform(curl);
        // 检查错误
        if(res != CURLE_OK)
            fprintf(stderr, "curl_easy_perform() failed: %s\n",
                    curl_easy_strerror(res));

        // 始终清理
        curl_easy_cleanup(curl);
    }
    return 0;
}
```

使用类似`gcc -o http_request http_request.c -lcurl`的命令编译此代码，运行它应执行对"http://example.com"的简单GET请求。

### 样本输出

由于示例没有处理服务器的响应，运行它不会产生除潜在错误消息之外的可见输出。整合回调函数以处理接收到的数据对于有意义的交互至关重要。

## 深入探讨

从C程序发送HTTP请求的概念依托于该语言的强大网络能力，以及由于C本身是一种底层语言而没有内置的高级互联网协议支持，因此需要外部库。在专用库如libcurl出现之前，程序员历史上会手动使用C语言中的套接字编程，这是一个复杂而乏味的过程，用于与Web服务器交互。

基于C的libcurl简化了该过程，抽象了套接字编程和HTTP协议细节的繁琐之处。它支持超出HTTP/HTTPS的多种协议，包括FTP、SMTP等，使其成为C语言中网络编程的多用途工具。

虽然在C语言中使用libcurl进行HTTP请求在实践中很实用，但现代编程通常倾向于使用内置支持此类任务的语言，如Python（requests库）或JavaScript（Fetch API）。这些替代品提供了更简单、更可读的语法，但牺牲了通过直接套接字操作和精细调整库使用可能在C中实现的细粒度控制和性能优化。

对于关键性能应用或需要直接系统级交互的情况，C仍然是一个可行的选项，特别是有了libcurl这样的库简化了网络通信的复杂性。然而，对于大多数高级Web交互，探索更专门的Web编程语言可能会更有效。
