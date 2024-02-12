---
title:                "वेब पेज डाउनलोड करना"
aliases:
- hi/php/downloading-a-web-page.md
date:                  2024-01-20T17:44:43.979478-07:00
model:                 gpt-4-1106-preview
simple_title:         "वेब पेज डाउनलोड करना"

tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/hi/php/downloading-a-web-page.md"
---

{{< edit_this_page >}}

## What & Why? (क्या और क्यों?)

वेब पेज डाउनलोडिंग मतलब वेब साइट की सामग्री को उसके सर्वर से आपके कंप्यूटर पर लाना। प्रोग्रामर्स इसे करते हैं ताकि डेटा का विश्लेषण कर सकें या उसे अपने ऐप्लिकेशन में उपयोग कर सकें।

## How to: (कैसे करें:)

PHP में वेब पेज को डाउनलोड करने के लिए `file_get_contents()` फंक्शन एक सरल तरीका है।

```php
<?php
// वेब पेज का URL
$url = 'http://example.com';

// URL से HTML कंटेंट प्राप्त करना
$html = file_get_contents($url);

// अगर आवश्यक हो, तो आप HTML कंटेंट की प्रोसेसिंग कर सकते हैं
// ...

// HTML कंटेंट दिखाना
echo $html;
?>
```

आउटपुट में `http://example.com` का HTML कोड दिखेगा।

## Deep Dive (गहन जानकारी):

इंटरनेट की शुरुआत से ही वेब पेजेज का डेटा प्राप्त करने का कांसेप्ट रहा है। `file_get_contents()` साधारण और सीधा होने के बावजूद, जटिल जरूरतों के लिए cURL लाइब्रेरी का उपयोग होता है, जैसे कि HTTP headers को सेट करना, POST डेटा भेजना, या एरर हैंडलिंग करना। पीएचपी की cURL लाइब्रेरी पूर्ण-प्रचालक HTTP क्लाइंट है।

पिछले संस्करणों में जहां `fopen()` के साथ रिमोट URL को हैंडल करने के लिए `allow_url_fopen` इनी सेटिंग की आवश्यकता होती थी, वर्तमान में। इसे अधिक सुरक्षित तरीके से करने के लिए cURL का उपयोग पसंद किया जाता है।

## See Also (और देखें):

- PHP Manual on file_get_contents(): https://www.php.net/manual/en/function.file-get-contents.php
- PHP Manual on cURL: https://www.php.net/manual/en/book.curl.php
- HTTP client Guzzle (जो cURL का उपयोग करता है): https://github.com/guzzle/guzzle
