---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 21:47:01.318954-06:00
description: "\u0E01\u0E32\u0E23\u0E2B\u0E32\u0E04\u0E27\u0E32\u0E21\u0E22\u0E32\u0E27\
  \u0E02\u0E2D\u0E07\u0E2A\u0E15\u0E23\u0E34\u0E07\u0E2B\u0E21\u0E32\u0E22\u0E16\u0E36\
  \u0E07\u0E01\u0E32\u0E23\u0E19\u0E31\u0E1A\u0E2D\u0E31\u0E01\u0E02\u0E23\u0E30\u0E02\
  \u0E2D\u0E07\u0E21\u0E31\u0E19 \u0E40\u0E23\u0E32\u0E17\u0E33\u0E40\u0E0A\u0E48\u0E19\
  \u0E19\u0E35\u0E49\u0E40\u0E1E\u0E37\u0E48\u0E2D\u0E15\u0E23\u0E27\u0E08\u0E2A\u0E2D\
  \u0E1A\u0E02\u0E49\u0E2D\u0E21\u0E39\u0E25\u0E17\u0E35\u0E48\u0E1B\u0E49\u0E2D\u0E19\
  , \u0E27\u0E19\u0E23\u0E2D\u0E1A\u0E1C\u0E48\u0E32\u0E19\u0E2D\u0E31\u0E01\u0E02\
  \u0E23\u0E30, \u0E08\u0E31\u0E14\u0E2A\u0E23\u0E23\u0E17\u0E23\u0E31\u0E1E\u0E22\
  \u0E32\u0E01\u0E23, \u0E2B\u0E23\u0E37\u0E2D\u0E40\u0E1E\u0E35\u0E22\u0E07\u0E41\
  \u0E04\u0E48\u0E04\u0E27\u0E32\u0E21\u0E2D\u0E22\u0E32\u0E01\u0E23\u0E39\u0E49 \u2013\
  \u2026"
lastmod: '2024-03-17T21:57:56.216545-06:00'
model: gpt-4-0125-preview
summary: "\u0E01\u0E32\u0E23\u0E2B\u0E32\u0E04\u0E27\u0E32\u0E21\u0E22\u0E32\u0E27\
  \u0E02\u0E2D\u0E07\u0E2A\u0E15\u0E23\u0E34\u0E07\u0E2B\u0E21\u0E32\u0E22\u0E16\u0E36\
  \u0E07\u0E01\u0E32\u0E23\u0E19\u0E31\u0E1A\u0E2D\u0E31\u0E01\u0E02\u0E23\u0E30\u0E02\
  \u0E2D\u0E07\u0E21\u0E31\u0E19 \u0E40\u0E23\u0E32\u0E17\u0E33\u0E40\u0E0A\u0E48\u0E19\
  \u0E19\u0E35\u0E49\u0E40\u0E1E\u0E37\u0E48\u0E2D\u0E15\u0E23\u0E27\u0E08\u0E2A\u0E2D\
  \u0E1A\u0E02\u0E49\u0E2D\u0E21\u0E39\u0E25\u0E17\u0E35\u0E48\u0E1B\u0E49\u0E2D\u0E19\
  , \u0E27\u0E19\u0E23\u0E2D\u0E1A\u0E1C\u0E48\u0E32\u0E19\u0E2D\u0E31\u0E01\u0E02\
  \u0E23\u0E30, \u0E08\u0E31\u0E14\u0E2A\u0E23\u0E23\u0E17\u0E23\u0E31\u0E1E\u0E22\
  \u0E32\u0E01\u0E23, \u0E2B\u0E23\u0E37\u0E2D\u0E40\u0E1E\u0E35\u0E22\u0E07\u0E41\
  \u0E04\u0E48\u0E04\u0E27\u0E32\u0E21\u0E2D\u0E22\u0E32\u0E01\u0E23\u0E39\u0E49 \u2013\
  \ \u0E01\u0E32\u0E23\u0E17\u0E23\u0E32\u0E1A\u0E02\u0E19\u0E32\u0E14\u0E40\u0E1B\
  \u0E47\u0E19\u0E40\u0E23\u0E37\u0E48\u0E2D\u0E07\u0E2A\u0E33\u0E04\u0E31\u0E0D."
