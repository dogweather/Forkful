---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 21:46:14.520938-06:00
description: "\u0E43\u0E19 Ruby, \u0E01\u0E32\u0E23\u0E2A\u0E23\u0E49\u0E32\u0E07\u0E44\
  \u0E1F\u0E25\u0E4C\u0E0A\u0E31\u0E48\u0E27\u0E04\u0E23\u0E32\u0E27\u0E0A\u0E48\u0E27\
  \u0E22\u0E43\u0E2B\u0E49\u0E02\u0E49\u0E2D\u0E21\u0E39\u0E25\u0E17\u0E35\u0E48\u0E25\
  \u0E30\u0E40\u0E2D\u0E35\u0E22\u0E14\u0E2D\u0E48\u0E2D\u0E19\u0E1B\u0E25\u0E2D\u0E14\
  \u0E20\u0E31\u0E22\u0E41\u0E25\u0E30\u0E08\u0E31\u0E14\u0E01\u0E32\u0E23\u0E04\u0E27\
  \u0E32\u0E21\u0E15\u0E49\u0E2D\u0E07\u0E01\u0E32\u0E23\u0E40\u0E01\u0E47\u0E1A\u0E02\
  \u0E49\u0E2D\u0E21\u0E39\u0E25\u0E0A\u0E31\u0E48\u0E27\u0E04\u0E23\u0E31\u0E49\u0E07\
  \u0E0A\u0E31\u0E48\u0E27\u0E04\u0E23\u0E32\u0E27\u0E44\u0E14\u0E49\u2026"
lastmod: '2024-03-17T21:57:56.747840-06:00'
model: gpt-4-0125-preview
summary: "\u0E43\u0E19 Ruby, \u0E01\u0E32\u0E23\u0E2A\u0E23\u0E49\u0E32\u0E07\u0E44\
  \u0E1F\u0E25\u0E4C\u0E0A\u0E31\u0E48\u0E27\u0E04\u0E23\u0E32\u0E27\u0E0A\u0E48\u0E27\
  \u0E22\u0E43\u0E2B\u0E49\u0E02\u0E49\u0E2D\u0E21\u0E39\u0E25\u0E17\u0E35\u0E48\u0E25\
  \u0E30\u0E40\u0E2D\u0E35\u0E22\u0E14\u0E2D\u0E48\u0E2D\u0E19\u0E1B\u0E25\u0E2D\u0E14\
  \u0E20\u0E31\u0E22\u0E41\u0E25\u0E30\u0E08\u0E31\u0E14\u0E01\u0E32\u0E23\u0E04\u0E27\
  \u0E32\u0E21\u0E15\u0E49\u0E2D\u0E07\u0E01\u0E32\u0E23\u0E40\u0E01\u0E47\u0E1A\u0E02\
  \u0E49\u0E2D\u0E21\u0E39\u0E25\u0E0A\u0E31\u0E48\u0E27\u0E04\u0E23\u0E31\u0E49\u0E07\
  \u0E0A\u0E31\u0E48\u0E27\u0E04\u0E23\u0E32\u0E27\u0E44\u0E14\u0E49 \u0E42\u0E1B\u0E23\
  \u0E41\u0E01\u0E23\u0E21\u0E40\u0E21\u0E2D\u0E23\u0E4C\u0E43\u0E0A\u0E49\u0E21\u0E31\
  \u0E19\u0E40\u0E1E\u0E37\u0E48\u0E2D\u0E01\u0E32\u0E23\u0E08\u0E31\u0E14\u0E01\u0E32\
  \u0E23\u0E44\u0E1F\u0E25\u0E4C\u0E23\u0E30\u0E22\u0E30\u0E2A\u0E31\u0E49\u0E19\u0E17\
  \u0E35\u0E48\u0E1B\u0E25\u0E2D\u0E14\u0E20\u0E31\u0E22\u0E42\u0E14\u0E22\u0E44\u0E21\
  \u0E48\u0E17\u0E33\u0E43\u0E2B\u0E49\u0E44\u0E1F\u0E25\u0E4C\u0E23\u0E30\u0E1A\u0E1A\
  \u0E2B\u0E25\u0E31\u0E01\u0E40\u0E01\u0E30\u0E01\u0E30."
title: "\u0E2A\u0E23\u0E49\u0E32\u0E07\u0E44\u0E1F\u0E25\u0E4C\u0E0A\u0E31\u0E48\u0E27\
  \u0E04\u0E23\u0E32\u0E27"
weight: 21
---

## วิธีการ:
ไลบรารีมาตรฐานของ Ruby มี `Tempfile` สำหรับการสร้างไฟล์ชั่วคราว ลองดูกันเลย:

```Ruby
require 'tempfile'

Tempfile.create('my_temp') do |tempfile|
  tempfile.write('Temporary content')
  puts "Temporary file is located at: #{tempfile.path}"
end
# หลังจากบล็อก, ไฟล์จะถูกลบโดยอัตโนมัติ
```

เมื่อคุณรันสคริปต์นี้, คุณจะเห็น:

```
Temporary file is located at: /tmp/my_temp20180418-56789-1234567
```

ไฟล์นี้จะไม่อยู่นานเกินควร ทันทีที่บล็อกสิ้นสุด, Ruby จะทำความสะอาดให้คุณ

## ลงลึก
คลาส `Tempfile` มีมาตั้งแต่ Ruby 1.8, ฝึกฝนและขัดเกลามาเป็นเวลานาน ใต้ฮู้ด, มันใช้เส้นทางไฟล์ชั่วคราวของระบบของคุณ, ซึ่งระบบปฏิบัติการของคุณเสนอ

มีทางเลือกอื่นไหม? แน่นอน, คุณอาจ manually สร้างและติดตามไฟล์ชั่วคราว, แต่ทำไมต้องคิดใหม่ทั้งที่มีวิธีดีๆอยู่แล้ว? `Tempfile` ให้คุณฟิลเนมที่สุ่มและไม่ซ้ำใคร, ลดความเสี่ยงของการชนกัน

สำหรับคนที่ต้องการการควบคุมมากขึ้น, วิธีการ `Tempfile.new` รับพารามิเตอร์สำหรับการปรับเปลี่ยนชื่อไฟล์และตำแหน่ง แต่จำไว้ว่า, ด้วยอำนาจที่ยิ่งใหญ่มาพร้อมกับความรับผิดชอบที่ยิ่งใหญ่ - คุณจะต้องลบไฟล์เหล่านี้ด้วยตัวเอง

ขอบเขตจริงของการใช้ `Tempfile` อยู่ในความเป็นเธรด-เซฟและการถูกเก็บรวบรวมโดยการ์เบจคอลเลกชัน มันปิดล็อกไฟล์และรับรองว่าข้อมูลที่ละเอียดอ่อนนั้นจะไม่คงอยู่นานเกินควร ไฟล์ชั่วคราวทำงานคล้ายคลึงกับอ็อบเจคไฟล์มาตรฐาน, ดังนั้นคุณสามารถอ่านจาก, เขียนเข้าไป, และจัดการมันโดยใช้การดำเนินการกับไฟล์โดยปกติ

## ดูเพิ่มเติม
- Ruby API Dock สำหรับตัวอย่างการใช้งาน Tempfile เพิ่มเติม: [API Dock Tempfile](https://apidock.com/ruby/Tempfile)
- คู่มือการจัดการไฟล์ใน Ruby สำหรับเพิ่มเติมเกี่ยวกับการจัดการไฟล์: [File I/O](https://www.rubyguides.com/2015/05/working-with-files-ruby/)
