---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 21:51:59.391173-06:00
description: "\u0E43\u0E19 Elixir, \u0E2D\u0E32\u0E23\u0E4C\u0E40\u0E23\u0E22\u0E4C\
  \u0E41\u0E1A\u0E1A\u0E1C\u0E39\u0E01\u0E04\u0E39\u0E48\u0E0B\u0E36\u0E48\u0E07\u0E40\
  \u0E23\u0E35\u0E22\u0E01\u0E27\u0E48\u0E32 Maps, \u0E40\u0E1B\u0E47\u0E19\u0E04\u0E2D\
  \u0E25\u0E40\u0E25\u0E04\u0E0A\u0E31\u0E19\u0E02\u0E2D\u0E07\u0E04\u0E39\u0E48\u0E04\
  \u0E35\u0E22\u0E4C-\u0E04\u0E48\u0E32\u0E17\u0E35\u0E48\u0E04\u0E35\u0E22\u0E4C\u0E17\
  \u0E35\u0E48\u0E44\u0E21\u0E48\u0E0B\u0E49\u0E33\u0E41\u0E15\u0E48\u0E25\u0E30\u0E15\
  \u0E31\u0E27\u0E0A\u0E35\u0E49\u0E44\u0E1B\u0E17\u0E35\u0E48\u0E04\u0E48\u0E32\u0E2B\
  \u0E19\u0E36\u0E48\u0E07 \u0E46\u2026"
lastmod: '2024-03-17T21:57:55.843190-06:00'
model: gpt-4-0125-preview
summary: "\u0E43\u0E19 Elixir, \u0E2D\u0E32\u0E23\u0E4C\u0E40\u0E23\u0E22\u0E4C\u0E41\
  \u0E1A\u0E1A\u0E1C\u0E39\u0E01\u0E04\u0E39\u0E48\u0E0B\u0E36\u0E48\u0E07\u0E40\u0E23\
  \u0E35\u0E22\u0E01\u0E27\u0E48\u0E32 Maps, \u0E40\u0E1B\u0E47\u0E19\u0E04\u0E2D\u0E25\
  \u0E40\u0E25\u0E04\u0E0A\u0E31\u0E19\u0E02\u0E2D\u0E07\u0E04\u0E39\u0E48\u0E04\u0E35\
  \u0E22\u0E4C-\u0E04\u0E48\u0E32\u0E17\u0E35\u0E48\u0E04\u0E35\u0E22\u0E4C\u0E17\u0E35\
  \u0E48\u0E44\u0E21\u0E48\u0E0B\u0E49\u0E33\u0E41\u0E15\u0E48\u0E25\u0E30\u0E15\u0E31\
  \u0E27\u0E0A\u0E35\u0E49\u0E44\u0E1B\u0E17\u0E35\u0E48\u0E04\u0E48\u0E32\u0E2B\u0E19\
  \u0E36\u0E48\u0E07 \u0E46 \u0E1E\u0E27\u0E01\u0E21\u0E31\u0E19\u0E21\u0E35\u0E1B\
  \u0E23\u0E30\u0E42\u0E22\u0E0A\u0E19\u0E4C\u0E21\u0E32\u0E01\u0E2A\u0E33\u0E2B\u0E23\
  \u0E31\u0E1A\u0E01\u0E32\u0E23\u0E40\u0E01\u0E47\u0E1A\u0E41\u0E25\u0E30\u0E40\u0E23\
  \u0E35\u0E22\u0E01\u0E02\u0E49\u0E2D\u0E21\u0E39\u0E25\u0E44\u0E14\u0E49\u0E2D\u0E22\
  \u0E48\u0E32\u0E07\u0E23\u0E27\u0E14\u0E40\u0E23\u0E47\u0E27, \u0E17\u0E33\u0E43\
  \u0E2B\u0E49\u0E42\u0E04\u0E49\u0E14\u0E02\u0E2D\u0E07\u0E04\u0E38\u0E13\u0E2A\u0E30\
  \u0E2D\u0E32\u0E14\u0E41\u0E25\u0E30\u0E0A\u0E35\u0E27\u0E34\u0E15\u0E02\u0E2D\u0E07\
  \u0E04\u0E38\u0E13\u0E07\u0E48\u0E32\u0E22\u0E02\u0E36\u0E49\u0E19."
title: "\u0E01\u0E32\u0E23\u0E43\u0E0A\u0E49\u0E41\u0E2D\u0E40\u0E23\u0E22\u0E4C\u0E2A\
  \u0E21\u0E32\u0E0A\u0E34\u0E01"
weight: 15
---

## วิธีการ:
การสร้าง Map นั้นทำได้ง่ายโดยใช้ syntax `%{}` เช่น:

```elixir
my_map = %{"name" => "Alex", "age" => 32}
IO.inspect(my_map)
```

การเข้าถึงค่าทำได้โดยการใช้คีย์:

```elixir
IO.puts my_map["name"]
```
ผลลัพธ์: `Alex`

เพื่อเพิ่มหรืออัปเดตค่า, คุณสามารถใช้ฟังก์ชัน `Map.put/3`:

```elixir
updated_map = Map.put(my_map, "location", "NY")
IO.inspect(updated_map)
```
ผลลัพธ์: `%{"age" => 32, "location" => "NY", "name" => "Alex"}`

การลบคีย์ก็ง่ายด้วย `Map.delete/2`:

```elixir
trimmed_map = Map.delete(updated_map, "age")
IO.inspect(trimmed_map)
```
ผลลัพธ์: `%{"location" => "NY", "name" => "Alex"}`

## ล้ำลึก
Maps ใน Elixir เป็นการพัฒนาต่อจากประเภทการเก็บข้อมูลคีย์-ค่าแบบเก่า, เช่น Hashes ใน Ruby หรือ Dictionaries ใน Python พวกมันอนุญาตให้ทำการค้นหาและแทรกได้มากขึ้นด้วยประสิทธิภาพ, ทำให้เป็นตัวเลือกสำหรับการเขียนโปรแกรม Elixir สมัยใหม่ ควรทราบว่าก่อนมี Maps, Elixir ใช้โมดูล HashDict และ Dict ซึ่งตอนนี้ถูกยกเลิกแล้ว

อย่างไรก็ตาม, สำหรับสถานการณ์ที่ต้องการข้อมูลเรียงลำดับ, คุณอาจดูที่ keyword lists ใน Elixir นี่คือรายการของทูเพิล, มีประสิทธิภาพสำหรับการรวบรวมขนาดเล็กแต่ไม่จำกัดประสิทธิภาพสำหรับชุดข้อมูลขนาดใหญ่เหมือนกับ Maps

จำไว้ว่า Maps เก็บคีย์ไว้ในโครงสร้าง "แบน", ทำให้การเข้าถึงค่าที่ซ้อนกันโดยตรงบางครั้งอาจจะยาก สำหรับการซ้อนข้อมูลลึก, คุณอาจพิจารณาการเข้าถึงโครงสร้างผ่านฟังก์ชัน `get_in`, `put_in`, `update_in`, และ `get_and_update_in`, ซึ่งอนุญาตให้มีวิธีการที่ยืดหยุ่นกว่าในการจัดการข้อมูลที่ซับซ้อน

โดยสรุป, ในขณะที่ Maps เป็นตัวเลือกหลักสำหรับความต้องการอาร์เรย์แบบผูกคู่ใน Elixir, ภาษานี้มีความหลากหลายของโครงสร้างข้อมูลสำหรับทุกสถานการณ์, กระตุ้นให้คุณเลือกเครื่องมือที่เหมาะสมที่สุดสำหรับงานนั้น ๆ
