---
aliases:
- /hi/elixir/sending-an-http-request-with-basic-authentication/
date: 2024-01-20 18:01:41.787107-07:00
description: "HTTP \u0905\u0928\u0941\u0930\u094B\u0927 \u092C\u0947\u0938\u093F\u0915\
  \ \u092A\u094D\u0930\u092E\u093E\u0923\u0940\u0915\u0930\u0923 \u0915\u0947 \u0938\
  \u093E\u0925 \u092D\u0947\u091C\u0928\u093E \u090F\u0915 \u092A\u094D\u0930\u0915\
  \u094D\u0930\u093F\u092F\u093E \u0939\u0948 \u091C\u093F\u0938\u092E\u0947\u0902\
  \ \u0935\u0947\u092C \u0938\u0947\u0935\u093E \u092A\u094D\u0930\u092E\u093E\u0923\
  \u093F\u0924 \u0915\u0930\u0924\u0940 \u0939\u0948 \u0915\u093F \u0905\u0928\u0941\
  \u0930\u094B\u0927 \u092D\u0947\u091C\u0928\u0947 \u0935\u093E\u0932\u093E \u0909\
  \u0938 \u0921\u0947\u091F\u093E \u0924\u0915 \u092A\u0939\u0941\u0901\u091A\u0928\
  \u0947 \u0915\u093E \u0939\u0915\u0926\u093E\u0930 \u0939\u0948\u0964 \u092A\u094D\
  \u0930\u094B\u0917\u094D\u0930\u093E\u092E\u0930\u2026"
lastmod: 2024-02-18 23:09:02.802483
model: gpt-4-1106-preview
summary: "HTTP \u0905\u0928\u0941\u0930\u094B\u0927 \u092C\u0947\u0938\u093F\u0915\
  \ \u092A\u094D\u0930\u092E\u093E\u0923\u0940\u0915\u0930\u0923 \u0915\u0947 \u0938\
  \u093E\u0925 \u092D\u0947\u091C\u0928\u093E \u090F\u0915 \u092A\u094D\u0930\u0915\
  \u094D\u0930\u093F\u092F\u093E \u0939\u0948 \u091C\u093F\u0938\u092E\u0947\u0902\
  \ \u0935\u0947\u092C \u0938\u0947\u0935\u093E \u092A\u094D\u0930\u092E\u093E\u0923\
  \u093F\u0924 \u0915\u0930\u0924\u0940 \u0939\u0948 \u0915\u093F \u0905\u0928\u0941\
  \u0930\u094B\u0927 \u092D\u0947\u091C\u0928\u0947 \u0935\u093E\u0932\u093E \u0909\
  \u0938 \u0921\u0947\u091F\u093E \u0924\u0915 \u092A\u0939\u0941\u0901\u091A\u0928\
  \u0947 \u0915\u093E \u0939\u0915\u0926\u093E\u0930 \u0939\u0948\u0964 \u092A\u094D\
  \u0930\u094B\u0917\u094D\u0930\u093E\u092E\u0930\u2026"
title: "\u092C\u0947\u0938\u093F\u0915 \u092A\u094D\u0930\u092E\u093E\u0923\u0940\u0915\
  \u0930\u0923 \u0915\u0947 \u0938\u093E\u0925 HTTP \u0905\u0928\u0941\u0930\u094B\
  \u0927 \u092D\u0947\u091C\u0928\u093E"
---

{{< edit_this_page >}}

## क्या और क्यों?

HTTP अनुरोध बेसिक प्रमाणीकरण के साथ भेजना एक प्रक्रिया है जिसमें वेब सेवा प्रमाणित करती है कि अनुरोध भेजने वाला उस डेटा तक पहुँचने का हकदार है। प्रोग्रामर इसका उपयोग अक्सर सिक्योर API एंडपॉइंट्स तक पहुँचने के लिए करते हैं।

## कैसे करें:

Elixir में HTTPoison लाइब्रेरी का उपयोग करके HTTP अनुरोध बेसिक प्रमाणीकरण के साथ भेजा जा सकता है। पहले `HTTPoison` जोड़ें अपने `mix.exs` फाइल में।

```elixir
def deps do
  [
    {:httpoison, "~> 1.8"}
  ]
end
```

फिर निम्न कोड का उपयोग करें:

```elixir
defmodule MyHTTPClient do
  def send_request do
    auth = {"my_username", "my_password"}
    options = [basic_auth: auth]
    HTTPoison.get!("https://example.com/secret-data", [], options)
  end
end
```

सैंपल आउटपुट:

```
%HTTPoison.Response{
  status_code: 200,
  body: "...",
  headers: [...],
}
```

## गहराई से जानकारी

HTTP बेसिक प्रमाणीकरण एक मानक तकनीक है जो 1990 के दशक से उपयोग में है। यह यूजरनेम और पासवर्ड को Base64 में एन्कोड करके HTTP हेडर (`Authorization`) में भेजती है। इस पद्धति का मुख्य विकल्प OAuth है, जिसे अधिक सुरक्षा के लिए इस्तेमाल किया जाता है। Elixir में, `HTTPoison` के अलावा, आप `Tesla` या `hackney` जैसे अन्य HTTP क्लाइंट्स भी इस्तेमाल कर सकते हैं।

## संबंधित स्रोत

- [HTTPoison GitHub repository](https://github.com/edgurgel/httpoison)
- [MDN Web Docs: Authorization](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Authorization)
