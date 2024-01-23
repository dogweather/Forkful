---
title:                "基本認証を使用したHTTPリクエストの送信"
date:                  2024-01-20T18:01:21.049212-07:00
model:                 gpt-4-1106-preview
simple_title:         "基本認証を使用したHTTPリクエストの送信"
programming_language: "C++"
category:             "C++"
tag:                  "HTML and the Web"
isCJKLanguage:        true
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ja/cpp/sending-an-http-request-with-basic-authentication.md"
---

{{< edit_this_page >}}

## What & Why?
何とは何か？そしてなぜ？

HTTPリクエストに基本認証を付けて送ることで、アクセスを許可されたユーザーだけが情報を取得できるように制限します。プログラマーはこれを使ってセキュリティを保ちます。

## How to:
どうやって？

```C++
#include <iostream>
#include <curl/curl.h>

static size_t WriteCallback(void *contents, size_t size, size_t nmemb, void *userp) {
    ((std::string*)userp)->append((char*)contents, size * nmemb);
    return size * nmemb;
}

int main() {
    CURL *curl;
    CURLcode res;
    std::string readBuffer;
    
    curl = curl_easy_init();
    if(curl) {
        std::string userPwd = "username:password"; // ベーシック認証のユーザー名とパスワード

        curl_easy_setopt(curl, CURLOPT_URL, "http://example.com/resource");
        curl_easy_setopt(curl, CURLOPT_WRITEFUNCTION, WriteCallback);
        curl_easy_setopt(curl, CURLOPT_WRITEDATA, &readBuffer);
        curl_easy_setopt(curl, CURLOPT_USERPWD, userPwd.c_str());
        curl_easy_setopt(curl, CURLOPT_HTTPAUTH, CURLAUTH_BASIC);

        res = curl_easy_perform(curl);
        
        if (res != CURLE_OK) {
            std::cerr << "curl_easy_perform() failed: " << curl_easy_strerror(res) << std::endl;
        } else {
            std::cout << readBuffer << std::endl; // HTTPレスポンスの内容を表示
        }
        
        curl_easy_cleanup(curl);
    }
    return 0;
}
```
出力例:
```
<html>
<body>
<p>認証された内容がここに表示されます。</p>
</body>
</html>
```

## Deep Dive:
深いダイブ

基本認証は、RFC 7617で定義されています。ユーザーネームとパスワードをコロンで連結し、Base64でエンコードします。比較的単純だが、HTTPSを使わないと情報漏洩のリスクがあります。

代わりにOAuthなどのよりセキュアな手法が利用されることもあります。ただ、簡単な内部システムやテスト用のケースでは、基本認証が使われることも多いです。

CURLはC言語のライブラリですが、C++からも使えます。設定は`curl_easy_setopt`を通じて行い、`CURLOPT_USERPWD`でユーザーネームとパスワードを設定します。これにより、HTTPヘッダに認証情報が組み込まれます。

## See Also:
参照してください

- libcurl公式ドキュメント: https://curl.se/libcurl/
- RFC 7617, 'The 'Basic' HTTP Authentication Scheme': https://tools.ietf.org/html/rfc7617
- Base64エンコード: https://ja.wikipedia.org/wiki/Base64
- OAuth: https://oauth.net/
