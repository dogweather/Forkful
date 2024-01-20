---
title:                "Друк відлагоджувального виводу"
html_title:           "Arduino: Друк відлагоджувального виводу"
simple_title:         "Друк відлагоджувального виводу"
programming_language: "Swift"
category:             "Swift"
tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/uk/swift/printing-debug-output.md"
---

{{< edit_this_page >}}

## Що це таке & Навіщо це потрібно?

Друк відлагоджувального виводу - це процес відображення внутрішніх даних програми, покликаний допомагти розробникам краще розуміти, як працює їх код. Це неоціненний інструмент для пошуку і виправлення помилок, а також відлагодження сложних алгоритмів.
 
## Як це зробити: 

У Swift це можна зробити декількома способами, але найпопулярнішим є використання команди `print()`. 

```swift
let name = "Kyiv"
print("City name is \(name)")
```

Вивід:
```
City name is Kyiv
```

## Поглиблений аналіз

`print()` - це найпростіший спосіб використання друку відлагоджувального виводу в Swift, але не єдиний. В історичному контексті, `print()` прийшов з мови Objective-C, де використовувався `NSLog()`. 

Альтернативи включають використання `debugPrint()`, яке подає більше інформації про типи даних, а також `dump()`, для виводу структурованої інформації про складні об'єкти і структури даних.

Але важливо враховувати, що незалежно від методу, вивід відлагоджувального друку треба використовувати з обережністю, особливо в ситуаціях, коли він може впливати на продуктивність програми або на її бажану функціональність.

## Дивіться також:

- [Apple Developer Documentation](https://developer.apple.com/documentation/swift/1541053-print)
- [Using NSLog and print for debugging with Swift](https://fluffy.es/nslog-print-swift/)
- [5 Tips for Effective Debugging](https://www.raywenderlich.com/113259/debugging-ios-swift)