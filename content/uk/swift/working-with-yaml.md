---
title:                "Робота з YAML"
aliases:
- uk/swift/working-with-yaml.md
date:                  2024-02-03T19:27:20.100598-07:00
model:                 gpt-4-0125-preview
simple_title:         "Робота з YAML"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/uk/swift/working-with-yaml.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Що і чому?
YAML, що означає "YAML Ain't Markup Language" (YAML - це не мова розмітки), є стандартом серіалізації даних, дружнім до користувача, для всіх мов програмування. Програмісти використовують його для файлів конфігурації, міжпроцесного обміну повідомленнями та зберігання даних, оскільки його читабельність набагато ближча до звичайної англійської мови порівняно з іншими форматами даних, як-от XML або JSON, що робить його простішим для розуміння і написання.

## Як це зробити:
Swift не включає вбудованої підтримки для парсингу та серіалізації YAML, що вимагає використання сторонніх бібліотек. Популярним вибором є `Yams`, бібліотека для роботи з YAML у Swift.

Спочатку вам потрібно додати `Yams` до вашого проекту. Якщо ви використовуєте Swift Package Manager, ви можете додати його як залежність у ваш файл `Package.swift`:

```swift
dependencies: [
    .package(url: "https://github.com/jpsim/Yams.git", from: "4.0.0")
]
```

### Парсинг YAML у Swift
Припустимо, у вас є така конфігурація YAML для простого додатку:

```yaml
name: MyApp
version: 1.0
environment: development
features:
  - login
  - notifications
```

Ось як ви можете розібрати цей YAML рядок у Swift за допомогою `Yams`:

```swift
import Yams

let yamlString = """
name: MyApp
version: 1.0
environment: development
features:
  - login
  - notifications
"""

do {
    if let data = try Yams.load(yaml: yamlString) as? [String: Any] {
        print(data)
        // Приклад доступу до розібраних даних
        if let name = data["name"] as? String {
            print("Назва додатку: \(name)")
        }
    }
} catch {
    print("Помилка парсингу YAML: \(error)")
}
```

Приклад виводу:

```
["name": MyApp, "version": 1.0, "environment": "development", "features": ["login", "notifications"]]
Назва додатку: MyApp
```

### Серіалізація об'єктів Swift у YAML
Конвертація об'єкту Swift назад у рядок YAML також проста за допомогою `Yams`. Припустимо, у вас є та сама структура даних, яка потребує серіалізації:

```swift
let appInfo = [
    "name": "MyApp",
    "version": 1.0,
    "environment": "development",
    "features": ["login", "notifications"]
] as [String : Any]

do {
    let yamlString = try Yams.dump(object: appInfo)
    print(yamlString)
} catch {
    print("Помилка серіалізації у YAML: \(error)")
}
```

Це виробить рядок, відформатований у YAML:

```yaml
environment: development
features:
  - login
  - notifications
name: MyApp
version: 1.0
```

Ці приклади демонструють основні операції для роботи з YAML у додатках Swift. Пам'ятайте, хоча YAML перевершує у читабельності для людини та простоті використання, завжди враховуйте специфічні потреби вашого додатку, особливо стосовно продуктивності та складності, при виборі вашого формату серіалізації даних.
