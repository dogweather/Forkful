---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 21:48:27.657074-06:00
description: "\u0E01\u0E32\u0E23\u0E08\u0E31\u0E14\u0E23\u0E30\u0E40\u0E1A\u0E35\u0E22\
  \u0E1A\u0E42\u0E04\u0E49\u0E14\u0E40\u0E02\u0E49\u0E32\u0E44\u0E1B\u0E43\u0E19\u0E1F\
  \u0E31\u0E07\u0E01\u0E4C\u0E0A\u0E31\u0E19\u0E0A\u0E48\u0E27\u0E22\u0E41\u0E1A\u0E48\
  \u0E07\u0E2A\u0E04\u0E23\u0E34\u0E1B\u0E15\u0E4C\u0E02\u0E2D\u0E07\u0E04\u0E38\u0E13\
  \u0E2D\u0E2D\u0E01\u0E40\u0E1B\u0E47\u0E19\u0E2A\u0E48\u0E27\u0E19\u0E17\u0E35\u0E48\
  \u0E2A\u0E32\u0E21\u0E32\u0E23\u0E16\u0E19\u0E33\u0E01\u0E25\u0E31\u0E1A\u0E21\u0E32\
  \u0E43\u0E0A\u0E49\u0E44\u0E14\u0E49\u0E2D\u0E35\u0E01. \u0E17\u0E31\u0E49\u0E07\
  \u0E2B\u0E21\u0E14\u0E19\u0E35\u0E49\u0E40\u0E01\u0E35\u0E48\u0E22\u0E27\u0E01\u0E31\
  \u0E1A\u0E01\u0E32\u0E23\u0E17\u0E33\u0E43\u0E2B\u0E49\u0E42\u0E04\u0E49\u0E14\u0E02\
  \u0E2D\u0E07\u0E04\u0E38\u0E13\u0E2A\u0E30\u0E2D\u0E32\u0E14 \u0E08\u0E31\u0E14\u0E01\
  \u0E32\u0E23\u0E44\u0E14\u0E49\u0E07\u0E48\u0E32\u0E22\u2026"
lastmod: '2024-03-17T21:57:56.734650-06:00'
model: gpt-4-0125-preview
summary: "\u0E01\u0E32\u0E23\u0E08\u0E31\u0E14\u0E23\u0E30\u0E40\u0E1A\u0E35\u0E22\
  \u0E1A\u0E42\u0E04\u0E49\u0E14\u0E40\u0E02\u0E49\u0E32\u0E44\u0E1B\u0E43\u0E19\u0E1F\
  \u0E31\u0E07\u0E01\u0E4C\u0E0A\u0E31\u0E19\u0E0A\u0E48\u0E27\u0E22\u0E41\u0E1A\u0E48\
  \u0E07\u0E2A\u0E04\u0E23\u0E34\u0E1B\u0E15\u0E4C\u0E02\u0E2D\u0E07\u0E04\u0E38\u0E13\
  \u0E2D\u0E2D\u0E01\u0E40\u0E1B\u0E47\u0E19\u0E2A\u0E48\u0E27\u0E19\u0E17\u0E35\u0E48\
  \u0E2A\u0E32\u0E21\u0E32\u0E23\u0E16\u0E19\u0E33\u0E01\u0E25\u0E31\u0E1A\u0E21\u0E32\
  \u0E43\u0E0A\u0E49\u0E44\u0E14\u0E49\u0E2D\u0E35\u0E01."
title: "\u0E01\u0E32\u0E23\u0E08\u0E31\u0E14\u0E23\u0E30\u0E40\u0E1A\u0E35\u0E22\u0E1A\
  \u0E42\u0E04\u0E49\u0E14\u0E40\u0E02\u0E49\u0E32\u0E44\u0E1B\u0E43\u0E19\u0E1F\u0E31\
  \u0E07\u0E01\u0E4C\u0E0A\u0E31\u0E19"
weight: 18
---

## วิธีการ:
ลองนึกภาพว่าคุณกำลังเขียนสคริปต์เร็ว ๆ ที่จะทักทายผู้ใช้:

```Ruby
def greet(name)
  "Hello, #{name}!"
end

puts greet("Alice")   # ผลลัพท์: Hello, Alice!
puts greet("Bob")     # ผลลัพท์: Hello, Bob!
```

หรืออาจถึงเวลาที่คุณกำลังคำนวณพื้นที่ของวงกลม:

```Ruby
def circle_area(radius)
  Math::PI * radius ** 2
end

puts circle_area(5)   # ผลลัพท์: 78.53981633974483
```

เนี๊ยบและง่ายต่อการจัดการ, ใช่ไหม?

## การขุดลึก
ความคิดของฟังก์ชั่น หรือที่รู้จักในชื่อเมธอดใน Ruby ไม่ใช่เรื่องใหม่ - มันเก่าแก่เท่าที่การเขียนโปรแกรมมีมา เคยมีผู้กลับมาถึงยุค 1950s, subroutines, อย่างที่พวกเขาถูกเรียก, ถูกนำมาใช้เพื่อลดความซ้ำซ้อน

มีทางเลือกอื่นอีกไหม? แน่นอน, คุณมีโค้ดแบบอินไลน์, คุณอาจเลือกทำ OOP ด้วยคลาสและอ็อบเจ็กต์, หรือแม้แต่ฟังก์ชันแบบฟังก์ชันนัลด้วย lambdas และ procs แต่ฟังก์ชันนั้นเป็นหลักการของโค้ดที่เรียบร้อย ต้องการประสิทธิภาพ? ตัวแปรในฟังก์ชันมีความเร็วสูง และฟังก์ชันสามารถส่งคืนค่าทันทีด้วย `return`

ในแง่ของการใช้งาน, คุณสามารถกำหนดฟังก์ชันด้วย `def` และจบด้วย `end` คุณสามารถตั้งค่าพารามิเตอร์เริ่มต้น, ใช้ตัวดำเนินการ splat สำหรับฟังก์ชัน variadic, และอีกมากมาย ฟังก์ชันสามารถเรียบง่ายหรือซับซ้อนตามที่คุณต้องการ

## ดูเพิ่มเติม
- [เอกสารการใช้เมธอดของ Ruby](https://ruby-doc.org/core-2.7.0/Method.html)
- [เรียนรู้การโปรแกรมคอมพิวเตอร์โดย Chris Pine](https://pine.fm/LearnToProgram/)
- [การออกแบบโอบเจกต์ที่มีประโยชน์ใน Ruby โดย Sandi Metz](https://www.poodr.com/)
