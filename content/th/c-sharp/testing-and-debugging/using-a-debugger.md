---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 21:51:34.619573-06:00
description: "\u0E01\u0E32\u0E23\u0E43\u0E0A\u0E49\u0E07\u0E32\u0E19 debugger \u0E2B\
  \u0E21\u0E32\u0E22\u0E16\u0E36\u0E07\u0E01\u0E32\u0E23\u0E43\u0E0A\u0E49\u0E40\u0E04\
  \u0E23\u0E37\u0E48\u0E2D\u0E07\u0E21\u0E37\u0E2D\u0E1E\u0E34\u0E40\u0E28\u0E29\u0E43\
  \u0E19\u0E01\u0E32\u0E23\u0E17\u0E14\u0E2A\u0E2D\u0E1A\u0E41\u0E25\u0E30\u0E27\u0E34\
  \u0E19\u0E34\u0E08\u0E09\u0E31\u0E22\u0E42\u0E04\u0E49\u0E14 \u0E42\u0E1B\u0E23\u0E41\
  \u0E01\u0E23\u0E21\u0E40\u0E21\u0E2D\u0E23\u0E4C\u0E17\u0E33\u0E40\u0E0A\u0E48\u0E19\
  \u0E19\u0E35\u0E49\u0E40\u0E1E\u0E37\u0E48\u0E2D\u0E08\u0E31\u0E14\u0E01\u0E32\u0E23\
  \u0E01\u0E31\u0E1A\u0E1A\u0E31\u0E4A\u0E01, \u0E40\u0E02\u0E49\u0E32\u0E43\u0E08\
  \u0E01\u0E32\u0E23\u0E44\u0E2B\u0E25\u0E02\u0E2D\u0E07\u0E42\u0E04\u0E49\u0E14,\u2026"
lastmod: '2024-03-17T21:57:56.231130-06:00'
model: gpt-4-0125-preview
summary: "\u0E01\u0E32\u0E23\u0E43\u0E0A\u0E49\u0E07\u0E32\u0E19 debugger \u0E2B\u0E21\
  \u0E32\u0E22\u0E16\u0E36\u0E07\u0E01\u0E32\u0E23\u0E43\u0E0A\u0E49\u0E40\u0E04\u0E23\
  \u0E37\u0E48\u0E2D\u0E07\u0E21\u0E37\u0E2D\u0E1E\u0E34\u0E40\u0E28\u0E29\u0E43\u0E19\
  \u0E01\u0E32\u0E23\u0E17\u0E14\u0E2A\u0E2D\u0E1A\u0E41\u0E25\u0E30\u0E27\u0E34\u0E19\
  \u0E34\u0E08\u0E09\u0E31\u0E22\u0E42\u0E04\u0E49\u0E14 \u0E42\u0E1B\u0E23\u0E41\u0E01\
  \u0E23\u0E21\u0E40\u0E21\u0E2D\u0E23\u0E4C\u0E17\u0E33\u0E40\u0E0A\u0E48\u0E19\u0E19\
  \u0E35\u0E49\u0E40\u0E1E\u0E37\u0E48\u0E2D\u0E08\u0E31\u0E14\u0E01\u0E32\u0E23\u0E01\
  \u0E31\u0E1A\u0E1A\u0E31\u0E4A\u0E01, \u0E40\u0E02\u0E49\u0E32\u0E43\u0E08\u0E01\
  \u0E32\u0E23\u0E44\u0E2B\u0E25\u0E02\u0E2D\u0E07\u0E42\u0E04\u0E49\u0E14,\u2026"
title: "\u0E01\u0E32\u0E23\u0E43\u0E0A\u0E49\u0E07\u0E32\u0E19\u0E15\u0E31\u0E27\u0E14\
  \u0E35\u0E1A\u0E31\u0E4A\u0E01"
---

## วิธีการ:
จินตนาการว่าคุณมีโปรแกรมขนาดเล็กที่ทำงานไม่ถูกต้อง:

```C#
static void Main()
{
    int result = Sum(1, 2);
    Console.WriteLine(result);
}

static int Sum(int a, int b)
{
    return a + a; // อ๊ะ, ควรจะเป็น a + b
}
```

ในการใช้งาน debugger ของ Visual Studio, ตั้งจุดหยุดโดยการคลิกที่ขอบซ้ายข้างๆ `return a + a;` เมื่อคุณรันโปรแกรม (ด้วย F5), การดำเนินการจะหยุดอยู่ที่นั่น เลื่อนเมาส์ไปที่ตัวแปรเพื่อตรวจสอบค่า หรือใช้ Immediate Window เพื่อประเมินนิพจน์ คุณจะเห็นว่า `a` เป็น 1 และ `b` เป็น 2, แต่ `a + a` ไม่ใช่ผลรวมที่เราคาดหวัง เปลี่ยนเป็น `a + b`, ดำเนินการต่อรัน (F5), และวอลา, คอนโซลจะแสดงออกมาเป็น 3

## ลงลึก
ประวัติศาสตร์ของการตรวจสอบบั๊กมีมายาวนานถึงยุค 1940 เมื่อบั๊กจริง (แมลงสาบ) ถูกพบในคอมพิวเตอร์รุ่นเริ่มต้น debugger ในปัจจุบัน, เช่น ตัวหนึ่งใน Visual Studio, มีฟีเจอร์ทรงพลังหลากหลาย, รวมถึงจุดหยุด, การดำเนินการทีละขั้นตอน, หน้าต่างการดูค่าและอื่นๆ

ตัวเลือกที่แทน debugger ของ Visual Studio ได้แก่ตัวเลือกแหล่งเปิดที่รวมถึง GDB สำหรับภาษาแนว C หรือ pdb สำหรับ Python, และ IDE ข้ามแพลตฟอร์มเช่น JetBrains Rider หรือ VS Code ซึ่งเสนอเครื่องมือการดีบักสำหรับ C# และภาษาอื่นๆ

เมื่อคุณลงลึกไปยังการทำงานของ debugger, คุณกำลังมองหาโปรแกรมที่แนบกับกระบวนการของแอปพลิเคชันของคุณ มันตีความรหัสเครื่อง, จัดการสถานะหน่วยความจำ, และควบคุมการดำเนินการของการไหล นี่คือเรื่องค่อนข้างใหญ่ที่สำคัญสำหรับการดีบักที่มีประสิทธิภาพ, ซึ่งเป็นเหตุผลที่โหมดดีบักมักจะทำงานช้ากว่าโหมดปล่อยที่ฮุกเหล่านี้ไม่มีอยู่

## ดูเพิ่มเติม
- [เอกสารการใช้งาน Debugger ของ Visual Studio](https://docs.microsoft.com/en-us/visualstudio/debugger/)
- [กลยุทธ์ในการ Debugging](https://www.codeproject.com/Articles/79508/Effective-Exception-Handling-in-Visual-C)
