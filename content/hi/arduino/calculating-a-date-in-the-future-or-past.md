---
title:                "भविष्य या अतीत में तारीख की गणना"
date:                  2024-01-20T17:31:28.509004-07:00
model:                 gpt-4-1106-preview
simple_title:         "भविष्य या अतीत में तारीख की गणना"
programming_language: "Arduino"
category:             "Arduino"
tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/hi/arduino/calculating-a-date-in-the-future-or-past.md"
---

{{< edit_this_page >}}

## क्या और क्यों? (What & Why?)

भविष्य या अतीत की तारीख की गणना मतलब है आज की तारीख से कुछ दिनों को जोड़ना या घटाना। प्रोग्रामर इसे इवेंट्स की डेट, रिमाइंडर्स, या दूसरे समय-संबंधित कामों के लिए करते हैं।

## कैसे: (How to:)

Arduino बोर्ड पर आप "TimeLib.h" लाइब्रेरी का इस्तेमाल करके आसानी से तारीख की गणना कर सकते हैं:

```Arduino
#include <TimeLib.h>

void setup() {
  Serial.begin(9600);
  setTime(23, 59, 50, 4, 1, 2021); // 23:59:50, 4 January 2021
}

void loop() {
  time_t now = now();
  
  // भविष्य में 10 दिन जोड़ना
  time_t futureDate = now + 10 * SECS_PER_DAY;
  Serial.print("Future Date: ");
  Serial.println(day(futureDate));
  Serial.print("/");
  Serial.println(month(futureDate));
  Serial.print("/");
  Serial.println(year(futureDate));
  Serial.println();

  // अतीत में 10 दिन घटाना
  time_t pastDate = now - 10 * SECS_PER_DAY;
  Serial.print("Past Date: ");
  Serial.println(day(pastDate));
  Serial.print("/");
  Serial.println(month(pastDate));
  Serial.print("/");
  Serial.println(year(pastDate));
  Serial.println();

  delay(10000); // Update every 10 seconds
}
```

## गहराई में: (Deep Dive)

तारीखों को गणना करना कंप्यूटर साइंस और प्रोग्रामिंग के पुराने समस्याओं में से एक है। यह ज्यादातर प्रोग्रामर लाइब्रेरी या टाइम सर्विस API के जरिए करते हैं जो कि टाइम जोन्स, लीप ईयर और दूसरी जटिलताओं को संभालते हैं। Arduino में `TimeLib.h` एक ऐसी ही शक्तिशाली लाइब्रेरी है जो समय और तारीख की गणना में मदद करती है।

'Unix Time' प्रणाली भी लोकप्रिय है, जहां समय को 1 जनवरी 1970 से सेकंड्स में मापा जाता है। लेकिन Arduino पर डेट और टाइम के साथ काम करते वक्त, मेमोरी और प्रोसेसिंग पावर कम होने की वजह से 'TimeLib.h' जैसी लाइब्रेरीज को पसंद किया जाता है।

## संबंधित स्रोत: (See Also)

- Arduino Time Library: https://www.arduino.cc/en/Reference/Time
- Unix Time and Date Command: https://www.unixtimestamp.com/
- NTP Client for Arduino: https://github.com/arduino-libraries/NTPClient

अधिक जानकारी और कोड उदाहरण के लिए इन स्रोतों पर जाएं। यह आपकी समझ को और भी बेहतर बनाने में मदद करेंगे।
