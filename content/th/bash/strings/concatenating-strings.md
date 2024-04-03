---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 21:45:28.573527-06:00
description: "\u0E01\u0E32\u0E23\u0E15\u0E48\u0E2D\u0E2A\u0E15\u0E23\u0E34\u0E07\u0E43\
  \u0E19 Bash \u0E2B\u0E21\u0E32\u0E22\u0E16\u0E36\u0E07\u0E01\u0E32\u0E23\u0E19\u0E33\
  \u0E2A\u0E2D\u0E07\u0E2A\u0E48\u0E27\u0E19\u0E02\u0E2D\u0E07\u0E02\u0E49\u0E2D\u0E04\
  \u0E27\u0E32\u0E21\u0E2B\u0E23\u0E37\u0E2D\u0E21\u0E32\u0E01\u0E01\u0E27\u0E48\u0E32\
  \u0E21\u0E32\u0E23\u0E27\u0E21\u0E01\u0E31\u0E19 \u0E40\u0E2B\u0E25\u0E48\u0E32\u0E42\
  \u0E1B\u0E23\u0E41\u0E01\u0E23\u0E21\u0E40\u0E21\u0E2D\u0E23\u0E4C\u0E17\u0E33\u0E40\
  \u0E0A\u0E48\u0E19\u0E19\u0E35\u0E49\u0E40\u0E1E\u0E37\u0E48\u0E2D\u0E2A\u0E23\u0E49\
  \u0E32\u0E07\u0E04\u0E33\u0E2A\u0E31\u0E48\u0E07, \u0E2A\u0E23\u0E49\u0E32\u0E07\
  \u0E40\u0E2A\u0E49\u0E19\u0E17\u0E32\u0E07\u0E44\u0E1F\u0E25\u0E4C,\u2026"
lastmod: '2024-03-17T21:57:56.387589-06:00'
model: gpt-4-0125-preview
summary: "\u0E01\u0E32\u0E23\u0E15\u0E48\u0E2D\u0E2A\u0E15\u0E23\u0E34\u0E07\u0E43\
  \u0E19 Bash \u0E2B\u0E21\u0E32\u0E22\u0E16\u0E36\u0E07\u0E01\u0E32\u0E23\u0E19\u0E33\
  \u0E2A\u0E2D\u0E07\u0E2A\u0E48\u0E27\u0E19\u0E02\u0E2D\u0E07\u0E02\u0E49\u0E2D\u0E04\
  \u0E27\u0E32\u0E21\u0E2B\u0E23\u0E37\u0E2D\u0E21\u0E32\u0E01\u0E01\u0E27\u0E48\u0E32\
  \u0E21\u0E32\u0E23\u0E27\u0E21\u0E01\u0E31\u0E19 \u0E40\u0E2B\u0E25\u0E48\u0E32\u0E42\
  \u0E1B\u0E23\u0E41\u0E01\u0E23\u0E21\u0E40\u0E21\u0E2D\u0E23\u0E4C\u0E17\u0E33\u0E40\
  \u0E0A\u0E48\u0E19\u0E19\u0E35\u0E49\u0E40\u0E1E\u0E37\u0E48\u0E2D\u0E2A\u0E23\u0E49\
  \u0E32\u0E07\u0E04\u0E33\u0E2A\u0E31\u0E48\u0E07, \u0E2A\u0E23\u0E49\u0E32\u0E07\
  \u0E40\u0E2A\u0E49\u0E19\u0E17\u0E32\u0E07\u0E44\u0E1F\u0E25\u0E4C, \u0E2B\u0E23\
  \u0E37\u0E2D\u0E41\u0E04\u0E48\u0E08\u0E31\u0E14\u0E23\u0E39\u0E1B\u0E41\u0E1A\u0E1A\
  \u0E02\u0E49\u0E2D\u0E04\u0E27\u0E32\u0E21\u0E17\u0E35\u0E48\u0E41\u0E2A\u0E14\u0E07\
  \u0E1C\u0E25."
title: "\u0E01\u0E32\u0E23\u0E15\u0E48\u0E2D\u0E2A\u0E15\u0E23\u0E34\u0E07"
weight: 3
---

## วิธีการ:
นี่คือทางลัดในการกอดสตริงของคุณจนแนบแน่นใน Bash:

```Bash
# การต่อสตริงโดยการวางสตริงข้างๆ กัน
greeting="Hello, "
name="world!"
welcome=$greeting$name
echo $welcome  # แสดงผล: Hello, world!

# การใช้วงเล็บปีกกาเพื่อความชัดเจน
version="version"
number=1
full_version=${version}_${number}
echo $full_version  # แสดงผล: version_1

# การต่อสตริงด้วยตัวแปรและตัวอักขระตายตัว
timestamp=$(date +%Y%m%d)  # ได้วันที่ปัจจุบันในรูปแบบ YYYYMMDD
filename="backup_${timestamp}.tar.gz"
echo $filename  # แสดงผล: backup_20230315.tar.gz
```

## ลึกรายละเอียด
ในยุคก่อนที่ GUI ครองโลก, เส้นทางคำสั่งและสคริปต์คือกษัตริย์แห่งการโต้ตอบกับคอมพิวเตอร์ การต่อสตริงเป็นสิ่งที่สำคัญเสมอเนื่องจากมันช่วยให้สามารถจัดการคำสั่งและไฟล์ได้อย่างไดนามิก

ทางเลือกทางประวัติศาสตร์คือคำสั่ง `expr`, ซึ่งตอนนี้รู้สึกเหมือนเป็นโบราณ:

```Bash
older_way=$(expr $greeting $name)
```

แต่ Bash ก็บอกว่า, "ใครต้องการความยุ่งยากนั้น?" และทำให้มันเป็นธรรมชาติ อย่างไร? ดี, Bash รักษาสตริงเหมือนเพื่อนตัวแสบที่พวกเขาคือ: วางข้างๆ กันและพวกมันจะกอดกันเข้าด้วยกันเป็นสตริงยาว

ภายใต้ฝา, Bash จัดการสิ่งนี้โดยไม่ต้องใช้ฟังก์ชันพิเศษหรือไวยากรณ์สำหรับการต่อสตริง คำหรือตัวแปรเพียงแค่ไหลรวมกัน อย่างไรก็ตาม, หากตัวแปรของคุณอาจเริ่มต้นด้วยตัวเลขหรือเครื่องหมายขีดล่าง, คุณมักจะห่อมันด้วยวงเล็บปีกกาเพื่อป้องกันความสับสนกับชื่อตัวแปรอื่นๆ

อย่างไรก็ตามมีข้อจำกัด: ช่องว่างมีความสำคัญ หากคุณไม่ระมัดระวัง, คุณอาจจบลงด้วยช่องว่างที่ไม่ตั้งใจหรือผลลัพธ์ที่ติดกันรกๆ

ทางเลือกปัจจุบันคือการใช้ฟังก์ชัน `printf`, ซึ่งให้ความควบคุมเกี่ยวกับการจัดรูปแบบมากขึ้น:

```Bash
printf -v full_greeting "%s%s" "$greeting" "$name"
echo $full_greeting  # แสดงผล: Hello, world!
```

## ดูเพิ่มเติม
- [คู่มือ GNU Bash](https://www.gnu.org/software/bash/manual/) สำหรับความรู้พื้นฐานของทุกสิ่งใน Bash
- [คู่มือการเขียนสคริปต์ Bash ขั้นสูง](https://tldp.org/LDP/abs/html/) สำหรับการฝึกการเขียนสคริปต์และตัวอย่างเพิ่มเติม
