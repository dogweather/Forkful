---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 21:52:08.171815-06:00
description: "Associative arrays \u0E43\u0E19 Lua \u0E40\u0E2B\u0E21\u0E37\u0E2D\u0E19\
  \u0E01\u0E32\u0E23\u0E17\u0E31\u0E01\u0E17\u0E32\u0E22\u0E25\u0E31\u0E1A\u0E2A\u0E33\
  \u0E2B\u0E23\u0E31\u0E1A\u0E02\u0E49\u0E2D\u0E21\u0E39\u0E25\u2014\u0E41\u0E17\u0E19\
  \u0E17\u0E35\u0E48\u0E08\u0E30\u0E40\u0E1B\u0E47\u0E19\u0E40\u0E1E\u0E35\u0E22\u0E07\
  \u0E15\u0E31\u0E27\u0E40\u0E25\u0E02\u0E17\u0E35\u0E48\u0E40\u0E23\u0E35\u0E22\u0E07\
  \u0E01\u0E31\u0E19\u0E2D\u0E22\u0E48\u0E32\u0E07\u0E40\u0E04\u0E23\u0E48\u0E07\u0E04\
  \u0E23\u0E31\u0E14\u0E15\u0E32\u0E21\u0E14\u0E31\u0E0A\u0E19\u0E35, \u0E04\u0E38\
  \u0E13\u0E2A\u0E32\u0E21\u0E32\u0E23\u0E16\u0E01\u0E33\u0E2B\u0E19\u0E14\u0E04\u0E35\
  \u0E22\u0E4C\u0E44\u0E14\u0E49\u0E15\u0E32\u0E21\u0E17\u0E35\u0E48\u0E04\u0E38\u0E13\
  \u0E15\u0E49\u0E2D\u0E07\u0E01\u0E32\u0E23,\u2026"
lastmod: '2024-03-17T21:57:56.347317-06:00'
model: gpt-4-0125-preview
summary: "Associative arrays \u0E43\u0E19 Lua \u0E40\u0E2B\u0E21\u0E37\u0E2D\u0E19\
  \u0E01\u0E32\u0E23\u0E17\u0E31\u0E01\u0E17\u0E32\u0E22\u0E25\u0E31\u0E1A\u0E2A\u0E33\
  \u0E2B\u0E23\u0E31\u0E1A\u0E02\u0E49\u0E2D\u0E21\u0E39\u0E25\u2014\u0E41\u0E17\u0E19\
  \u0E17\u0E35\u0E48\u0E08\u0E30\u0E40\u0E1B\u0E47\u0E19\u0E40\u0E1E\u0E35\u0E22\u0E07\
  \u0E15\u0E31\u0E27\u0E40\u0E25\u0E02\u0E17\u0E35\u0E48\u0E40\u0E23\u0E35\u0E22\u0E07\
  \u0E01\u0E31\u0E19\u0E2D\u0E22\u0E48\u0E32\u0E07\u0E40\u0E04\u0E23\u0E48\u0E07\u0E04\
  \u0E23\u0E31\u0E14\u0E15\u0E32\u0E21\u0E14\u0E31\u0E0A\u0E19\u0E35, \u0E04\u0E38\
  \u0E13\u0E2A\u0E32\u0E21\u0E32\u0E23\u0E16\u0E01\u0E33\u0E2B\u0E19\u0E14\u0E04\u0E35\
  \u0E22\u0E4C\u0E44\u0E14\u0E49\u0E15\u0E32\u0E21\u0E17\u0E35\u0E48\u0E04\u0E38\u0E13\
  \u0E15\u0E49\u0E2D\u0E07\u0E01\u0E32\u0E23, \u0E17\u0E33\u0E43\u0E2B\u0E49\u0E01\
  \u0E32\u0E23\u0E40\u0E23\u0E35\u0E22\u0E01\u0E14\u0E39\u0E02\u0E49\u0E2D\u0E21\u0E39\
  \u0E25\u0E40\u0E1B\u0E47\u0E19\u0E40\u0E23\u0E37\u0E48\u0E2D\u0E07\u0E07\u0E48\u0E32\
  \u0E22."
title: "\u0E01\u0E32\u0E23\u0E43\u0E0A\u0E49\u0E41\u0E2D\u0E40\u0E23\u0E22\u0E4C\u0E2A\
  \u0E21\u0E32\u0E0A\u0E34\u0E01"
weight: 15
---

## วิธีการ:
ใน Lua, การสร้าง associative array (หรือตาราง, ในภาษา Lua) เป็นเรื่องง่าย. คุณทิ้งดัชนีตัวเลขปกติและเลือกใช้คีย์ของคุณเอง. ลองดูสิ:

```Lua
-- สร้าง associative array
userInfo = {
  name = "Jamie",
  occupation = "Adventurer",
  level = 42
}

-- เข้าถึงองค์ประกอบ
print(userInfo["name"]) -- พิมพ์ Jamie
print(userInfo.occupation) -- พิมพ์ Adventurer

-- เพิ่มคู่คีย์-ค่าใหม่
userInfo["hobby"] = "Coding"
userInfo.favLang = "Lua"

-- วนซ้ำผ่าน associative array
for key, value in pairs(userInfo) do
  print(key .. ": " .. value)
end
```

ผลลัพธ์:
```
Jamie
Adventurer
name: Jamie
occupation: Adventurer
level: 42
hobby: Coding
favLang: Lua
```

ส่วนที่เจ๋ง? คุณโต้ตอบกับข้อมูลโดยใช้คีย์ที่มีความหมายสำหรับคุณ, ทำให้โค้ดอ่านง่ายและบำรุงรักษาได้มากขึ้น.

## ศึกษาเพิ่มเติม
เมื่อ Lua เข้าสู่วงการ, มันได้นำเสนอตารางเป็นโครงสร้างข้อมูลอเนกประสงค์, ปฏิวัติวิธีการจัดการข้อมูลของนักพัฒนา. ไม่เหมือนในบางภาษาที่ associative arrays และ arrays เป็นสิ่งที่แตกต่างกัน, ตารางของ Lua ให้บริการทั้งสอง, ทำให้โครงสร้างข้อมูลเรียบง่ายขึ้น.

สิ่งที่ทำให้ตาราง Lua มีประสิทธิภาพเป็นพิเศษคือความยืดหยุ่นของมัน. อย่างไรก็ตาม, ความยืดหยุ่นนี้มาพร้อมกับความเป็นไปได้ของผลกระทบต่อประสิทธิภาพ, โดยเฉพาะกับชุดข้อมูลขนาดใหญ่ที่โครงสร้างข้อมูลที่เชี่ยวชาญมากขึ้นอาจเหมาะสมกว่าเพื่อประสิทธิภาพ.

ในขณะที่ Lua ไม่รองรับโครงสร้างข้อมูลแบบดั้งเดิมอย่างเช่น linked lists หรือ hash maps ออกมาโดยตรง, ความสามารถปรับเปลี่ยนของโครงสร้างตารางหมายความว่าคุณสามารถนำมาใช้งานเหล่านี้ได้โดยใช้ตารางหากคุณต้องการ. จำไว้ว่า: ด้วยพลังที่ยิ่งใหญ่มาพร้อมกับความรับผิดชอบที่ยิ่งใหญ่. ใช้ความยืดหยุ่นอย่างมีปัญญาเพื่อรักษาประสิทธิภาพและความสามารถในการอ่านของโค้ดของคุณ.
