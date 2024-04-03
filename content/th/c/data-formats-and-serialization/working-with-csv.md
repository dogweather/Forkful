---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 21:52:54.254673-06:00
description: "\u0E43\u0E19\u0E42\u0E25\u0E01\u0E02\u0E2D\u0E07\u0E01\u0E32\u0E23\u0E40\
  \u0E02\u0E35\u0E22\u0E19\u0E42\u0E1B\u0E23\u0E41\u0E01\u0E23\u0E21, \u0E01\u0E32\
  \u0E23\u0E17\u0E33\u0E07\u0E32\u0E19\u0E01\u0E31\u0E1A\u0E44\u0E1F\u0E25\u0E4C CSV\
  \ (Comma-Separated Values) \u0E2B\u0E21\u0E32\u0E22\u0E16\u0E36\u0E07\u0E01\u0E32\
  \u0E23\u0E2D\u0E48\u0E32\u0E19\u0E41\u0E25\u0E30\u0E40\u0E02\u0E35\u0E22\u0E19\u0E02\
  \u0E49\u0E2D\u0E21\u0E39\u0E25\u0E44\u0E1B\u0E22\u0E31\u0E07\u0E44\u0E1F\u0E25\u0E4C\
  \u0E02\u0E49\u0E2D\u0E04\u0E27\u0E32\u0E21\u0E17\u0E35\u0E48\u0E16\u0E39\u0E01\u0E08\
  \u0E31\u0E14\u0E23\u0E30\u0E40\u0E1A\u0E35\u0E22\u0E1A\u0E40\u0E1B\u0E47\u0E19\u0E41\
  \u0E16\u0E27\u0E46\u2026"
lastmod: '2024-03-17T21:57:56.708057-06:00'
model: gpt-4-0125-preview
summary: "\u0E43\u0E19\u0E42\u0E25\u0E01\u0E02\u0E2D\u0E07\u0E01\u0E32\u0E23\u0E40\
  \u0E02\u0E35\u0E22\u0E19\u0E42\u0E1B\u0E23\u0E41\u0E01\u0E23\u0E21, \u0E01\u0E32\
  \u0E23\u0E17\u0E33\u0E07\u0E32\u0E19\u0E01\u0E31\u0E1A\u0E44\u0E1F\u0E25\u0E4C CSV\
  \ (Comma-Separated Values) \u0E2B\u0E21\u0E32\u0E22\u0E16\u0E36\u0E07\u0E01\u0E32\
  \u0E23\u0E2D\u0E48\u0E32\u0E19\u0E41\u0E25\u0E30\u0E40\u0E02\u0E35\u0E22\u0E19\u0E02\
  \u0E49\u0E2D\u0E21\u0E39\u0E25\u0E44\u0E1B\u0E22\u0E31\u0E07\u0E44\u0E1F\u0E25\u0E4C\
  \u0E02\u0E49\u0E2D\u0E04\u0E27\u0E32\u0E21\u0E17\u0E35\u0E48\u0E16\u0E39\u0E01\u0E08\
  \u0E31\u0E14\u0E23\u0E30\u0E40\u0E1A\u0E35\u0E22\u0E1A\u0E40\u0E1B\u0E47\u0E19\u0E41\
  \u0E16\u0E27\u0E46 \u0E42\u0E14\u0E22\u0E41\u0E15\u0E48\u0E25\u0E30\u0E41\u0E16\u0E27\
  \u0E41\u0E17\u0E19\u0E23\u0E30\u0E40\u0E1A\u0E35\u0E22\u0E1A\u0E01\u0E32\u0E23\u0E41\
  \u0E25\u0E30\u0E1F\u0E34\u0E25\u0E14\u0E4C\u0E02\u0E2D\u0E07\u0E41\u0E15\u0E48\u0E25\
  \u0E30\u0E40\u0E23\u0E01\u0E04\u0E2D\u0E23\u0E4C\u0E14\u0E08\u0E30\u0E16\u0E39\u0E01\
  \u0E41\u0E22\u0E01\u0E14\u0E49\u0E27\u0E22\u0E08\u0E38\u0E25\u0E20\u0E32\u0E04."
title: "\u0E01\u0E32\u0E23\u0E17\u0E33\u0E07\u0E32\u0E19\u0E01\u0E31\u0E1A CSV"
weight: 37
---

## วิธีการ:


### การอ่านไฟล์ CSV
ในการอ่านไฟล์ CSV ด้วยภาษา C, เราใช้ฟังก์ชัน I/O ไฟล์มาตรฐานควบคู่กับฟังก์ชันการจัดการสตริงเพื่อแยกวิเคราะห์แต่ละบรรทัด. ด้านล่างเป็นตัวอย่างพื้นฐานของการอ่านไฟล์ CSV และการพิมพ์ฟิลด์ของแต่ละแถวไปยังคอนโซล

