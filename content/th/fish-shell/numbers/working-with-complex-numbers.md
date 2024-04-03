---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 21:53:48.989657-06:00
description: "\u0E08\u0E33\u0E19\u0E27\u0E19\u0E40\u0E0A\u0E34\u0E07\u0E0B\u0E49\u0E2D\
  \u0E19\u0E02\u0E22\u0E32\u0E22\u0E04\u0E27\u0E32\u0E21\u0E04\u0E34\u0E14\u0E02\u0E2D\
  \u0E07\u0E40\u0E2A\u0E49\u0E19\u0E15\u0E31\u0E27\u0E40\u0E25\u0E02\u0E2B\u0E19\u0E36\
  \u0E48\u0E07\u0E21\u0E34\u0E15\u0E34\u0E2D\u0E2D\u0E01\u0E44\u0E1B\u0E22\u0E31\u0E07\
  \u0E23\u0E30\u0E19\u0E32\u0E1A\u0E40\u0E0A\u0E34\u0E07\u0E0B\u0E49\u0E2D\u0E19\u0E2A\
  \u0E2D\u0E07\u0E21\u0E34\u0E15\u0E34 \u0E42\u0E1B\u0E23\u0E41\u0E01\u0E23\u0E21\u0E40\
  \u0E21\u0E2D\u0E23\u0E4C\u0E43\u0E0A\u0E49\u0E1E\u0E27\u0E01\u0E21\u0E31\u0E19\u0E43\
  \u0E19\u0E2A\u0E32\u0E02\u0E32\u0E40\u0E0A\u0E48\u0E19\u0E27\u0E34\u0E28\u0E27\u0E01\
  \u0E23\u0E23\u0E21, \u0E1F\u0E34\u0E2A\u0E34\u0E01\u0E2A\u0E4C\u2026"
lastmod: '2024-03-17T21:57:56.637584-06:00'
model: gpt-4-0125-preview
summary: "\u0E08\u0E33\u0E19\u0E27\u0E19\u0E40\u0E0A\u0E34\u0E07\u0E0B\u0E49\u0E2D\
  \u0E19\u0E02\u0E22\u0E32\u0E22\u0E04\u0E27\u0E32\u0E21\u0E04\u0E34\u0E14\u0E02\u0E2D\
  \u0E07\u0E40\u0E2A\u0E49\u0E19\u0E15\u0E31\u0E27\u0E40\u0E25\u0E02\u0E2B\u0E19\u0E36\
  \u0E48\u0E07\u0E21\u0E34\u0E15\u0E34\u0E2D\u0E2D\u0E01\u0E44\u0E1B\u0E22\u0E31\u0E07\
  \u0E23\u0E30\u0E19\u0E32\u0E1A\u0E40\u0E0A\u0E34\u0E07\u0E0B\u0E49\u0E2D\u0E19\u0E2A\
  \u0E2D\u0E07\u0E21\u0E34\u0E15\u0E34 \u0E42\u0E1B\u0E23\u0E41\u0E01\u0E23\u0E21\u0E40\
  \u0E21\u0E2D\u0E23\u0E4C\u0E43\u0E0A\u0E49\u0E1E\u0E27\u0E01\u0E21\u0E31\u0E19\u0E43\
  \u0E19\u0E2A\u0E32\u0E02\u0E32\u0E40\u0E0A\u0E48\u0E19\u0E27\u0E34\u0E28\u0E27\u0E01\
  \u0E23\u0E23\u0E21, \u0E1F\u0E34\u0E2A\u0E34\u0E01\u0E2A\u0E4C \u0E41\u0E25\u0E30\
  \u0E01\u0E23\u0E32\u0E1F\u0E34\u0E01\u0E2A\u0E33\u0E2B\u0E23\u0E31\u0E1A\u0E01\u0E32\
  \u0E23\u0E04\u0E33\u0E19\u0E27\u0E13\u0E17\u0E35\u0E48\u0E15\u0E49\u0E2D\u0E07\u0E01\
  \u0E32\u0E23\u0E2A\u0E2D\u0E07\u0E2A\u0E48\u0E27\u0E19\u0E1B\u0E23\u0E30\u0E01\u0E2D\
  \u0E1A \u0E40\u0E0A\u0E48\u0E19 \u0E2A\u0E31\u0E0D\u0E0D\u0E32\u0E13\u0E2B\u0E23\
  \u0E37\u0E2D\u0E01\u0E32\u0E23\u0E2B\u0E21\u0E38\u0E19."
