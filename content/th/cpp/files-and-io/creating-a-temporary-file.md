---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 21:46:07.550730-06:00
description: "\u0E01\u0E32\u0E23\u0E2A\u0E23\u0E49\u0E32\u0E07\u0E44\u0E1F\u0E25\u0E4C\
  \u0E0A\u0E31\u0E48\u0E27\u0E04\u0E23\u0E32\u0E27\u0E2B\u0E21\u0E32\u0E22\u0E16\u0E36\
  \u0E07\u0E01\u0E32\u0E23\u0E17\u0E33\u0E44\u0E1F\u0E25\u0E4C\u0E02\u0E36\u0E49\u0E19\
  \u0E21\u0E32\u0E40\u0E1E\u0E37\u0E48\u0E2D\u0E40\u0E01\u0E47\u0E1A\u0E02\u0E49\u0E2D\
  \u0E21\u0E39\u0E25\u0E0A\u0E31\u0E48\u0E27\u0E04\u0E23\u0E32\u0E27 \u0E41\u0E25\u0E30\
  \u0E08\u0E30\u0E16\u0E39\u0E01\u0E25\u0E1A\u0E2B\u0E25\u0E31\u0E07\u0E08\u0E32\u0E01\
  \u0E01\u0E32\u0E23\u0E43\u0E0A\u0E49\u0E07\u0E32\u0E19\u2026"
lastmod: '2024-03-17T21:57:56.540326-06:00'
model: gpt-4-0125-preview
summary: "\u0E01\u0E32\u0E23\u0E2A\u0E23\u0E49\u0E32\u0E07\u0E44\u0E1F\u0E25\u0E4C\
  \u0E0A\u0E31\u0E48\u0E27\u0E04\u0E23\u0E32\u0E27\u0E2B\u0E21\u0E32\u0E22\u0E16\u0E36\
  \u0E07\u0E01\u0E32\u0E23\u0E17\u0E33\u0E44\u0E1F\u0E25\u0E4C\u0E02\u0E36\u0E49\u0E19\
  \u0E21\u0E32\u0E40\u0E1E\u0E37\u0E48\u0E2D\u0E40\u0E01\u0E47\u0E1A\u0E02\u0E49\u0E2D\
  \u0E21\u0E39\u0E25\u0E0A\u0E31\u0E48\u0E27\u0E04\u0E23\u0E32\u0E27 \u0E41\u0E25\u0E30\
  \u0E08\u0E30\u0E16\u0E39\u0E01\u0E25\u0E1A\u0E2B\u0E25\u0E31\u0E07\u0E08\u0E32\u0E01\
  \u0E01\u0E32\u0E23\u0E43\u0E0A\u0E49\u0E07\u0E32\u0E19 \u0E42\u0E1B\u0E23\u0E41\u0E01\
  \u0E23\u0E21\u0E40\u0E21\u0E2D\u0E23\u0E4C\u0E17\u0E33\u0E01\u0E32\u0E23\u0E19\u0E35\
  \u0E49\u0E40\u0E1E\u0E37\u0E48\u0E2D\u0E08\u0E31\u0E14\u0E01\u0E32\u0E23\u0E02\u0E49\
  \u0E2D\u0E21\u0E39\u0E25\u0E23\u0E30\u0E2B\u0E27\u0E48\u0E32\u0E07\u0E02\u0E31\u0E49\
  \u0E19\u0E15\u0E2D\u0E19\u0E42\u0E14\u0E22\u0E44\u0E21\u0E48\u0E17\u0E33\u0E43\u0E2B\
  \u0E49\u0E23\u0E30\u0E1A\u0E1A\u0E44\u0E1F\u0E25\u0E4C\u0E22\u0E38\u0E48\u0E07\u0E40\
  \u0E2B\u0E22\u0E34\u0E07\u0E2B\u0E23\u0E37\u0E2D\u0E40\u0E2A\u0E35\u0E48\u0E22\u0E07\
  \u0E15\u0E48\u0E2D\u0E01\u0E32\u0E23\u0E02\u0E31\u0E14\u0E41\u0E22\u0E49\u0E07\u0E01\
  \u0E31\u0E1A\u0E44\u0E1F\u0E25\u0E4C\u0E2D\u0E37\u0E48\u0E19."