```c
#include <stdio.h>
#include <string.h>

int main() {
    FILE *fp = fopen("data.csv", "r");
    if (!fp) {
        printf("Can't open file\n");
        return 1;
    }

    char buf[1024];
    while (fgets(buf, 1024, fp)) {
        char *field = strtok(buf, ",");
        while(field) {
            printf("%s\n", field);
            field = strtok(NULL, ",");
        }
    }

    fclose(fp);
    return 0;
}
```

ตัวอย่าง `data.csv`:
```
Name,Age,Occupation
John Doe,29,Software Engineer
```

ตัวอย่างผลลัพธ์:
```
Name
Age
Occupation
John Doe
29
Software Engineer
```

### การเขียนไปยังไฟล์ CSV
ในทำนองเดียวกัน การเขียนไปยังไฟล์ CSV นั้นเกี่ยวข้องกับการใช้ `fprintf` เพื่อบันทึกข้อมูลในรูปแบบที่แยกด้วยจุลภาค

```c
#include <stdio.h>

int main() {
    FILE *fp = fopen("output.csv", "w");
    if (!fp) {
        printf("Can't open file\n");
        return 1;
    }

    char *headers[] = {"Name", "Age", "Occupation", NULL};
    for (int i = 0; headers[i] != NULL; i++) {
        fprintf(fp, "%s%s", headers[i], (headers[i+1] != NULL) ? "," : "\n");
    }
    fprintf(fp, "%s,%d,%s\n", "Jane Doe", 27, "Data Scientist");

    fclose(fp);
    return 0;
}
```

ตัวอย่างเนื้อหา `output.csv`:
```
Name,Age,Occupation
Jane Doe,27,Data Scientist
```

## การศึกษาเจาะลึก
รูปแบบ CSV, ถึงแม้ดูเหมือนจะตรงไปตรงมา, แต่มาพร้อมกับความซับซ้อนต่างๆ เช่น การจัดการจุลภาคภายในฟิลด์และการห่อหุ้มฟิลด์ด้วยเครื่องหมายคำพูด. ตัวอย่างพื้นฐานที่แสดงออกมาไม่ได้อธิบายถึงความซับซ้อนเหล่านี้ หรือการจัดการกับข้อผิดพลาดที่อาจเกิดขึ้นอย่างมีประสิทธิภาพ.

ในประวัติศาสตร์, การจัดการ CSV ในภาษา C ส่วนใหญ่ได้ทำอย่างต่อเนื่องเนื่องจากลักษณะของภาษาที่อยู่ในระดับต่ำและการขาดการสร้างโครงสร้างพื้นฐานระดับสูงสำหรับงานดังกล่าว. การจัดการด้วยตนเองนี้รวมถึงการเปิดไฟล์, การอ่านบรรทัด, การแยกสตริง, และการแปลงประเภทข้อมูลตามที่ต้องการ.

ตอนที่การจัดการไฟล์ CSV โดยตรงในภาษา C ให้ประสบการณ์การเรียนรู้ที่มีค่าเกี่ยวกับไฟล์ I/O และการจัดการสตริง, มีทางเลือกสมัยใหม่หลายอย่างที่สัญญาว่าจะมีประสิทธิภาพและกระบวนการที่น้อยผิดพลาด. ห้องสมุดเช่น `libcsv` และ `csv-parser` ให้ฟังก์ชันครอบคลุมสำหรับอ่านและเขียนไฟล์ CSV, รวมถึงการสนับสนุนฟิลด์ที่ถูกอ้างถึงด้วยเครื่องหมายคำพูดและตัวคั่นที่กำหนดเอง.

นอกจากนี้, เมื่อทำงานในระบบนิเวศที่รองรับ, การรวมกับภาษาหรือแพลตฟอร์มที่ให้ฟังก์ชันการจัดการ CSV ระดับสูง (เช่น Python กับไลบรารี `pandas` ของมัน) อาจเป็นทางเลือกที่เหมาะสมกว่าสำหรับการใช้งานที่ต้องการการประมวลผล CSV อย่างหนัก. ทางเลือกข้ามภาษานี้ใช้ประโยชน์จากประสิทธิภาพและความสามารถในการเขียนโปรแกรมระบบของ C ขณะที่ใช้ความสะดวกในการใช้งานจากภาษาอื่นสำหรับงานเฉพาะเช่นการจัดการ CSV.
