---
aliases:
- /uk/arduino/working-with-yaml/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:25:07.625892-07:00
description: "YAML (YAML Ain't Markup Language) - \u0446\u0435 \u0441\u0442\u0430\u043D\
  \u0434\u0430\u0440\u0442 \u0441\u0435\u0440\u0456\u0430\u043B\u0456\u0437\u0430\u0446\
  \u0456\u0457 \u0434\u0430\u043D\u0438\u0445, \u044F\u043A\u0438\u0439 \u043B\u0435\
  \u0433\u043A\u043E \u0447\u0438\u0442\u0430\u0454\u0442\u044C\u0441\u044F \u043B\
  \u044E\u0434\u044C\u043C\u0438, \u0456 \u043C\u043E\u0436\u0435 \u0432\u0438\u043A\
  \u043E\u0440\u0438\u0441\u0442\u043E\u0432\u0443\u0432\u0430\u0442\u0438\u0441\u044F\
  \ \u0434\u043B\u044F \u0444\u0430\u0439\u043B\u0456\u0432 \u043A\u043E\u043D\u0444\
  \u0456\u0433\u0443\u0440\u0430\u0446\u0456\u0457,\u2026"
lastmod: 2024-02-18 23:09:00.838276
model: gpt-4-0125-preview
summary: "YAML (YAML Ain't Markup Language) - \u0446\u0435 \u0441\u0442\u0430\u043D\
  \u0434\u0430\u0440\u0442 \u0441\u0435\u0440\u0456\u0430\u043B\u0456\u0437\u0430\u0446\
  \u0456\u0457 \u0434\u0430\u043D\u0438\u0445, \u044F\u043A\u0438\u0439 \u043B\u0435\
  \u0433\u043A\u043E \u0447\u0438\u0442\u0430\u0454\u0442\u044C\u0441\u044F \u043B\
  \u044E\u0434\u044C\u043C\u0438, \u0456 \u043C\u043E\u0436\u0435 \u0432\u0438\u043A\
  \u043E\u0440\u0438\u0441\u0442\u043E\u0432\u0443\u0432\u0430\u0442\u0438\u0441\u044F\
  \ \u0434\u043B\u044F \u0444\u0430\u0439\u043B\u0456\u0432 \u043A\u043E\u043D\u0444\
  \u0456\u0433\u0443\u0440\u0430\u0446\u0456\u0457,\u2026"
title: "\u0420\u043E\u0431\u043E\u0442\u0430 \u0437 YAML"
---

{{< edit_this_page >}}

## Що і Чому?

YAML (YAML Ain't Markup Language) - це стандарт серіалізації даних, який легко читається людьми, і може використовуватися для файлів конфігурації, міжпрограмного спілкування та зберігання даних. Програмісти звертаються до YAML для проектів на Arduino, щоб спростити процес налаштування своїх застосунків, роблячи зміну параметрів простішою без поглиблення у код, підвищуючи зрозумілість та спрощуючи обмін конфігураціями.

## Як це робити:

Робота з YAML безпосередньо на Arduino не така проста, як у вищих програмних середовищах через обмеження пам'яті та відсутність вбудованих бібліотек обробки YAML. Однак, для проектів, яким потрібен аналіз або генерація YAML, типовий підхід включає використання супутнього комп'ютера (наприклад, Raspberry Pi) або конвертацію файлів YAML до більш пристосованого для Arduino формату (наприклад, JSON) за допомогою зовнішніх скриптів. Для демонстрації зосередимося на останньому підході за допомогою популярної бібліотеки: ArduinoJson.

**Крок 1:** Конвертуйте вашу конфігурацію YAML у JSON. Для цього можна використати онлайн-інструменти або утиліти командного рядка, такі як `yq`.

YAML файл (`config.yaml`):
```yaml
wifi:
  ssid: "YourSSID"
  password: "YourPassword"
```

Конвертовано у JSON (`config.json`):
```json
{
  "wifi": {
    "ssid": "YourSSID",
    "password": "YourPassword"
  }
}
```

**Крок 2:** Використовуйте бібліотеку ArduinoJson для аналізу JSON файлу у вашому скетчі для Arduino. Спершу, вам потрібно встановити бібліотеку ArduinoJson через Менеджер Бібліотек у Arduino IDE.

**Крок 3:** Завантажте та аналізуйте JSON у вашому коді. З огляду на обмеження пам'яті Arduino, уявіть, що рядок JSON зберігається у змінній або читається з SD-карти.

Зразок скетча для Arduino:
```cpp
#include <ArduinoJson.h>

const char* jsonConfig = "{\"wifi\":{\"ssid\":\"YourSSID\",\"password\":\"YourPassword\"}}";

void setup() {
  Serial.begin(9600);

  StaticJsonDocument<200> doc;
  DeserializationError error = deserializeJson(doc, jsonConfig);

  if (error) {
    Serial.print(F("deserializeJson() failed: "));
    Serial.println(error.f_str());
    return;
  }

  const char* ssid = doc["wifi"]["ssid"]; // "YourSSID"
  const char* password = doc["wifi"]["password"]; // "YourPassword"

  Serial.print("SSID: ");
  Serial.println(ssid);
  Serial.print("Password: ");
  Serial.println(password);
}

void loop() {
  // Тут нічого немає у цьому прикладі
}
```

Результат після запуску скетча:
```
SSID: YourSSID
Password: YourPassword
```

Цей підхід, що включає конвертацію в JSON та використання бібліотеки ArduinoJson, дозволяє контролювати налаштування YAML у проектах Arduino, обходячи прямий аналіз YAML на мікроконтролері.
