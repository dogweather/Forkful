---
date: 2024-01-20 17:59:23.946796-07:00
description: "HTTP \u0905\u0928\u0941\u0930\u094B\u0927 \u092D\u0947\u091C\u0928\u093E\
  \ \u0935\u0947\u092C \u0938\u0930\u094D\u0935\u0930 \u092A\u0930 \u090F\u0915 \u0928\
  \u093F\u0936\u094D\u091A\u093F\u0924 \u0921\u0947\u091F\u093E \u0905\u0928\u0941\
  \u0930\u094B\u0927 \u092F\u093E \u092A\u094D\u0930\u0924\u093F\u0915\u094D\u0930\
  \u093F\u092F\u093E \u092D\u0947\u091C\u0928\u0947 \u0915\u0940 \u092A\u094D\u0930\
  \u0915\u094D\u0930\u093F\u092F\u093E \u0939\u0948\u0964 \u092A\u094D\u0930\u094B\
  \u0917\u094D\u0930\u093E\u092E\u0930\u094D\u0938 \u0910\u0938\u093E \u0921\u0947\
  \u091F\u093E \u092A\u093E\u0928\u0947, \u0935\u0947\u092C \u0938\u0930\u094D\u0935\
  \u093F\u0938\u0947\u091C \u0938\u0947 \u092C\u093E\u0924 \u0915\u0930\u0928\u0947\
  \ \u092F\u093E IoT\u2026"
lastmod: '2024-03-13T22:44:52.769505-06:00'
model: gpt-4-1106-preview
summary: "HTTP \u0905\u0928\u0941\u0930\u094B\u0927 \u092D\u0947\u091C\u0928\u093E\
  \ \u0935\u0947\u092C \u0938\u0930\u094D\u0935\u0930 \u092A\u0930 \u090F\u0915 \u0928\
  \u093F\u0936\u094D\u091A\u093F\u0924 \u0921\u0947\u091F\u093E \u0905\u0928\u0941\
  \u0930\u094B\u0927 \u092F\u093E \u092A\u094D\u0930\u0924\u093F\u0915\u094D\u0930\
  \u093F\u092F\u093E \u092D\u0947\u091C\u0928\u0947 \u0915\u0940 \u092A\u094D\u0930\
  \u0915\u094D\u0930\u093F\u092F\u093E \u0939\u0948\u0964 \u092A\u094D\u0930\u094B\
  \u0917\u094D\u0930\u093E\u092E\u0930\u094D\u0938 \u0910\u0938\u093E \u0921\u0947\
  \u091F\u093E \u092A\u093E\u0928\u0947, \u0935\u0947\u092C \u0938\u0930\u094D\u0935\
  \u093F\u0938\u0947\u091C \u0938\u0947 \u092C\u093E\u0924 \u0915\u0930\u0928\u0947\
  \ \u092F\u093E IoT \u0921\u093F\u0935\u093E\u0907\u0938\u0947\u0938 \u0915\u094B\
  \ \u0928\u0947\u091F\u0935\u0930\u094D\u0915 \u0938\u0947 \u091C\u094B\u0921\u093C\
  \u0928\u0947 \u0915\u0947 \u0932\u093F\u090F \u0915\u0930\u0924\u0947 \u0939\u0948\
  \u0902\u0964."
title: "HTTP \u0905\u0928\u0941\u0930\u094B\u0927 \u092D\u0947\u091C\u0928\u093E"
weight: 44
---

## कैसे करें:
```Arduino
#include <ESP8266WiFi.h>

const char* ssid = "yourSSID";
const char* password = "yourPASSWORD";

const char* host = "example.com";

void setup() {
  Serial.begin(115200);
  delay(10);

  // वाई-फाई से कनेक्ट करें
  Serial.println();
  Serial.println();
  Serial.print("Connecting to ");
  Serial.println(ssid);

  WiFi.begin(ssid, password);

  while (WiFi.status() != WL_CONNECTED) {
    delay(500);
    Serial.print(".");
  }

  Serial.println("");
  Serial.println("WiFi connected");
  Serial.println("IP address: ");
  Serial.println(WiFi.localIP());

  // सर्वर से कनेक्ट करें
  Serial.print("Connecting to ");
  Serial.println(host);

  // Use WiFiClient class to create TCP connections
  WiFiClient client;
  const int httpPort = 80;
  if (!client.connect(host, httpPort)) {
    Serial.println("Connection failed");
    return;
  }

  // HTTP अनुरोध भेजें
  String url = "/path";
  Serial.print("Requesting URL: ");
  Serial.println(url);
  client.print(String("GET ") + url + " HTTP/1.1\r\n" +
               "Host: " + host + "\r\n" + 
               "Connection: close\r\n\r\n");

  while (client.connected()) {
    String line = client.readStringUntil('\n');
    if (line == "\r") {
      Serial.println("Headers received");
      break;
    }
  }

  // रिस्पॉन्स पढ़ें
  String line = client.readStringUntil('\n');
  if (line.startsWith("{\"state\":\"success\"")) {
    Serial.println("Received a successful response from the server");
  } else {
    Serial.println("Received an unexpected response from the server");
  }
}

void loop() {
  // Nothing to do here
}
```

## गहराई से जानकारी:
ESP8266 मॉड्यूल अरुदिनो को वाई-फाई से जोड़कर HTTP अनुरोध भेजने की क्षमता देता है। एक समय में, प्रोग्रामर्स इथरनेट शील्ड के सहारे नेटवर्क ऑपरेशन्स करते थे, लेकिन इसके वायरलेस संस्करण ने IoT परियोजनाओं में क्रांति ला दी है। REST एपीआई और Webhooks जैसे तकनीकें हमें वेब सर्विसेज से बातचीत के लिए HTTP अनुरोधों का इस्तेमाल करने देती हैं।

## देखें भी:
- [Arduino HttpClient library](https://www.arduino.cc/en/Tutorial/LibraryExamples/HttpClient)
- [Arduino WiFi library documentation](https://www.arduino.cc/en/Reference/WiFi)
