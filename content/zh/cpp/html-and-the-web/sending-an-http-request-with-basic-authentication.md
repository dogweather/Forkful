---
title:                "使用基本认证发送 HTTP 请求"
aliases:
- zh/cpp/sending-an-http-request-with-basic-authentication.md
date:                  2024-01-20T18:01:31.202502-07:00
model:                 gpt-4-1106-preview
simple_title:         "使用基本认证发送 HTTP 请求"

tag:                  "HTML and the Web"
isCJKLanguage:        true
editURL:              "https://github.com/dogweather/forkful/blob/master/content/zh/cpp/sending-an-http-request-with-basic-authentication.md"
---

{{< edit_this_page >}}

## What & Why? (什么和为什么？)

发送带基本认证的HTTP请求让你的应用可以安全访问需要用户名和密码的资源。程序员这么做为了保护数据，避免未授权访问。

## How to: (如何实现：)

```C++
#include <iostream>
#include <curl/curl.h>
#include <string>

// 初始化CURL，设置基本认证信息，发送GET请求，并清理
void sendGetRequestWithBasicAuth(const std::string& url, 
                                 const std::string& username, 
                                 const std::string& password) {
    CURL *curl = curl_easy_init();
    if(curl) {
        CURLcode res;
        std::string userPass = username + ":" + password;
        // 设置目标URL和认证信息
        curl_easy_setopt(curl, CURLOPT_URL, url.c_str());
        curl_easy_setopt(curl, CURLOPT_HTTPAUTH, (long)CURLAUTH_BASIC);
        curl_easy_setopt(curl, CURLOPT_USERPWD, userPass.c_str());
        
        // 发送请求
        res = curl_easy_perform(curl);
        
        if(res != CURLE_OK) {
            std::cerr << "CURL error: " << curl_easy_strerror(res) << '\n';
        }
        
        // 清理
        curl_easy_cleanup(curl);
    }
}

int main() {
    std::string url = "http://yourapi.com/data";
    std::string username = "user";
    std::string password = "pass";
    
    sendGetRequestWithBasicAuth(url, username, password);
    
    return 0;
}
```
这段代码没有输出。成功时，它默默工作。失败时，会在控制台打印错误信息。

## Deep Dive (深入探究):

发送带基本认证的HTTP请求是互联网早期常用的一种认证方式，它简单但不是最安全。基本认证通过编码'用户名:密码'（并不是加密！）并附加在请求头上。现代web更推荐使用基于token的方法，比如OAuth。

C++中发送HTTP请求可以用不同库，比如CURL或Boost.Beast。CURL是C语言库，但可以很好地和C++集成。不同于CURL，Boost.Beast是纯C++，利用了现代C++特性。选择合适的库取决于项目需求和个人偏好。

确保你了解了HTTPS和加密的重要性。基本认证如果不通过HTTPS发送，用户名和密码可能被拦截。

## See Also (另请参阅):

- CURL官方文档: https://curl.se/libcurl/c/libcurl.html
- Boost.Beast库: https://www.boost.org/doc/libs/release/libs/beast/
- RFC 7617 The 'Basic' HTTP Authentication Scheme: https://tools.ietf.org/html/rfc7617
- OAuth 2.0: https://oauth.net/2/
