---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 21:46:57.256054-06:00
description: "\u0E01\u0E32\u0E23\u0E14\u0E32\u0E27\u0E19\u0E4C\u0E42\u0E2B\u0E25\u0E14\
  \u0E40\u0E27\u0E47\u0E1A\u0E40\u0E1E\u0E08\u0E43\u0E19 Visual Basic for Applications\
  \ (VBA) \u0E40\u0E01\u0E35\u0E48\u0E22\u0E27\u0E02\u0E49\u0E2D\u0E07\u0E01\u0E31\
  \u0E1A\u0E01\u0E32\u0E23\u0E40\u0E23\u0E35\u0E22\u0E01\u0E40\u0E19\u0E37\u0E49\u0E2D\
  \u0E2B\u0E32 HTML \u0E02\u0E2D\u0E07\u0E40\u0E27\u0E47\u0E1A\u0E40\u0E1E\u0E08\u0E08\
  \u0E32\u0E01\u0E2D\u0E34\u0E19\u0E40\u0E17\u0E2D\u0E23\u0E4C\u0E40\u0E19\u0E47\u0E15\
  \u2026"
lastmod: '2024-03-17T21:57:56.036806-06:00'
model: gpt-4-0125-preview
summary: "\u0E01\u0E32\u0E23\u0E14\u0E32\u0E27\u0E19\u0E4C\u0E42\u0E2B\u0E25\u0E14\
  \u0E40\u0E27\u0E47\u0E1A\u0E40\u0E1E\u0E08\u0E43\u0E19 Visual Basic for Applications\
  \ (VBA) \u0E40\u0E01\u0E35\u0E48\u0E22\u0E27\u0E02\u0E49\u0E2D\u0E07\u0E01\u0E31\
  \u0E1A\u0E01\u0E32\u0E23\u0E40\u0E23\u0E35\u0E22\u0E01\u0E40\u0E19\u0E37\u0E49\u0E2D\
  \u0E2B\u0E32 HTML \u0E02\u0E2D\u0E07\u0E40\u0E27\u0E47\u0E1A\u0E40\u0E1E\u0E08\u0E08\
  \u0E32\u0E01\u0E2D\u0E34\u0E19\u0E40\u0E17\u0E2D\u0E23\u0E4C\u0E40\u0E19\u0E47\u0E15\
  \ \u0E42\u0E1B\u0E23\u0E41\u0E01\u0E23\u0E21\u0E40\u0E21\u0E2D\u0E23\u0E4C\u0E21\
  \u0E31\u0E01\u0E08\u0E30\u0E17\u0E33\u0E07\u0E32\u0E19\u0E19\u0E35\u0E49\u0E40\u0E1E\
  \u0E37\u0E48\u0E2D\u0E14\u0E33\u0E40\u0E19\u0E34\u0E19\u0E01\u0E32\u0E23\u0E2B\u0E23\
  \u0E37\u0E2D\u0E27\u0E34\u0E40\u0E04\u0E23\u0E32\u0E30\u0E2B\u0E4C\u0E40\u0E19\u0E37\
  \u0E49\u0E2D\u0E2B\u0E32\u0E02\u0E2D\u0E07\u0E40\u0E27\u0E47\u0E1A\u0E44\u0E0B\u0E15\
  \u0E4C\u0E42\u0E14\u0E22\u0E01\u0E32\u0E23\u0E40\u0E02\u0E35\u0E22\u0E19\u0E42\u0E1B\
  \u0E23\u0E41\u0E01\u0E23\u0E21 \u0E08\u0E32\u0E01\u0E20\u0E32\u0E22\u0E43\u0E19\
  \ Excel, Access \u0E2B\u0E23\u0E37\u0E2D\u0E41\u0E2D\u0E1B\u0E1E\u0E25\u0E34\u0E40\
  \u0E04\u0E0A\u0E31\u0E48\u0E19 Office \u0E2D\u0E37\u0E48\u0E19 \u0E46."
title: "\u0E01\u0E32\u0E23\u0E14\u0E32\u0E27\u0E19\u0E4C\u0E42\u0E2B\u0E25\u0E14\u0E2B\
  \u0E19\u0E49\u0E32\u0E40\u0E27\u0E47\u0E1A"