title: "\u0E04\u0E49\u0E19\u0E2B\u0E32\u0E04\u0E27\u0E32\u0E21\u0E22\u0E32\u0E27\u0E02\
  \u0E2D\u0E07\u0E2A\u0E15\u0E23\u0E34\u0E07"
weight: 7
---

## วิธีการ:
ใน C#, คุณสมบัติ `string.Length` ให้คุณทราบจำนวนอักขระในสตริง นี่คือวิธีใช้งาน:

```C#
using System;

class Program
{
    static void Main()
    {
        string example = "Hello, World!";
        Console.WriteLine(example.Length); // ผลลัพธ์: 13
    }
}
```

ง่าย, ใช่ไหม? แต่จำไว้ว่า, มันนับ *อักขระ* ไม่ใช่ไบต์ กับอีโมจิหรืออักขระพิเศษ, สถานการณ์อาจซับซ้อนขึ้น จะอธิบายเพิ่มเติมในภายหลัง

## ลงลึก
ในอดีต, การหาความยาวของสตริงเกี่ยวข้องกับการจัดการและการจัดการหน่วยความจำในการเขียนโปรแกรม เนื่องจาก C# เป็นภาษาระดับสูง, มันทำให้การทำงานระดับต่ำเหล่านั้นหายไป อย่างไรก็ตาม, การรู้ว่ามีอะไรอยู่ใต้ฝาครอบก็ดี

มีทางเลือกอื่นหรือ? แน่นอน! คุณอาจเห็น `example.ToCharArray().Length` อยู่ในโค้ดทั่วไป, แต่มันเป็นเพียงการทำงานเพิ่มเติมเพื่อผลลัพธ์เดียวกัน

ตอนนี้, เกี่ยวกับอักขระที่ซับซ้อน เช่น C# คุณสมบัติ `Length` นับจำนวน `char` ออบเจกต์ของสตริง, แต่ละตัวแทนหน่วยรหัส UTF-16 นั่นโอเคจนกระทั่งคุณพบกับ *คู่ surrogate* – อักขระเช่นอีโมจิที่ต้องการสอง `char` ออบเจกต์ นี่คือสิ่งที่: `Length` นับพวกมันเป็นสอง ใช่แล้ว

สำหรับการนับที่แม่นยำของ *อักขระที่เห็นได้ชัด* หรือ *กลุ่มกราฟีม*, คุณจะต้องหันไปใช้คลาส `StringInfo` ของ System.Globalization:

```C#
using System;
using System.Globalization;

class Program
{
    static void Main()
    {
        string example = "👍"; // อิโมจิชูมือ

        Console.WriteLine(example.Length); // ผลลัพธ์: 2 <- เพราะคู่ surrogate!
        Console.WriteLine(new StringInfo(example).LengthInTextElements); // ผลลัพธ์: 1
    }
}
```

เข้าใจความแตกต่างหรือไม่? ไม่เพียงแค่ทฤษฎี; มันอาจส่งผลต่อการประมวลผลข้อความในทางที่มีความหมาย

## ดูเพิ่มเติม
สำรวจเพิ่มเติมด้วยทรัพยากรเหล่านี้:

- [เอกสารอ้างอิงอย่างเป็นทางการของ Microsoft เกี่ยวกับสตริง](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/strings/)
- [การเข้าใจ Unicode และ UTF-16](https://unicodebook.readthedocs.io/unicode_encodings.html)
- [เอกสารของคลาส StringInfo](https://docs.microsoft.com/en-us/dotnet/api/system.globalization.stringinfo?view=net-6.0)

รู้จักสตริงของคุณ, จัดการกับพวกมันอย่างมีปัญญา, และเขียนโค้ดที่นับได้ – ในทุกความหมาย
