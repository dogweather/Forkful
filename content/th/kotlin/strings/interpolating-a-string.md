---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 21:47:58.111030-06:00
description: "\u0E01\u0E32\u0E23\u0E43\u0E2A\u0E48\u0E02\u0E49\u0E2D\u0E04\u0E27\u0E32\
  \u0E21\u0E43\u0E19\u0E2A\u0E15\u0E23\u0E34\u0E07\u0E2B\u0E23\u0E37\u0E2D String\
  \ interpolation \u0E0A\u0E48\u0E27\u0E22\u0E43\u0E2B\u0E49\u0E04\u0E38\u0E13\u0E1D\
  \u0E31\u0E07\u0E15\u0E31\u0E27\u0E41\u0E1B\u0E23\u0E40\u0E02\u0E49\u0E32\u0E44\u0E1B\
  \u0E43\u0E19\u0E2A\u0E15\u0E23\u0E34\u0E07\u0E42\u0E14\u0E22\u0E15\u0E23\u0E07\u2026"
lastmod: '2024-03-17T21:57:56.160266-06:00'
model: gpt-4-0125-preview
summary: "\u0E01\u0E32\u0E23\u0E43\u0E2A\u0E48\u0E02\u0E49\u0E2D\u0E04\u0E27\u0E32\
  \u0E21\u0E43\u0E19\u0E2A\u0E15\u0E23\u0E34\u0E07\u0E2B\u0E23\u0E37\u0E2D String\
  \ interpolation \u0E0A\u0E48\u0E27\u0E22\u0E43\u0E2B\u0E49\u0E04\u0E38\u0E13\u0E1D\
  \u0E31\u0E07\u0E15\u0E31\u0E27\u0E41\u0E1B\u0E23\u0E40\u0E02\u0E49\u0E32\u0E44\u0E1B\
  \u0E43\u0E19\u0E2A\u0E15\u0E23\u0E34\u0E07\u0E42\u0E14\u0E22\u0E15\u0E23\u0E07 \u0E0B\
  \u0E36\u0E48\u0E07\u0E21\u0E35\u0E1B\u0E23\u0E30\u0E42\u0E22\u0E0A\u0E19\u0E4C\u0E43\
  \u0E19\u0E01\u0E32\u0E23\u0E2A\u0E23\u0E49\u0E32\u0E07\u0E02\u0E49\u0E2D\u0E04\u0E27\
  \u0E32\u0E21\u0E17\u0E35\u0E48\u0E21\u0E35\u0E04\u0E27\u0E32\u0E21\u0E22\u0E37\u0E14\
  \u0E2B\u0E22\u0E38\u0E48\u0E19\u0E41\u0E25\u0E30\u0E2D\u0E48\u0E32\u0E19\u0E07\u0E48\
  \u0E32\u0E22\u0E42\u0E14\u0E22\u0E44\u0E21\u0E48\u0E15\u0E49\u0E2D\u0E07\u0E43\u0E0A\
  \u0E49\u0E01\u0E32\u0E23\u0E15\u0E48\u0E2D\u0E02\u0E49\u0E2D\u0E04\u0E27\u0E32\u0E21\
  \u0E17\u0E35\u0E48\u0E14\u0E39\u0E22\u0E38\u0E48\u0E07\u0E22\u0E32\u0E01."
title: "\u0E01\u0E32\u0E23\u0E41\u0E17\u0E23\u0E01\u0E04\u0E48\u0E32\u0E25\u0E07\u0E43\
  \u0E19\u0E2A\u0E15\u0E23\u0E34\u0E07"
weight: 8
---

## วิธีการ:
```kotlin
fun main() {
    val name = "Alex"
    val age = 29
    // ใส่ตัวแปรลงในสตริง
    val greeting = "สวัสดี, ฉันชื่อ $name และฉันอายุ $age ปี"
    println(greeting) // ผลลัพธ์: สวัสดี, ฉันชื่อ Alex และฉันอายุ 29 ปี

    // ใช้ Expression ภายในข้อความ
    val announcement = "ปีหน้า, ฉันจะมีอายุ ${age + 1} ปี!"
    println(announcement) // ผลลัพธ์: ปีหน้า, ฉันจะมีอายุ 30 ปี!
}
```

## ลงลึก
Kotlin ได้รับอิทธิพลจากภาษาสมัยใหม่อื่นๆ และได้แนะนำการใส่ข้อความในสตริงหรือ String interpolation เป็นทางเลือกที่สะอาดยิ่งขึ้นเมื่อเปรียบเทียบกับการต่อข้อความสตริงใน Java มันช่วยปรับปรุงความสามารถในการอ่านและทำให้โค้ดง่ายขึ้น

ในอดีต, Java ต้องใช้การต่อข้อความที่ซับซ้อนโดยใช้ `+` ซึ่งอาจอ่านได้ยากและมีประสิทธิภาพต่ำ เนื่องจากสร้างวัตถุสตริงหลายตัว Kotlin มีวิธีการที่มากขึ้นกำลัง, อนุญาตให้ฝังตัวแปรและประเมินค่า Expression ภายในสตริง

ภายใต้ฮูด, Kotlin คอมไพล์การใส่ข้อความนี้เป็นการดำเนินงานของ `StringBuilder` หรือการต่อข้อความ ขึ้นอยู่กับความซับซ้อน, ลดภาระให้กับผู้พัฒนา

ตัวเลือกที่ไม่ใช่การใส่ข้อความ ได้แก่ เครื่องมือสำหรับการจัดการข้อความขนาดใหญ่ แต่ในโค้ด, การใส่ข้อความโดยทั่วไปเป็นวิธีที่เร็วที่สุดในการรวมเนื้อหาที่เป็นไดนามิก

## ดูเพิ่มเติม
- [เอกสารของ Kotlin เกี่ยวกับสตริงแม่แบบ](https://kotlinlang.org/docs/basic-syntax.html#string-templates)
- [API `String` ของ Kotlin](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-string/)
- [การเปรียบเทียบประสิทธิภาพการต่อข้อความสตริงของ Java และ Kotlin](https://proandroiddev.com/the-cost-of-kotlin-language-features-8f7035e9dcb9)
