---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 21:53:08.812988-06:00
description: "\u0E01\u0E32\u0E23\u0E43\u0E0A\u0E49\u0E07\u0E32\u0E19 JSON (JavaScript\
  \ Object Notation) \u0E43\u0E19\u0E20\u0E32\u0E29\u0E32 C \u0E1B\u0E23\u0E30\u0E01\
  \u0E2D\u0E1A\u0E44\u0E1B\u0E14\u0E49\u0E27\u0E22\u0E01\u0E32\u0E23\u0E27\u0E34\u0E40\
  \u0E04\u0E23\u0E32\u0E30\u0E2B\u0E4C, \u0E2A\u0E23\u0E49\u0E32\u0E07, \u0E41\u0E25\
  \u0E30\u0E08\u0E31\u0E14\u0E01\u0E32\u0E23\u0E42\u0E04\u0E23\u0E07\u0E2A\u0E23\u0E49\
  \u0E32\u0E07\u0E02\u0E49\u0E2D\u0E21\u0E39\u0E25 JSON\u2026"
lastmod: '2024-03-17T21:57:56.707158-06:00'
model: gpt-4-0125-preview
summary: "\u0E01\u0E32\u0E23\u0E43\u0E0A\u0E49\u0E07\u0E32\u0E19 JSON (JavaScript\
  \ Object Notation) \u0E43\u0E19\u0E20\u0E32\u0E29\u0E32 C \u0E1B\u0E23\u0E30\u0E01\
  \u0E2D\u0E1A\u0E44\u0E1B\u0E14\u0E49\u0E27\u0E22\u0E01\u0E32\u0E23\u0E27\u0E34\u0E40\
  \u0E04\u0E23\u0E32\u0E30\u0E2B\u0E4C, \u0E2A\u0E23\u0E49\u0E32\u0E07, \u0E41\u0E25\
  \u0E30\u0E08\u0E31\u0E14\u0E01\u0E32\u0E23\u0E42\u0E04\u0E23\u0E07\u0E2A\u0E23\u0E49\
  \u0E32\u0E07\u0E02\u0E49\u0E2D\u0E21\u0E39\u0E25 JSON \u0E19\u0E31\u0E01\u0E1E\u0E31\
  \u0E12\u0E19\u0E32\u0E17\u0E33\u0E40\u0E0A\u0E48\u0E19\u0E19\u0E35\u0E49\u0E40\u0E1E\
  \u0E37\u0E48\u0E2D\u0E40\u0E1B\u0E34\u0E14\u0E43\u0E0A\u0E49\u0E07\u0E32\u0E19\u0E01\
  \u0E32\u0E23\u0E2A\u0E37\u0E48\u0E2D\u0E2A\u0E32\u0E23\u0E01\u0E31\u0E1A\u0E40\u0E27\
  \u0E47\u0E1A\u0E40\u0E0B\u0E2D\u0E23\u0E4C\u0E27\u0E34\u0E2A, \u0E01\u0E32\u0E23\
  \u0E08\u0E31\u0E14\u0E40\u0E01\u0E47\u0E1A\u0E02\u0E49\u0E2D\u0E21\u0E39\u0E25 \u0E2B\
  \u0E23\u0E37\u0E2D\u0E44\u0E1F\u0E25\u0E4C\u0E01\u0E32\u0E23\u0E01\u0E33\u0E2B\u0E19\
  \u0E14\u0E04\u0E48\u0E32\u0E43\u0E19\u0E23\u0E39\u0E1B\u0E41\u0E1A\u0E1A\u0E17\u0E35\
  \u0E48\u0E40\u0E1A\u0E32\u0E41\u0E25\u0E30\u0E2D\u0E48\u0E32\u0E19\u0E07\u0E48\u0E32\
  \u0E22\u0E2A\u0E33\u0E2B\u0E23\u0E31\u0E1A\u0E21\u0E19\u0E38\u0E29\u0E22\u0E4C."
title: "\u0E01\u0E32\u0E23\u0E17\u0E33\u0E07\u0E32\u0E19\u0E01\u0E31\u0E1A JSON"
weight: 38
---

## วิธีการ:
ในการใช้งาน JSON ในภาษา C, คุณมักจะใช้ไลบรารีเช่น `jansson` หรือ `json-c` เนื่องจากภาษา C ขาดการสนับสนุน JSON โดยตรง ที่นี่ เราจะโฟกัสที่ `jansson` เนื่องจากความง่ายในการใช้งานและการบำรุงรักษาที่เป็นปัจจุบัน ขั้นแรก, ติดตั้งไลบรารี (เช่น ใช้งาน package manager เช่น `apt` บน Ubuntu: `sudo apt-get install libjansson-dev`)

