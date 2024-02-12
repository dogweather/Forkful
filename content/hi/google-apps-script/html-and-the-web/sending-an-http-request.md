---
title:                "एचटीटीपी अनुरोध भेजना"
aliases:
- /hi/google-apps-script/sending-an-http-request/
date:                  2024-02-01T22:02:35.537677-07:00
model:                 gpt-4-0125-preview
simple_title:         "एचटीटीपी अनुरोध भेजना"
tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/hi/google-apps-script/sending-an-http-request.md"
changelog:
  - 2024-02-01, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## क्या और क्यों?

Google Apps Script में HTTP अनुरोध भेजने का अर्थ है बाहरी वेब सर्वर या API को प्रोग्रामैटिक रूप से कॉल करना। प्रोग्रामर्स इसे वेब सेवाओं से डेटा प्राप्त करने या डेटा भेजने के लिए करते हैं, अपने Google Apps Script प्रोजेक्ट्स में वेब संसाधनों और कार्यक्षमताओं की विशाल दुनिया को एकीकृत करते हुए।

## कैसे:

Google Apps Script में, HTTP अनुरोध भेजने का प्रमुख तरीका `UrlFetchApp` सेवा का उपयोग करना है। यह सेवा HTTP GET और POST अनुरोधों को करने के तरीके प्रदान करती है। यहाँ JSON डेटा प्राप्त करने के लिए GET अनुरोध करने का एक सरल उदाहरण है:

```javascript
function fetchJsonData() {
  var url = 'https://api.example.com/data';
  var response = UrlFetchApp.fetch(url);
  var json = response.getContentText();
  var data = JSON.parse(json);
  
  Logger.log(data);
}
```

POST अनुरोध के लिए, जिसका आम तौर पर सर्वर को डेटा भेजने के लिए उपयोग किया जाता है, आपको विकल्प पैरामीटर में अधिक विवरण शामिल करने की आवश्यकता है:

```javascript
function postExample() {
  var url = 'https://api.example.com/post';
  var payload = {
    key1: 'value1',
    key2: 'value2'
  };
  
  var options = {
    'method' : 'post',
    'contentType': 'application/json',
    // JavaScript ऑब्जेक्ट को JSON स्ट्रिंग में परिवर्तित करें
    'payload' : JSON.stringify(payload)
  };
  
  var response = UrlFetchApp.fetch(url, options);
  Logger.log(response.getContentText());
}
```

ये स्निपेट्स GET और POST अनुरोधों के मूल कार्यान्वयन दिखाते हैं। आउटपुट API प्रतिसाद पर निर्भर करेगा और इसे Google Apps Script के Logger में देखा जा सकता है।

## गहराई में जानें

Google Apps Script की `UrlFetchApp` सेवा अपने आरंभ से काफी विकसित हुई है, हैडर्स, पेलोड और फ़ाइल अपलोड के लिए मल्टीपार्ट/फॉर्म-डेटा संभालने जैसी सुविधाओं के साथ HTTP अनुरोधों पर अधिक नियंत्रण प्रदान करती है। बाहरी वेब सेवाओं को एकीकृत करने के लिए यह एक सीधा साधन प्रदान करती है, हालाँकि, अधिक उन्नत बैकएंड भाषाओं से आने वाले डेवलपर्स को इसकी कार्यक्षमता पायथन के `requests` या Node.js में JavaScript के `fetch` API जैसी लाइब्रेरियों की तुलना में कुछ हद तक सीमित लग सकती है।

एक महत्वपूर्ण सीमा Google Apps Script के लिए निष्पादन समय सीमा है, जो लंबे समय तक चलने वाले अनुरोधों को प्रभावित करती है। इसके अलावा, जबकि `UrlFetchApp` व्यापक परिदृश्यों को कवर करता है, OAuth प्रमाणीकरण संभालने या बहुत बड़े पेलोड्स से निपटने जैसे अधिक जटिल परिदृश्यों को संभालने के लिए रचनात्मक समाधानों की आवश्यकता हो सकती है या अतिरिक्त Google Cloud संसाधनों का लाभ उठाने की आवश्यकता हो सकती है।

फिर भी, ज्यादातर एकीकरण के लिए जिनसे Google Workspace डेवलपर्स मुलाकात करते हैं—डेटा प्राप्ति से लेकर बाहरी सेवाओं को अपडेट पोस्ट करने तक—`UrlFetchApp` एक शक्तिशाली, सुलभ उपकरण प्रदान करता है। इसका Google Apps Script में एकीकरण का मतलब है कि बाहरी लाइब्रेरियों या जटिल सेटअप की कोई आवश्यकता नहीं है, HTTP अनुरोधों को Google Apps Script की सीमाओं के भीतर सीधे तौर पर क्रियान्वित करना अपेक्षाकृत सरल बनाता है। वेब API की दुनिया जैसे विस्तार करते हैं, `UrlFetchApp` Google Apps Script कार्यक्रमों को Google के इकोसिस्टम से परे दुनिया के साथ इंटरैक्ट करने के लिए एक महत्वपूर्ण पुल बना रहता है।