weight: 42
---

## วิธีการ:
เพื่อดาวน์โหลดเว็บเพจใน VBA คุณสามารถใช้ห้องสมุด Microsoft XML, v6.0 (MSXML6) ซึ่งช่วยในการร้องขอ HTTP จากเซิร์ฟเวอร์ ก่อนที่จะเริ่มเขียนโค้ด ตรวจสอบว่าคุณได้เปิดใช้งานการอ้างอิงนี้ในตัวแก้ไข VBA ของคุณโดยไปที่ `เครื่องมือ` -> `การอ้างอิง` และตรวจสอบ `Microsoft XML, v6.0`

นี่คือตัวอย่างง่าย ๆ ของวิธีการดาวน์โหลดเนื้อหา HTML ของเว็บเพจ:

```basic
Sub DownloadWebPage()
    Dim request As Object
    Dim url As String
    Dim response As String
    
    ' เริ่มต้นของออบเจกต์ XML HTTP request
    Set request = CreateObject("MSXML2.XMLHTTP")
    
    url = "http://www.example.com"
    
    ' เปิดการร้องขอแบบซิงโครนัส
    request.Open "GET", url, False
    
    ' ส่งการร้องขอไปยังเซิร์ฟเวอร์
    request.send
    
    ' รับข้อความตอบกลับ
    response = request.responseText
    
    ' แสดงผลข้อความตอบกลับในหน้าต่างทันที (เพื่อวัตถุประสงค์ในการดีบัก)
    Debug.Print response
    
    ' ทำความสะอาด
    Set request = Nothing
End Sub
```

การรัน Subroutine นี้จะพิมพ์ HTML ของเว็บไซต์ `http://www.example.com` ออกมาที่ Immediate Window ในตัวแก้ไข VBA โปรดสังเกตว่าพารามิเตอร์ `False` ในเมธอด `Open` ทำให้การร้องขอเป็นแบบซิงโครนัสหมายความว่าโค้ดจะรอจนกระทั่งเว็บเพจถูกดาวน์โหลดก่อนที่จะเคลื่อนไปยังบรรทัดถัดไป

## การทำความเข้าใจลึกซึ้ง
เทคนิคที่แสดงอยู่นี้ขึ้นอยู่กับ MSXML, การดำเนินการของ Microsoft ตามมาตรฐาน XML HTTP Request ซึ่งมักจะใช้สำหรับการร้องขอ AJAX ในการพัฒนาเว็บ ส่วนประกอบนี้เป็นส่วนหนึ่งของเทคโนโลยีสแต็คของ Microsoft มาเป็นระยะเวลานานทำให้เป็นทางเลือกที่แข็งแกร่งสำหรับการร้องขอเครือข่ายใน VBA

อย่างไรก็ตาม การพึ่งพา MSXML และ VBA สำหรับการดาวน์โหลดและการแยกวิเคราะห์เนื้อหาเว็บอาจเป็นเรื่องที่จำกัด โดยเฉพาะกับแอปพลิเคชันเว็บสมัยใหม่ที่ใช้ JavaScript อย่างหนักเพื่อการเรนเดอร์เนื้อหาแบบไดนามิก ข้อจำกัดเหล่านี้อาจทำให้ภาษาอื่นหรือเครื่องมือเช่น Python พร้อมกับไลบรารีเช่น BeautifulSoup หรือ Selenium เหมาะสมกว่าสำหรับงานดึงข้อมูลเว็บ เนื่องจากมีความสามารถในการทำงาน JavaScript และจัดการกับการโต้ตอบเว็บไซท์ที่ซับซ้อนได้

ถึงอย่างไรก็ตาม สำหรับงานง่าย ๆ ที่เกี่ยวข้องกับการเรียกเนื้อหา HTML ที่ตรงไปตรงมาหรือเมื่อทำงานภายในขอบเขตของแอปพลิเคชั่น Office VBA ยังคงเป็นเครื่องมือที่ปฏิบัติได้จริง การรวมกันในชุด Office ช่วยให้สามารถจัดการเอกสารได้โดยตรงตามเนื้อหาเว็บ โดยมีข้อได้เปรียบเฉพาะทางสำหรับกรณีการใช้งานบางอย่าง
