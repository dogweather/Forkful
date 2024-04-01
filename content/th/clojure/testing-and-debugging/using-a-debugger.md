---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 21:51:35.172794-06:00
description: "\u0E01\u0E32\u0E23\u0E43\u0E0A\u0E49\u0E40\u0E14\u0E1A\u0E31\u0E01\u0E40\
  \u0E01\u0E2D\u0E23\u0E4C\u0E2B\u0E21\u0E32\u0E22\u0E16\u0E36\u0E07\u0E01\u0E32\u0E23\
  \u0E17\u0E35\u0E48\u0E04\u0E38\u0E13\u0E15\u0E34\u0E14\u0E15\u0E31\u0E49\u0E07\u0E40\
  \u0E25\u0E19\u0E2A\u0E4C\u0E02\u0E22\u0E32\u0E22\u0E40\u0E1E\u0E37\u0E48\u0E2D\u0E15\
  \u0E23\u0E27\u0E08\u0E2A\u0E2D\u0E1A\u0E42\u0E04\u0E49\u0E14\u0E02\u0E2D\u0E07\u0E04\
  \u0E38\u0E13\u0E2D\u0E22\u0E48\u0E32\u0E07\u0E43\u0E01\u0E25\u0E49\u0E0A\u0E34\u0E14\
  \ \u0E42\u0E1B\u0E23\u0E41\u0E01\u0E23\u0E21\u0E40\u0E21\u0E2D\u0E23\u0E4C\u0E17\
  \u0E33\u0E40\u0E0A\u0E48\u0E19\u0E19\u0E35\u0E49\u0E40\u0E1E\u0E37\u0E48\u0E2D\u0E01\
  \u0E33\u0E08\u0E31\u0E14\u0E1A\u0E31\u0E4A\u0E01\u2026"
lastmod: '2024-03-17T21:57:55.812559-06:00'
model: gpt-4-0125-preview
summary: "\u0E01\u0E32\u0E23\u0E43\u0E0A\u0E49\u0E40\u0E14\u0E1A\u0E31\u0E01\u0E40\
  \u0E01\u0E2D\u0E23\u0E4C\u0E2B\u0E21\u0E32\u0E22\u0E16\u0E36\u0E07\u0E01\u0E32\u0E23\
  \u0E17\u0E35\u0E48\u0E04\u0E38\u0E13\u0E15\u0E34\u0E14\u0E15\u0E31\u0E49\u0E07\u0E40\
  \u0E25\u0E19\u0E2A\u0E4C\u0E02\u0E22\u0E32\u0E22\u0E40\u0E1E\u0E37\u0E48\u0E2D\u0E15\
  \u0E23\u0E27\u0E08\u0E2A\u0E2D\u0E1A\u0E42\u0E04\u0E49\u0E14\u0E02\u0E2D\u0E07\u0E04\
  \u0E38\u0E13\u0E2D\u0E22\u0E48\u0E32\u0E07\u0E43\u0E01\u0E25\u0E49\u0E0A\u0E34\u0E14\
  \ \u0E42\u0E1B\u0E23\u0E41\u0E01\u0E23\u0E21\u0E40\u0E21\u0E2D\u0E23\u0E4C\u0E17\
  \u0E33\u0E40\u0E0A\u0E48\u0E19\u0E19\u0E35\u0E49\u0E40\u0E1E\u0E37\u0E48\u0E2D\u0E01\
  \u0E33\u0E08\u0E31\u0E14\u0E1A\u0E31\u0E4A\u0E01\u2026"
title: "\u0E01\u0E32\u0E23\u0E43\u0E0A\u0E49\u0E07\u0E32\u0E19\u0E15\u0E31\u0E27\u0E14\
  \u0E35\u0E1A\u0E31\u0E4A\u0E01"
---

## วิธีการ:
Clojure ทำงานบน Java Virtual Machine (JVM) ดังนั้นการดีบักจึงเกิดขึ้นโดยใช้เครื่องมือของ Java มากมาย หนึ่งในเครื่องมือเหล่านั้นคือ `CIDER` ซึ่งเป็นแพ็คเกจทรงพลังสำหรับการพัฒนา Clojure ใน Emacs ซึ่งมีความสามารถการดีบักที่เป็นเลิศ ไปดูกัน:

```clojure
;; ก่อนอื่น เข้าสู่โครงการ Clojure ภายใน Emacs โดยใช้ CIDER
M-x cider-jack-in

;; ตั้งจุดหยุด (breakpoint)
;; ไปยังบรรทัดในโค้ด Clojure ที่คุณต้องการตรวจสอบและ
;; กด "C-c M-b" หรือ ปฏิบัติการ:
M-x cider-debug-defun-at-point

;; เมื่อโค้ดทำงาน คุณจะเจอกับจุดหยุด CIDER จะแสดงตัวเลือกด้วยคำสั่ง:
;; 1. n เพื่อไปยังขั้นตอนต่อไปที่เหมาะสมในการประมวลผล,
;; 2. c เพื่อดำเนินการต่อจนถึงจุดหยุดถัดไป,
;; 3. q เพื่อออกจากการดีบัก

;; ตรวจสอบตัวแปร locals ที่จุดหยุด
;; ขณะอยู่ที่จุดหยุด พิมพ์:
locals

;; คุณจะเห็นรายการของตัวแปร locals และค่าของพวกเขาที่แสดงอยู่ใน minibuffer
```
ตัวอย่างผลลัพธ์อาจดูเช่น:
```clojure
{:x 10, :y 20, :result 200}
```

## การศึกษาลึก
เดบักเกอร์เป็นเครื่องมือที่เก่าแก่เป็นภูเขาในแง่ของการคำนวณ คำว่า "บั๊ก" ถูกคิดขึ้นมาในยุคแรกๆ ของการคำนวณเมื่อแมลงจริงๆ ทำให้เครื่องหยุดทำงานด้วยการลัดวงจร

ในขณะที่ `CIDER` เป็นเรื่องที่ดีสำหรับผู้ที่ชื่นชอบ Emacs ยังมีทางเลือกอื่นๆ สำหรับการดีบักของ Clojure ตัวอย่างเช่น การใช้ IntelliJ กับปลั๊กอิน Cursive สามารถให้ประสบการณ์ดีบักที่ขับเคลื่อนด้วย GUI มากขึ้น นอกจากนี้คุณยังสามารถใช้ Leiningen ในตัวหรือ tools.deps เพื่อควบคุมกระบวนการดีบัก

ใต้ฝาประทุน เดบักเกอร์เหล่านี้มักจะจัดการกับ bytecode ทำการประเมินในเซสชัน nREPL ที่กำหนดและเสนอการตรวจสอบ stack trace พวกเขาใช้ประโยชน์จากความสามารถของ JVM ที่อยู่ด้านล่าง โดยใช้คุณสมบัติการดีบักของ Java

## ดูเพิ่มเติม
- [เอกสารการดีบักของ CIDER](https://docs.cider.mx/cider/debugging/debugger.html)
- [เดบักเกอร์ Cursive](https://cursive-ide.com/userguide/debugging.html)
- [Leiningen สำหรับ Automation และ Debugging](https://leiningen.org/)
- [tools.deps.alpha สำหรับการควบคุมมากขึ้น](https://github.com/clojure/tools.deps.alpha)
