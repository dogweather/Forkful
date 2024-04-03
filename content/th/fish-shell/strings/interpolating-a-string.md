---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 21:48:45.558644-06:00
description: "\u0E01\u0E32\u0E23\u0E43\u0E2A\u0E48\u0E15\u0E31\u0E27\u0E41\u0E1B\u0E23\
  \u0E2B\u0E23\u0E37\u0E2D\u0E19\u0E34\u0E1E\u0E08\u0E19\u0E4C\u0E40\u0E02\u0E49\u0E32\
  \u0E44\u0E1B\u0E43\u0E19\u0E2A\u0E15\u0E23\u0E34\u0E07\u0E2B\u0E21\u0E32\u0E22\u0E16\
  \u0E36\u0E07\u0E01\u0E32\u0E23\u0E1C\u0E2A\u0E21\u0E1C\u0E2A\u0E32\u0E19\u0E15\u0E31\
  \u0E27\u0E41\u0E1B\u0E23\u0E2B\u0E23\u0E37\u0E2D\u0E19\u0E34\u0E1E\u0E08\u0E19\u0E4C\
  \u0E40\u0E02\u0E49\u0E32\u0E44\u0E1B\u0E43\u0E19\u0E2A\u0E15\u0E23\u0E34\u0E07\u2026"
lastmod: '2024-03-17T21:57:56.630291-06:00'
model: gpt-4-0125-preview
summary: "\u0E01\u0E32\u0E23\u0E43\u0E2A\u0E48\u0E15\u0E31\u0E27\u0E41\u0E1B\u0E23\
  \u0E2B\u0E23\u0E37\u0E2D\u0E19\u0E34\u0E1E\u0E08\u0E19\u0E4C\u0E40\u0E02\u0E49\u0E32\
  \u0E44\u0E1B\u0E43\u0E19\u0E2A\u0E15\u0E23\u0E34\u0E07\u0E2B\u0E21\u0E32\u0E22\u0E16\
  \u0E36\u0E07\u0E01\u0E32\u0E23\u0E1C\u0E2A\u0E21\u0E1C\u0E2A\u0E32\u0E19\u0E15\u0E31\
  \u0E27\u0E41\u0E1B\u0E23\u0E2B\u0E23\u0E37\u0E2D\u0E19\u0E34\u0E1E\u0E08\u0E19\u0E4C\
  \u0E40\u0E02\u0E49\u0E32\u0E44\u0E1B\u0E43\u0E19\u0E2A\u0E15\u0E23\u0E34\u0E07 \u0E21\
  \u0E31\u0E19\u0E0A\u0E48\u0E27\u0E22\u0E1B\u0E23\u0E30\u0E2B\u0E22\u0E31\u0E14\u0E40\
  \u0E27\u0E25\u0E32\u0E41\u0E25\u0E30\u0E40\u0E1E\u0E34\u0E48\u0E21\u0E04\u0E27\u0E32\
  \u0E21\u0E2A\u0E32\u0E21\u0E32\u0E23\u0E16\u0E43\u0E19\u0E01\u0E32\u0E23\u0E2D\u0E48\
  \u0E32\u0E19\u0E42\u0E14\u0E22\u0E44\u0E21\u0E48\u0E15\u0E49\u0E2D\u0E07\u0E43\u0E0A\
  \u0E49\u0E01\u0E32\u0E23\u0E15\u0E48\u0E2D\u0E2A\u0E15\u0E23\u0E34\u0E07\u0E2D\u0E22\
  \u0E48\u0E32\u0E07\u0E0B\u0E31\u0E1A\u0E0B\u0E49\u0E2D\u0E19."
title: "\u0E01\u0E32\u0E23\u0E41\u0E17\u0E23\u0E01\u0E04\u0E48\u0E32\u0E25\u0E07\u0E43\
  \u0E19\u0E2A\u0E15\u0E23\u0E34\u0E07"
weight: 8
---

## วิธีการ:
ใน Fish, คุณใช้เครื่องหมายคำพูดคู่ "" และวางตัวแปรหรือคำสั่งที่คุณต้องการใส่เข้ากับเครื่องหมายดอลลาร์ `$` ไว้ตรงในสตริง

```fish
set name "world"
echo "Hello, $name!"
```

ผลลัพธ์:
```
สวัสดี, โลก!
```

เพื่อรวมผลลัพธ์ของคำสั่งเข้าไปในสตริง:

```fish
echo "ฉันมี (count (ls)) ไฟล์ในไดเรกทอรีนี้."
```

ผลลัพธ์อาจเป็น:
```
ฉันมี 9 ไฟล์ในไดเรกทอรีนี้.
```

ตัวแปรและคำสั่งจะถูกประเมินและแทรกเข้าไปในตำแหน่งที่คุณวางไว้อย่างเรียบร้อย

## การศึกษาลึกลงไป
ก่อน Fish และ Shell สมัยใหม่อื่น ๆ คุณมักจะใช้การผสมผสานของเครื่องหมายคำพูดและการต่อสตริงที่มากขึ้น หรือพึ่งพาเครื่องมือภายนอก เพื่อให้ได้ตัวแปรเข้าไปในสตริง

ใน bash, ตัวอย่างเช่น, จะดูเป็นอย่างนี้:

```bash
name="world"
echo "Hello, "$name"!"
```

ไม่ดูดีเลยใช่ไหม?

Fish ไม่เพียงแต่ทำให้กระบวนการนี้ง่ายขึ้น แต่ยังจัดการกับข้อผิดพลาดได้ดีกว่า เช่น ถ้าตัวแปรไม่มีอยู่, Fish จะใส่สตริงว่างเข้าไป ลดโอกาสของการเกิดความผิดพลาดจากการใส่ตัวแปรไม่ถูกต้อง

ทางเลือกอื่นสำหรับการใส่ตัวแปรโดยตรง ได้แก่ การใช้คำสั่ง `printf`:

```fish
set animal "narwhal"
printf "The %s is an awesome creature!" $animal
```

ผลลัพธ์:
```
narwhal เป็นสิ่งมีชีวิตที่น่าทึ่ง!
```

ในกรณีนี้, `%s` เป็นตัวยึดที่สำหรับตัวแปรสตริง `$animal` ที่จะถูกแทนที่โดย `printf`.

ในแง่ของการประยุกต์ใช้งาน, เมื่อ Fish ประมวลผลบรรทัดคำสั่ง, มันจะแยกสตริงที่อยู่ในเครื่องหมายคำพูดคู่และเปลี่ยนตัวแปรเป็นค่าของมันในทันที นับเป็นวิธีการที่เรียบร้อยและเลียนแบบการใส่ตัวแปรที่พบในภาษาการเขียนโปรแกรมระดับสูงอย่าง Ruby หรือ PHP

## ดูเพิ่มเติม
สำหรับข้อมูลเพิ่มเติมเกี่ยวกับการจัดการสตริงและการเขียนสคริปต์ใน Fish, ตรวจสอบที่นี่:

- [Fish Shell Documentation: Quotes](https://fishshell.com/docs/current/index.html#quotes)
- [Fish Shell Tutorial](https://fishshell.com/docs/current/tutorial.html)
- [Stack Overflow: How to use variables in a command in Fish](https://stackoverflow.com/questions/2763006/how-to-use-variables-in-a-command-in-fish)
