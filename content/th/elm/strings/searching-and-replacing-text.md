---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 21:50:33.576780-06:00
description: "\u0E01\u0E32\u0E23\u0E04\u0E49\u0E19\u0E2B\u0E32\u0E41\u0E25\u0E30\u0E41\
  \u0E17\u0E19\u0E17\u0E35\u0E48\u0E02\u0E49\u0E2D\u0E04\u0E27\u0E32\u0E21\u0E0A\u0E48\
  \u0E27\u0E22\u0E43\u0E2B\u0E49\u0E04\u0E38\u0E13\u0E2B\u0E32\u0E2A\u0E15\u0E23\u0E34\
  \u0E07\u0E17\u0E35\u0E48\u0E40\u0E08\u0E32\u0E30\u0E08\u0E07\u0E41\u0E25\u0E30\u0E41\
  \u0E17\u0E19\u0E17\u0E35\u0E48\u0E14\u0E49\u0E27\u0E22\u0E2A\u0E34\u0E48\u0E07\u0E2D\
  \u0E37\u0E48\u0E19\u2026"
lastmod: '2024-03-17T21:57:56.113892-06:00'
model: gpt-4-0125-preview
summary: "\u0E01\u0E32\u0E23\u0E04\u0E49\u0E19\u0E2B\u0E32\u0E41\u0E25\u0E30\u0E41\
  \u0E17\u0E19\u0E17\u0E35\u0E48\u0E02\u0E49\u0E2D\u0E04\u0E27\u0E32\u0E21\u0E0A\u0E48\
  \u0E27\u0E22\u0E43\u0E2B\u0E49\u0E04\u0E38\u0E13\u0E2B\u0E32\u0E2A\u0E15\u0E23\u0E34\
  \u0E07\u0E17\u0E35\u0E48\u0E40\u0E08\u0E32\u0E30\u0E08\u0E07\u0E41\u0E25\u0E30\u0E41\
  \u0E17\u0E19\u0E17\u0E35\u0E48\u0E14\u0E49\u0E27\u0E22\u0E2A\u0E34\u0E48\u0E07\u0E2D\
  \u0E37\u0E48\u0E19 \u0E40\u0E2B\u0E25\u0E48\u0E32\u0E42\u0E1B\u0E23\u0E41\u0E01\u0E23\
  \u0E21\u0E40\u0E21\u0E2D\u0E23\u0E4C\u0E43\u0E0A\u0E49\u0E21\u0E31\u0E19\u0E43\u0E19\
  \u0E17\u0E38\u0E01\u0E2D\u0E22\u0E48\u0E32\u0E07\u0E15\u0E31\u0E49\u0E07\u0E41\u0E15\
  \u0E48\u0E01\u0E32\u0E23\u0E41\u0E01\u0E49\u0E44\u0E02\u0E04\u0E33\u0E1C\u0E34\u0E14\
  \u0E44\u0E1B\u0E08\u0E19\u0E16\u0E36\u0E07\u0E01\u0E32\u0E23\u0E23\u0E35\u0E41\u0E1F\
  \u0E01\u0E40\u0E15\u0E2D\u0E23\u0E4C\u0E42\u0E04\u0E49\u0E14\u0E2D\u0E22\u0E48\u0E32\
  \u0E07\u0E21\u0E35\u0E1B\u0E23\u0E30\u0E2A\u0E34\u0E17\u0E18\u0E34\u0E20\u0E32\u0E1E\
  ."
title: "\u0E01\u0E32\u0E23\u0E04\u0E49\u0E19\u0E2B\u0E32\u0E41\u0E25\u0E30\u0E41\u0E17\
  \u0E19\u0E17\u0E35\u0E48\u0E02\u0E49\u0E2D\u0E04\u0E27\u0E32\u0E21"
weight: 10
---

## วิธีการ:
ใน Elm, คุณสามารถใช้โมดูล `String` เพื่อแทนที่ส่วนหนึ่งของสตริงได้ มาดูการทำงานกัน:

```Elm
import String

replaceExample : String
replaceExample =
    String.replace "cat" "dog" "The cat sat on the mat"

-- ผลลัพธ์จะเป็น: "The dog sat on the mat"
```

## ศึกษาลึกลงไป
วิธีการจัดการการค้นหาและแทนที่สตริงใน Elm ค่อนข้างตรงไปตรงมา คล้ายกับภาษาฟังก์ชันอื่นๆ ไม่ใช้ regular expressions ในภาษาหลักโดยค่าเริ่มต้น ไม่เหมือนกับภาษาอย่าง JavaScript ความเรียบง่ายนี้ถูกออกแบบมาเพื่อรักษาเป้าหมายของ Elm ในเรื่องความเชื่อถือได้และการบำรุงรักษา

ในแง่ประวัติศาสตร์, Elm มุ่งหวังที่จะให้ชุดฟังก์ชันที่ในตัวที่แข็งแกร่งซึ่งจัดการกับงานทั่วไป และค้นหา-แทนที่ก็ไม่ต่างกัน โมดูล `String` ของ Elm ได้รับการอยู่มาตั้งแต่สมัยแรกๆ แม้ว่าจะมีการเปลี่ยนแปลงตามที่ภาษาพัฒนาไป

ทางเลือกในการใช้ฟังก์ชัน `String.replace` อาจรวมถึงการเขียนตรรกะค้นหาและแทนที่ของคุณเอง หรือการดึงแพ็คเกจเพิ่มเติมเข้ามาที่ขยายความสามารถในการจัดการสตริงของ Elm เช่นการค้นหาที่ใช้ regex

ในแง่ของการนำไปใช้งาน, ฟังก์ชัน `String.replace` ของ Elm เป็นฟังก์ชันแบบบริสุทธิ์ นั่นหมายความว่ามันผลิตผลลัพธ์เดียวกันเสมอสำหรับอินพุตที่กำหนดและไม่มีผลข้างเคียง – เป็นหลักการหลักในการออกแบบของ Elm มันใช้อัลกอริทึมที่มีประสิทธิภาพอยู่ภายใต้ประทุน แต่ภาษานั้นซ่อนความซับซ้อนไว้เพื่อให้คุณสามารถโฟกัสไปที่การเขียนโค้ดได้โดยไม่ต้องกังวลเรื่องเล็กน้อย

## ดูเพิ่มเติม
- เอกสารของโมดูล Elm `String`: https://package.elm-lang.org/packages/elm/core/latest/String
- บทนำเกี่ยวกับ regex ใน Elm โดยใช้แพ็คเกจ elm/regex: https://package.elm-lang.org/packages/elm/regex/latest
- การประมวลผลสตริงในการเขียนโปรแกรมฟังก์ชัน: https://en.wikipedia.org/wiki/Functional_programming
