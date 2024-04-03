---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 21:44:49.182468-06:00
description: "\u0E01\u0E32\u0E23\u0E40\u0E1B\u0E23\u0E35\u0E22\u0E1A\u0E40\u0E17\u0E35\
  \u0E22\u0E1A\u0E27\u0E31\u0E19\u0E17\u0E35\u0E48\u0E2A\u0E2D\u0E07\u0E27\u0E31\u0E19\
  \u0E2B\u0E21\u0E32\u0E22\u0E16\u0E36\u0E07\u0E01\u0E32\u0E23\u0E2B\u0E32\u0E27\u0E48\
  \u0E32\u0E27\u0E31\u0E19\u0E44\u0E2B\u0E19\u0E2D\u0E22\u0E39\u0E48\u0E01\u0E48\u0E2D\
  \u0E19\u0E2B\u0E23\u0E37\u0E2D\u0E2B\u0E25\u0E31\u0E07 \u0E2B\u0E23\u0E37\u0E2D\u0E27\
  \u0E48\u0E32\u0E17\u0E31\u0E49\u0E07\u0E2A\u0E2D\u0E07\u0E27\u0E31\u0E19\u0E40\u0E17\
  \u0E48\u0E32\u0E01\u0E31\u0E19\u0E2B\u0E23\u0E37\u0E2D\u0E44\u0E21\u0E48\u2026"
lastmod: '2024-03-17T21:57:56.493359-06:00'
model: gpt-4-0125-preview
summary: "\u0E01\u0E32\u0E23\u0E40\u0E1B\u0E23\u0E35\u0E22\u0E1A\u0E40\u0E17\u0E35\
  \u0E22\u0E1A\u0E27\u0E31\u0E19\u0E17\u0E35\u0E48\u0E2A\u0E2D\u0E07\u0E27\u0E31\u0E19\
  \u0E2B\u0E21\u0E32\u0E22\u0E16\u0E36\u0E07\u0E01\u0E32\u0E23\u0E2B\u0E32\u0E27\u0E48\
  \u0E32\u0E27\u0E31\u0E19\u0E44\u0E2B\u0E19\u0E2D\u0E22\u0E39\u0E48\u0E01\u0E48\u0E2D\
  \u0E19\u0E2B\u0E23\u0E37\u0E2D\u0E2B\u0E25\u0E31\u0E07 \u0E2B\u0E23\u0E37\u0E2D\u0E27\
  \u0E48\u0E32\u0E17\u0E31\u0E49\u0E07\u0E2A\u0E2D\u0E07\u0E27\u0E31\u0E19\u0E40\u0E17\
  \u0E48\u0E32\u0E01\u0E31\u0E19\u0E2B\u0E23\u0E37\u0E2D\u0E44\u0E21\u0E48 \u0E19\u0E31\
  \u0E01\u0E40\u0E02\u0E35\u0E22\u0E19\u0E42\u0E1B\u0E23\u0E41\u0E01\u0E23\u0E21\u0E17\
  \u0E33\u0E41\u0E1A\u0E1A\u0E19\u0E35\u0E49\u0E40\u0E1E\u0E37\u0E48\u0E2D\u0E15\u0E34\
  \u0E14\u0E15\u0E32\u0E21\u0E40\u0E2B\u0E15\u0E38\u0E01\u0E32\u0E23\u0E13\u0E4C\u0E17\
  \u0E35\u0E48\u0E02\u0E36\u0E49\u0E19\u0E2D\u0E22\u0E39\u0E48\u0E01\u0E31\u0E1A\u0E40\
  \u0E27\u0E25\u0E32 \u0E40\u0E0A\u0E48\u0E19 \u0E01\u0E32\u0E23\u0E01\u0E33\u0E2B\
  \u0E19\u0E14\u0E15\u0E32\u0E23\u0E32\u0E07\u0E07\u0E32\u0E19\u0E2B\u0E23\u0E37\u0E2D\
  \u0E01\u0E32\u0E23\u0E1A\u0E31\u0E19\u0E17\u0E36\u0E01\u0E02\u0E49\u0E2D\u0E21\u0E39\
  \u0E25\u0E15\u0E32\u0E21\u0E40\u0E27\u0E25\u0E32."
title: "\u0E40\u0E1B\u0E23\u0E35\u0E22\u0E1A\u0E40\u0E17\u0E35\u0E22\u0E1A\u0E2A\u0E2D\
  \u0E07\u0E27\u0E31\u0E19\u0E17\u0E35\u0E48"
weight: 27
---

## วิธีการ:
ใน Arduino, คุณสามารถเปรียบเทียบวันที่โดยใช้ไลบรารี `TimeLib.h` ติดตั้งมันก่อน จากนั้นลองดูโค้ดตัวอย่างนี้:

```Arduino
#include <TimeLib.h>

void setup() {
  Serial.begin(9600);
  // ตั้งค่าเวลาที่แตกต่างกันสองครั้ง (ปี, เดือน, วัน, ชั่วโมง, นาที, วินาที)
  // ที่นี่เรากำลังตั้งค่า 3 มีนาคม 2023, 8:30:00 และ 4 มีนาคม 2023, 16:45:00
  time_t firstTime = makeTime({0, 30, 8, 3, 3, 2023});
  time_t secondTime = makeTime({0, 45, 16, 4, 3, 2023});
  
  // เปรียบเทียบเวลาทั้งสอง
  if (firstTime < secondTime) {
    Serial.print("เวลาแรกอยู่ก่อน.");
  } else if (firstTime > secondTime) {
    Serial.print("เวลาที่สองอยู่ก่อน.");
  } else {
    Serial.print("ทั้งสองเวลาเท่ากัน.");
  }
}

void loop() {
  // ไม่มีอะไรที่นี่
}
```

ตัวอย่างผลลัพธ์:
```
เวลาแรกอยู่ก่อน.
```

## ลงลึก
Arduino ไม่มีการสนับสนุนฟังก์ชันในการจัดการวันและเวลาโดยตรง ดังนั้นเราจึงใช้ไลบรารีเช่น `TimeLib.h` ก่อนมีไลบรารี ผู้คนต้องคำนวณและเปรียบเทียบวันที่ด้วยตนเอง—ซึ่งเป็นงานที่ยุ่งยากเนื่องจากปีอธิกสุรทิน ความยาวของเดือนที่แตกต่างกัน และอื่นๆ

วิธีอื่นในการจัดการวันที่รวมถึงโมดูล RTC (Real Time Clock) เช่น DS3231 ซึ่งรักษาเวลาไว้แม้ว่า Arduino จะปิดอยู่ สำหรับการเปรียบเทียบ คุณยังคงต้องดึงวันที่เข้ามาในโปรแกรมของคุณและเปรียบเทียบเหมือนที่เราทำข้างต้น

เมื่อนำไปใช้ ต้องคำนึงถึงเขตเวลาและการปรับเวลาตามฤดูกาลหากจำเป็น TimeLib สามารถจัดการเวลา UTC ซึ่งหลีกเลี่ยงปัญหาเหล่านี้ได้ แต่เวลาท้องถิ่นต้องการความระมัดระวังเพิ่มเติม

## ดูเพิ่มเติม
- [เอกสารประกอบไลบรารี TimeLib](https://www.pjrc.com/teensy/td_libs_Time.html) - รายละเอียดเกี่ยวกับการใช้ไลบรารี Time.
- [ไลบรารีเวลาของ Arduino](https://github.com/PaulStoffregen/Time) - ที่เก็บ GitHub สำหรับไลบรารีเวลา.