เรามาเริ่มกันด้วยการวิเคราะห์สตริง JSON และการเข้าถึงเนื้อหาของมัน:

```c
#include <jansson.h>
#include <stdio.h>

int main() {
    const char *json_string = "{\"name\":\"John Doe\",\"age\":30}";
    json_error_t error;
    json_t *root = json_loads(json_string, 0, &error);
    
    if(!root) {
        fprintf(stderr, "error: on line %d: %s\n", error.line, error.text);
        return 1;
    }
    
    const char *name;
    int age;
    json_unpack(root, "{s:s, s:i}", "name", &name, "age", &age);
    
    printf("Name: %s\nAge: %d\n", name, age);
    
    json_decref(root);
    return 0;
}
```

ผลลัพธ์ตัวอย่าง:
```
Name: John Doe
Age: 30
```

ต่อไป, การสร้างและการแสดงผลของวัตถุ JSON:

```c
#include <jansson.h>
#include <stdio.h>

int main() {
    json_t *root = json_object();
    json_object_set_new(root, "name", json_string("Jane Doe"));
    json_object_set_new(root, "age", json_integer(25));
    
    char *json_dump = json_dumps(root, JSON_ENCODE_ANY);
    printf("%s\n", json_dump);
    
    free(json_dump);
    json_decref(root);
    return 0;
}
```

ผลลัพธ์ตัวอย่าง:
```
{"name": "Jane Doe", "age": 25}
```

ตัวอย่างดังกล่าวนี้แสดงให้เห็นถึงพื้นฐานของการโหลดสตริง JSON, การแกะสลักค่าที่มี, การสร้างวัตถุ JSON ใหม่, แล้วจากนั้นการแสดงมันออกมาเป็นสตริง

## ดำดิ่งลึก
ความจำเป็นในการทำงานกับ JSON ในภาษา C เกิดจากการที่เว็บไซต์นั้นเลือกใช้ JSON เป็นรูปแบบหลักสำหรับการแลกเปลี่ยนข้อมูล ความเรียบง่ายและประสิทธิภาพของ JSON ทำให้มันเร็วกว่า XML อย่างรวดเร็ว ถึงแม้ภาษา C เริ่มแรกจะไม่มีการสนับสนุนตรงสำหรับการจัดการ JSON การแก้ปัญหาแต่เดิมเกี่ยวข้องกับการจัดการสตริงแบบด้วยตนเองซึ่งเสี่ยงต่อข้อผิดพลาดและไม่มีประสิทธิภาพ ไลบรารีเช่น `jansson` และ `json-c` ถูกสร้างขึ้นเพื่อเติมเต็มช่องว่างนี้ โดยให้ API ที่แข็งแกร่งสำหรับการแยกส่วน, การสร้าง, และการซีเรียไลซ์ JSON

ในขณะที่ `jansson` มอบความเรียบง่ายและความสะดวกในการใช้งาน, `json-c` อาจดึงดูดผู้ที่กำลังมองหาชุดคุณสมบัติที่กว้างขึ้น อย่างไรก็ตาม, ทางเลือกอื่นๆ เช่น ไลบรารีการแยกส่วนในภาษา C++ นำเสนอการนำเสนอที่ซับซ้อนขึ้น โดยขอบคุณต่อโครงสร้างข้อมูลที่ซับซ้อนขึ้นและการสนับสนุนไลบรารีมาตรฐานของภาษานั้น อย่างไรก็ตาม เมื่อทำงานในสภาพแวดล้อมที่ภาษา C เป็นที่ต้องการหรือจำเป็น - เช่น ระบบฝังตัวหรือเมื่อต้องจัดการกับไลบรารี C ที่มีอยู่ - การใช้ `jansson` หรือ `json-c` กลายเป็นสิ่งจำเป็น

ยังควรทราบว่าการทำงานกับ JSON ในภาษา C ต้องมีการเข้าใจที่ลึกขึ้นเกี่ยวกับการจัดการหน่วยความจำ เนื่องจากไลบรารีเหล่านี้มักจะคืนค่าวัตถุที่จัดสรรเนื้อที่อย่างพลวัตซึ่งจำเป็นต้องมีการคืนค่าอย่างชัดเจน ซึ่งเป็นความท้าทายสำหรับโปรแกรมเมอร์ในการหาความสมดุลระหว่างความสะดวกกับความรับผิดชอบในการป้องกันการรั่วไหลของหน่วยความจำ ซึ่งเป็นส่วนสำคัญของการเขียนโค้ด C ที่มีประสิทธิภาพ