title: "\u0E01\u0E32\u0E23\u0E17\u0E33\u0E07\u0E32\u0E19\u0E01\u0E31\u0E1A\u0E15\u0E31\
  \u0E27\u0E40\u0E25\u0E02\u0E0B\u0E31\u0E1A\u0E0B\u0E49\u0E2D\u0E19"
weight: 14
---

## วิธีการ:
ใน Fish, เราจัดการกับจำนวนเชิงซ้อนโดยใช้ `math` กับส่วนจริงและส่วนจินตภาพ นี่คือการเริ่มต้น:

```fish
# บวกจำนวนเชิงซ้อนสองจำนวน (3+4i) และ (5+2i)
set complex_sum (math "3+4i + 5+2i")
echo $complex_sum # แสดงผล: 8+6i

# คูณจำนวนเชิงซ้อนสองจำนวน (1+2i) และ (3+4i)
set complex_prod (math "1+2i * 3+4i")
echo $complex_prod # แสดงผล: -5+10i
```

ถ้าคุณต้องการยกกำลังจำนวนเชิงซ้อนหรือหาแบบสูตรเชิงซ้อน:

```fish
# ยกกำลังสองของ (2+3i)
set complex_square (math "(2+3i)^2")
echo $complex_square # แสดงผล: -5+12i

# ตัวเลขเชิงซ้อนของ (2i)
set complex_exp (math "e^(2i)")
echo $complex_exp # แสดงผล: -0.41615+0.9093i
```

## ลงลึก
การสนับสนุนจำนวนเชิงซ้อนของ Fish Shell เป็นเรื่องใหม่เมื่อเทียบกับการเริ่มต้นในเวอร์ชัน 3.1.0 ก่อนหน้านั้น คนอาจได้ใช้ `bc` หรือเรียกใช้เครื่องมือภายนอกเช่น Python สำหรับคำนวณเชิงซ้อน

ทางเลือกของคำสั่ง math ใน Fish ได้แก่ ห้องสมุดหรือภาษาเลขคณิตพิเศษเช่น MATLAB, Python ด้วย NumPy, หรือแม้แต่ C++ ด้วย Standard Library อย่างไรก็ตาม พวกเขาอาจเกินความจำเป็นสำหรับการคำนวณเชลล์อย่างรวดเร็ว

การสนับสนุนจำนวนเชิงซ้อนของ Fish ถูกฝังไว้ในคำสั่ง `math` ภายในของมัน โดยใช้ประโยชน์จาก libcalc นี้หมายความว่าคุณไม่จำเป็นต้องติดตั้งเครื่องมือเพิ่มเติมสำหรับการดำเนินการพื้นฐาน

อย่างไรก็ตาม Fish ไม่ได้ออกแบบมาสำหรับการคำนวณคณิตศาสตร์ที่หนักหน่วง ความสามารถทางคณิตศาสตร์ของมันเหมาะสำหรับการคำนวณหรือสคริปต์อย่างรวดเร็วที่จำนวนเชิงซ้อนเข้ามามีบทบาท แต่ควรพิจารณาเครื่องมือที่เข้มข้นยิ่งขึ้นสำหรับงานที่ต้องการมากกว่านี้

## ดูเพิ่มเติม
- เอกสารการใช้งาน Fish shell สำหรับคำสั่ง math: https://fishshell.com/docs/current/commands.html#math
- NumPy สำหรับ Python, ทางเลือกยอดนิยม: https://numpy.org/
- การศึกษาลึกลงไปเกี่ยวกับจำนวนเชิงซ้อน: https://betterexplained.com/articles/a-visual-intuitive-guide-to-imaginary-numbers/
