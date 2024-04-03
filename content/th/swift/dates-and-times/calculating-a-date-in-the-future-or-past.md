---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 21:44:52.101486-06:00
description: "\u0E40\u0E04\u0E22\u0E15\u0E49\u0E2D\u0E07\u0E01\u0E32\u0E23\u0E2B\u0E32\
  \u0E27\u0E31\u0E19\u0E17\u0E35\u0E48\u0E43\u0E19\u0E2D\u0E14\u0E35\u0E15\u0E2B\u0E23\
  \u0E37\u0E2D\u0E2D\u0E19\u0E32\u0E04\u0E15\u0E44\u0E2B\u0E21? \u0E42\u0E14\u0E22\
  \u0E01\u0E32\u0E23\u0E40\u0E02\u0E35\u0E22\u0E19\u0E42\u0E1B\u0E23\u0E41\u0E01\u0E23\
  \u0E21 \u0E40\u0E23\u0E32\u0E21\u0E31\u0E01\u0E08\u0E30\u0E04\u0E33\u0E19\u0E27\u0E13\
  \u0E27\u0E31\u0E19\u0E17\u0E35\u0E48\u0E2A\u0E33\u0E2B\u0E23\u0E31\u0E1A\u0E01\u0E33\
  \u0E2B\u0E19\u0E14\u0E40\u0E2A\u0E49\u0E19\u0E15\u0E32\u0E22 \u0E01\u0E32\u0E23\u0E40\
  \u0E15\u0E37\u0E2D\u0E19\u0E04\u0E27\u0E32\u0E21\u0E08\u0E33 \u0E2B\u0E23\u0E37\u0E2D\
  \u0E40\u0E2B\u0E15\u0E38\u0E01\u0E32\u0E23\u0E13\u0E4C\u0E15\u0E48\u0E32\u0E07\u0E46\
  \u2026"
lastmod: '2024-03-17T21:57:56.574482-06:00'
model: gpt-4-0125-preview
summary: "\u0E40\u0E04\u0E22\u0E15\u0E49\u0E2D\u0E07\u0E01\u0E32\u0E23\u0E2B\u0E32\
  \u0E27\u0E31\u0E19\u0E17\u0E35\u0E48\u0E43\u0E19\u0E2D\u0E14\u0E35\u0E15\u0E2B\u0E23\
  \u0E37\u0E2D\u0E2D\u0E19\u0E32\u0E04\u0E15\u0E44\u0E2B\u0E21."
title: "\u0E01\u0E32\u0E23\u0E04\u0E33\u0E19\u0E27\u0E13\u0E27\u0E31\u0E19\u0E17\u0E35\
  \u0E48\u0E43\u0E19\u0E2D\u0E19\u0E32\u0E04\u0E15\u0E2B\u0E23\u0E37\u0E2D\u0E2D\u0E14\
  \u0E35\u0E15"
weight: 26
---

## วิธีการ:
Swift ทำให้คณิตศาสตร์ของวันที่เป็นเรื่องง่ายด้วย `Calendar` และ `DateComponents` นี่คือสาระสำคัญ:

```Swift
import Foundation

// วันนี้
let today = Date()

// รับปฏิทินปัจจุบันของผู้ใช้
let currentCalendar = Calendar.current

// เพิ่ม 2 สัปดาห์ให้กับวันนี้
if let twoWeeksLater = currentCalendar.date(byAdding: .weekOfYear, value: 2, to: today) {
    print("สองสัปดาห์จากตอนนี้: \(twoWeeksLater)")
}

// ลบ 30 วันจากวันนี้
if let thirtyDaysBefore = currentCalendar.date(byAdding: .day, value: -30, to: today) {
    print("สามสิบวันที่แล้ว: \(thirtyDaysBefore)")
}
```

ผลลัพธ์อาจเป็นอย่างนี้:
```
สองสัปดาห์จากตอนนี้: 2023-04-14 10:26:47 +0000
สามสิบวันที่แล้ว: 2023-03-15 10:26:47 +0000
```
จำไว้ว่า ผลลัพธ์จริงอาจแตกต่างกันเนื่องจาก `Date()` ให้วันที่และเวลาปัจจุบันกับคุณ

## การดำดิ่งลึก
ก่อน Swift, Objective-C และไวยากรณ์ที่ซับซ้อนของมันเป็นที่นิยม Swift ของ `Date`, `Calendar`, และ `DateComponents` ทำให้การดำเนินการกับวันที่ง่ายขึ้น วัตถุเหล่านี้ให้ความเคารพต่อเขตเวลา จัดการการเปลี่ยนแปลงการประหยัดแสงวัน และรับผิดชอบต่อการตั้งค่าปฏิทินของผู้ใช้ - ปัจจัยเหล่านี้เป็นปัญหาใหญ่ในการจัดการใน Objective-C

ทางเลือกอื่น ๆ รวมถึงไลบรารีของบุคคลที่สามเช่น SwiftDate ซึ่งสามารถมอบความสะดวกสบายและฟังก์ชันการทำงานเพิ่มเติม แต่สำหรับคนส่วนใหญ่ ผลิตภัณฑ์ในตัวของ Swift ทำงานได้ดีเพียงพอ

วันที่มีความซับซ้อน พวกมันไม่ได้เป็นเพียงตัวเลขที่เพิ่มหรือลดลง; พวกเขาเกี่ยวข้องกับปฏิทิน ความเฉพาะเจาะจงของสถานที่ และเขตเวลา กรอบงานของ Apple Foundation จัดการกับความซับซ้อนนี้ได้ ทำให้แน่ใจว่าการคำนวณวันที่ในอนาคตและอดีตของคุณมีความหมายได้ทั่วโลก