title: "\u0E2A\u0E23\u0E49\u0E32\u0E07\u0E44\u0E1F\u0E25\u0E4C\u0E0A\u0E31\u0E48\u0E27\
  \u0E04\u0E23\u0E32\u0E27"
weight: 21
---

## วิธีการ:
นี่คือวิธีการสร้างและใช้ไฟล์ชั่วคราวใน C++ ปัจจุบัน:

```C++
#include <cstdio>
#include <filesystem>
#include <iostream>

int main() {
    // สร้างไฟล์ชั่วคราวที่ไม่ซ้ำใครโดยใช้ไลบรารีระบบไฟล์
    std::filesystem::path temp_path = std::filesystem::temp_directory_path() /= std::tmpnam(nullptr);

    // เปิดไฟล์ชั่วคราว
    std::FILE* temp_file = std::fopen(temp_path.c_str(), "w+");
    if (!temp_file) {
        std::perror("การเปิดไฟล์ล้มเหลว");
        return EXIT_FAILURE;
    }

    // เขียนข้อมูลบางอย่างลงไป
    std::fputs("Hello, Temp World!\n", temp_file);

    // อย่าลืมปิดไฟล์เสมอ
    std::fclose(temp_file);

    // แสดงทางเดินของไฟล์ชั่วคราวของเรา
    std::cout << "สร้างไฟล์ชั่วคราวที่: " << temp_path << std::endl;

    // การทำความสะอาด: ลบไฟล์ชั่วคราว
    std::filesystem::remove(temp_path);

    return EXIT_SUCCESS;
}
```

ตัวอย่างผลลัพธ์ (ทางเดินจริงอาจแตกต่างกัน):

```
สร้างไฟล์ชั่วคราวที่: /tmp/abc123
```

## การศึกษาลึก
ไฟล์ชั่วคราวเป็นมือง่ายในกรณีเช่นการบันทึกสถานะ, การเรียงข้อมูลชุดใหญ่, หรือการจัดการผลลัพธ์ที่ไม่จำเป็นต้องคงอยู่ ในอดีต, ไฟล์ชั่วคราวถูกสร้างในไดเรกทอรีที่มีร่วมกัน (เช่น `/tmp` บนระบบ Unix) โดยใช้วิธีการตั้งชื่อง่ายๆ ซึ่งเสี่ยงต่อการชนกัน ภาษา C++ สมัยใหม่ใช้ไลบรารี `<filesystem>` เพื่อหลีกเลี่ยงปัญหาดังกล่าว

ทางเลือกหนึ่ง ได้แก่ การใช้พื้นที่เก็บชั่วคราวบน RAM (เช่น tmpfs ในระบบที่คล้าย Unix ส่วนใหญ่) หรือ blobs ฐานข้อมูล วิธีการเหล่านี้ช่วยเก็บข้อมูลชั่วคราวไว้ในหน่วยความจำหรือระบบที่จัดการได้ ลดภาระ I/O และเพิ่มประสิทธิภาพ

ในด้านการดำเนินงาน, จำไว้ว่า:
- การ I/O ไฟล์อาจล้มเหลว ดังนั้นควรตรวจสอบการดำเนินการของไฟล์เสมอเพื่อหาข้อผิดพลาด
- ควรปิดไฟล์เสมอเพื่อป้องกันการรั่วไหลของทรัพยากร
- ทำความสะอาด: ลบไฟล์ชั่วคราวของคุณ (ถึงแม้ระบบมักจะทำเรื่องนี้ให้ แต่มันเป็นนิสัยที่ดี)

## ดูเพิ่มเติม
- [ไลบรารีระบบไฟล์ของ C++](https://en.cppreference.com/w/cpp/filesystem)
- [ไลบรารี IOstreams ของ C++](https://en.cppreference.com/w/cpp/io)
- [การจัดการไฟล์ชั่วคราวใน C](http://www.cplusplus.com/reference/cstdio/tmpfile/)
