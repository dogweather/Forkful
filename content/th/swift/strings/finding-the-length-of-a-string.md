---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 21:46:52.620071-06:00
description: "\u0E01\u0E32\u0E23\u0E2B\u0E32\u0E04\u0E27\u0E32\u0E21\u0E22\u0E32\u0E27\
  \u0E02\u0E2D\u0E07\u0E2A\u0E15\u0E23\u0E34\u0E07\u0E2B\u0E21\u0E32\u0E22\u0E16\u0E36\
  \u0E07\u0E01\u0E32\u0E23\u0E04\u0E49\u0E19\u0E2B\u0E32\u0E27\u0E48\u0E32\u0E21\u0E35\
  \u0E15\u0E31\u0E27\u0E2D\u0E31\u0E01\u0E29\u0E23\u0E2D\u0E22\u0E39\u0E48\u0E01\u0E35\
  \u0E48\u0E15\u0E31\u0E27\u0E43\u0E19\u0E19\u0E31\u0E49\u0E19 \u0E42\u0E1B\u0E23\u0E41\
  \u0E01\u0E23\u0E21\u0E40\u0E21\u0E2D\u0E23\u0E4C\u0E17\u0E33\u0E40\u0E0A\u0E48\u0E19\
  \u0E19\u0E35\u0E49\u0E40\u0E1E\u0E37\u0E48\u0E2D\u0E15\u0E23\u0E27\u0E08\u0E2A\u0E2D\
  \u0E1A\u0E02\u0E49\u0E2D\u0E21\u0E39\u0E25\u0E17\u0E35\u0E48\u0E44\u0E14\u0E49\u0E23\
  \u0E31\u0E1A, \u0E01\u0E32\u0E23\u0E08\u0E31\u0E14\u0E01\u0E32\u0E23\u0E02\u0E49\
  \u0E2D\u0E04\u0E27\u0E32\u0E21,\u2026"
lastmod: '2024-03-17T21:57:56.553220-06:00'
model: gpt-4-0125-preview
summary: "\u0E01\u0E32\u0E23\u0E2B\u0E32\u0E04\u0E27\u0E32\u0E21\u0E22\u0E32\u0E27\
  \u0E02\u0E2D\u0E07\u0E2A\u0E15\u0E23\u0E34\u0E07\u0E2B\u0E21\u0E32\u0E22\u0E16\u0E36\
  \u0E07\u0E01\u0E32\u0E23\u0E04\u0E49\u0E19\u0E2B\u0E32\u0E27\u0E48\u0E32\u0E21\u0E35\
  \u0E15\u0E31\u0E27\u0E2D\u0E31\u0E01\u0E29\u0E23\u0E2D\u0E22\u0E39\u0E48\u0E01\u0E35\
  \u0E48\u0E15\u0E31\u0E27\u0E43\u0E19\u0E19\u0E31\u0E49\u0E19 \u0E42\u0E1B\u0E23\u0E41\
  \u0E01\u0E23\u0E21\u0E40\u0E21\u0E2D\u0E23\u0E4C\u0E17\u0E33\u0E40\u0E0A\u0E48\u0E19\
  \u0E19\u0E35\u0E49\u0E40\u0E1E\u0E37\u0E48\u0E2D\u0E15\u0E23\u0E27\u0E08\u0E2A\u0E2D\
  \u0E1A\u0E02\u0E49\u0E2D\u0E21\u0E39\u0E25\u0E17\u0E35\u0E48\u0E44\u0E14\u0E49\u0E23\
  \u0E31\u0E1A, \u0E01\u0E32\u0E23\u0E08\u0E31\u0E14\u0E01\u0E32\u0E23\u0E02\u0E49\
  \u0E2D\u0E04\u0E27\u0E32\u0E21, \u0E2B\u0E23\u0E37\u0E2D\u0E40\u0E1E\u0E35\u0E22\
  \u0E07\u0E41\u0E04\u0E48\u0E40\u0E1E\u0E37\u0E48\u0E2D\u0E17\u0E33\u0E04\u0E27\u0E32\
  \u0E21\u0E40\u0E02\u0E49\u0E32\u0E43\u0E08\u0E02\u0E19\u0E32\u0E14\u0E02\u0E2D\u0E07\
  \u0E02\u0E49\u0E2D\u0E21\u0E39\u0E25\u0E02\u0E2D\u0E07\u0E1E\u0E27\u0E01\u0E40\u0E02\
  \u0E32."
title: "\u0E04\u0E49\u0E19\u0E2B\u0E32\u0E04\u0E27\u0E32\u0E21\u0E22\u0E32\u0E27\u0E02\
  \u0E2D\u0E07\u0E2A\u0E15\u0E23\u0E34\u0E07"
weight: 7
---

## วิธีการ:
ใน Swift, คุณสามารถหาความยาวของสตริงได้โดยการเข้าถึงคุณสมบัติ `count` ง่าย ๆ เลย, ลองทำดู:

```Swift
let greeting = "Hello, World!"
print(greeting.count) // ผลลัพธ์: 13
```

จำไว้ว่า Swift ถือว่าอีโมจิเป็นตัวอักษรเดียว, ขอบคุณ Unicode:

```Swift
let wave = "👋"
print(wave.count)  // ผลลัพธ์: 1
```

## ลงลึก
กลับไปในยุคของ Objective-C, การหาความยาวของสตริงไม่ได้ตรงไปตรงมาเช่นนี้—มี `length` และ `lengthOfBytes(using:)`. Swift ทำให้มันสะอาดกว่าด้วย `count`.

ระวังเกี่ยวกับอักขระประกอบ: คือตัวอักษรที่มองเห็นเป็นหนึ่งตัวแต่สร้างจากหลาย Unicode scalars. `count` จัดการกับสิ่งเหล่านี้ได้อย่างง่ายดาย

มีทางเลือกอื่นไหม? แน่นอน, คุณอาจจะเดินทางผ่านสตริงด้วยลูป, แต่นั่นเหมือนกับการประดิษฐ์ล้อใหม่และมีประสิทธิภาพน้อยกว่า

ภายใต้ฮู้ด, `count` มีความซับซ้อน O(n), ซึ่ง ‘n’ คือจำนวนตัวอักษร นั่นเป็นเพราะว่าสตริงของ Swift ไม่ใช่การรวบรวมของ `Char`s, แต่เป็นลำดับของกลุ่ม grapheme ซึ่งอาจมีความยาวแตกต่างกันไป

## ดูเพิ่มเติม
- เอกสารการใช้งาน Swift เกี่ยวกับสตริง: [เอกสารสตริง Swift](https://developer.apple.com/documentation/swift/string)
- พื้นฐาน Unicode: [คณะรักษาการ Unicode](https://home.unicode.org)
- ดำดิ่งไปเรื่องประสิทธิภาพสตริงของ Swift: [ประสิทธิภาพสตริง Swift](https://swift.org/blog/utf8-string/)
