---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 21:46:23.630134-06:00
description: "\u0E01\u0E32\u0E23\u0E14\u0E32\u0E27\u0E19\u0E4C\u0E42\u0E2B\u0E25\u0E14\
  \u0E2B\u0E19\u0E49\u0E32\u0E40\u0E27\u0E47\u0E1A\u0E2B\u0E21\u0E32\u0E22\u0E16\u0E36\
  \u0E07\u0E01\u0E32\u0E23\u0E04\u0E27\u0E49\u0E32\u0E40\u0E19\u0E37\u0E49\u0E2D\u0E2B\
  \u0E32 HTML \u0E14\u0E34\u0E1A\u0E08\u0E32\u0E01\u0E2D\u0E34\u0E19\u0E40\u0E17\u0E2D\
  \u0E23\u0E4C\u0E40\u0E19\u0E47\u0E15\u0E42\u0E14\u0E22\u0E43\u0E0A\u0E49\u0E42\u0E04\
  \u0E49\u0E14 \u0E42\u0E1B\u0E23\u0E41\u0E01\u0E23\u0E21\u0E40\u0E21\u0E2D\u0E23\u0E4C\
  \u0E17\u0E33\u0E40\u0E0A\u0E48\u0E19\u0E19\u0E35\u0E49\u0E40\u0E1E\u0E37\u0E48\u0E2D\
  \u0E1B\u0E23\u0E30\u0E21\u0E27\u0E25\u0E1C\u0E25\u0E02\u0E49\u0E2D\u0E21\u0E39\u0E25\
  \ \u0E42\u0E15\u0E49\u0E15\u0E2D\u0E1A\u0E01\u0E31\u0E1A\u0E40\u0E27\u0E47\u0E1A\
  \u0E40\u0E0B\u0E2D\u0E23\u0E4C\u0E27\u0E34\u0E2A\u2026"
lastmod: '2024-03-17T21:57:56.225111-06:00'
model: gpt-4-0125-preview
summary: "\u0E01\u0E32\u0E23\u0E14\u0E32\u0E27\u0E19\u0E4C\u0E42\u0E2B\u0E25\u0E14\
  \u0E2B\u0E19\u0E49\u0E32\u0E40\u0E27\u0E47\u0E1A\u0E2B\u0E21\u0E32\u0E22\u0E16\u0E36\
  \u0E07\u0E01\u0E32\u0E23\u0E04\u0E27\u0E49\u0E32\u0E40\u0E19\u0E37\u0E49\u0E2D\u0E2B\
  \u0E32 HTML \u0E14\u0E34\u0E1A\u0E08\u0E32\u0E01\u0E2D\u0E34\u0E19\u0E40\u0E17\u0E2D\
  \u0E23\u0E4C\u0E40\u0E19\u0E47\u0E15\u0E42\u0E14\u0E22\u0E43\u0E0A\u0E49\u0E42\u0E04\
  \u0E49\u0E14 \u0E42\u0E1B\u0E23\u0E41\u0E01\u0E23\u0E21\u0E40\u0E21\u0E2D\u0E23\u0E4C\
  \u0E17\u0E33\u0E40\u0E0A\u0E48\u0E19\u0E19\u0E35\u0E49\u0E40\u0E1E\u0E37\u0E48\u0E2D\
  \u0E1B\u0E23\u0E30\u0E21\u0E27\u0E25\u0E1C\u0E25\u0E02\u0E49\u0E2D\u0E21\u0E39\u0E25\
  \ \u0E42\u0E15\u0E49\u0E15\u0E2D\u0E1A\u0E01\u0E31\u0E1A\u0E40\u0E27\u0E47\u0E1A\
  \u0E40\u0E0B\u0E2D\u0E23\u0E4C\u0E27\u0E34\u0E2A \u0E2B\u0E23\u0E37\u0E2D\u0E40\u0E1E\
  \u0E35\u0E22\u0E07\u0E41\u0E04\u0E48\u0E1A\u0E31\u0E19\u0E17\u0E36\u0E01\u0E02\u0E49\
  \u0E2D\u0E21\u0E39\u0E25\u0E2A\u0E33\u0E2B\u0E23\u0E31\u0E1A\u0E43\u0E0A\u0E49\u0E07\
  \u0E32\u0E19\u0E41\u0E1A\u0E1A\u0E2D\u0E2D\u0E1F\u0E44\u0E25\u0E19\u0E4C."
title: "\u0E01\u0E32\u0E23\u0E14\u0E32\u0E27\u0E19\u0E4C\u0E42\u0E2B\u0E25\u0E14\u0E2B\
  \u0E19\u0E49\u0E32\u0E40\u0E27\u0E47\u0E1A"
weight: 42
---

## วิธีการ:
C# ทำให้การดาวน์โหลดหน้าเว็บเป็นเรื่องง่ายด้วยคลาส `HttpClient` นี่คือตัวอย่างอย่างรวดเร็ว:

```C#
using System;
using System.Net.Http;
using System.Threading.Tasks;

class Program
{
    static async Task Main(string[] args)
    {
        using (HttpClient client = new HttpClient())
        {
            try
            {
                string url = "http://example.com"; // แทนที่ด้วย URL ที่ต้องการ
                HttpResponseMessage response = await client.GetAsync(url);
                response.EnsureSuccessStatusCode();
                string responseBody = await response.Content.ReadAsStringAsync();
                
                Console.WriteLine(responseBody); // แสดงเนื้อหา HTML ดิบ
            }
            catch (HttpRequestException e)
            {
                Console.WriteLine("\nException Caught!");
                Console.WriteLine("Message :{0} ", e.Message);
            }
        }
    }
}
```

นี่จะแสดงเนื้อหา HTML ของหน้าเว็บที่ระบุไว้ในคอนโซล

## ขุดลึก
ก่อนหน้า `HttpClient`, C# ใช้คลาสเช่น `WebClient` และ `HttpWebRequest` เพื่อดาวน์โหลดเนื้อหาเว็บ `HttpClient` เป็นเวอร์ชันล่าสุด และถูกออกแบบให้สามารถใช้งานซ้ำได้ มีประสิทธิภาพ และรองรับการปฏิบัติการแบบอะซิงโครนัส ทำให้เป็นตัวเลือกที่นิยมสำหรับแอปพลิเคชันใหม่ๆ

มีตัวเลือกอื่นๆ อยู่ เช่น ไลบรารีบุคคลที่สาม เช่น `HtmlAgilityPack` สามารถแยกวิเคราะห์ HTML ทำให้ง่ายต่อการนำทาง DOM หรือดึงข้อมูลเฉพาะโดยไม่ต้องจัดการกับสตริง HTML ดิบ

เมื่อดาวน์โหลดหน้าเว็บ จำไว้ว่า: ให้ความเคารพต่อไฟล์ robots.txt จัดการข้อยกเว้น และระมัดระวังในเงื่อนไขการใช้งานของเว็บไซต์

## ดูเพิ่มเติม
- [HttpClient Class Documentation](https://docs.microsoft.com/en-us/dotnet/api/system.net.http.httpclient)
- [Async and Await](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/async/)
- [HTML Agility Pack on GitHub](https://github.com/zzzprojects/html-agility-pack)
- [การให้ความเคารพต่อ robots.txt](https://developers.google.com/search/docs/advanced/robots/intro)
