---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 21:47:13.674984-06:00
description: "\u0E01\u0E32\u0E23\u0E2B\u0E32\u0E04\u0E27\u0E32\u0E21\u0E22\u0E32\u0E27\
  \u0E02\u0E2D\u0E07\u0E2A\u0E15\u0E23\u0E34\u0E07\u0E2B\u0E21\u0E32\u0E22\u0E16\u0E36\
  \u0E07\u0E01\u0E32\u0E23\u0E19\u0E31\u0E1A\u0E08\u0E33\u0E19\u0E27\u0E19\u0E15\u0E31\
  \u0E27\u0E2D\u0E31\u0E01\u0E29\u0E23\u0E17\u0E35\u0E48\u0E21\u0E35\u0E2D\u0E22\u0E39\
  \u0E48\u0E43\u0E19\u0E19\u0E31\u0E49\u0E19 \u0E42\u0E1B\u0E23\u0E41\u0E01\u0E23\u0E21\
  \u0E40\u0E21\u0E2D\u0E23\u0E4C\u0E17\u0E33\u0E40\u0E0A\u0E48\u0E19\u0E19\u0E35\u0E49\
  \u0E40\u0E1E\u0E37\u0E48\u0E2D\u0E15\u0E23\u0E27\u0E08\u0E2A\u0E2D\u0E1A\u0E04\u0E27\
  \u0E32\u0E21\u0E16\u0E39\u0E01\u0E15\u0E49\u0E2D\u0E07, \u0E08\u0E31\u0E14\u0E23\
  \u0E39\u0E1B\u0E41\u0E1A\u0E1A,\u2026"
lastmod: '2024-03-17T21:57:55.980087-06:00'
model: gpt-4-0125-preview
summary: "\u0E01\u0E32\u0E23\u0E2B\u0E32\u0E04\u0E27\u0E32\u0E21\u0E22\u0E32\u0E27\
  \u0E02\u0E2D\u0E07\u0E2A\u0E15\u0E23\u0E34\u0E07\u0E2B\u0E21\u0E32\u0E22\u0E16\u0E36\
  \u0E07\u0E01\u0E32\u0E23\u0E19\u0E31\u0E1A\u0E08\u0E33\u0E19\u0E27\u0E19\u0E15\u0E31\
  \u0E27\u0E2D\u0E31\u0E01\u0E29\u0E23\u0E17\u0E35\u0E48\u0E21\u0E35\u0E2D\u0E22\u0E39\
  \u0E48\u0E43\u0E19\u0E19\u0E31\u0E49\u0E19 \u0E42\u0E1B\u0E23\u0E41\u0E01\u0E23\u0E21\
  \u0E40\u0E21\u0E2D\u0E23\u0E4C\u0E17\u0E33\u0E40\u0E0A\u0E48\u0E19\u0E19\u0E35\u0E49\
  \u0E40\u0E1E\u0E37\u0E48\u0E2D\u0E15\u0E23\u0E27\u0E08\u0E2A\u0E2D\u0E1A\u0E04\u0E27\
  \u0E32\u0E21\u0E16\u0E39\u0E01\u0E15\u0E49\u0E2D\u0E07, \u0E08\u0E31\u0E14\u0E23\
  \u0E39\u0E1B\u0E41\u0E1A\u0E1A, \u0E2B\u0E23\u0E37\u0E2D\u0E1B\u0E23\u0E30\u0E21\
  \u0E27\u0E25\u0E1C\u0E25\u0E02\u0E49\u0E2D\u0E21\u0E39\u0E25\u0E02\u0E49\u0E2D\u0E04\
  \u0E27\u0E32\u0E21\u0E44\u0E14\u0E49\u0E2D\u0E22\u0E48\u0E32\u0E07\u0E21\u0E35\u0E1B\
  \u0E23\u0E30\u0E2A\u0E34\u0E17\u0E18\u0E34\u0E20\u0E32\u0E1E."
title: "\u0E04\u0E49\u0E19\u0E2B\u0E32\u0E04\u0E27\u0E32\u0E21\u0E22\u0E32\u0E27\u0E02\
  \u0E2D\u0E07\u0E2A\u0E15\u0E23\u0E34\u0E07"
weight: 7
---

## วิธีการ:
Rust ให้คุณใช้ `len()` สำหรับความยาวโดยตรง:

```Rust
fn main() {
    let greeting = "Hello, world!";
    println!("Length: {}", greeting.len());
}
```

ผลลัพธ์: `Length: 13`

แต่ระวัง, `len()` นับเป็นไบต์, ไม่ใช่ตัวอักษร สำหรับนับจำนวนตัวอักษร, ใช้ `.chars().count()`:

```Rust
fn main() {
    let greeting = "¡Hola, mundo!";
    println!("Character count: {}", greeting.chars().count());
}
```

ผลลัพธ์: `Character count: 12`

## ลงลึก
`len()` นับเป็นไบต์เพราะว่าสตริงใน Rust เป็นรหัส UTF-8 โดยประวัติศาสตร์, คอมพิวเตอร์รุ่นแรกใช้ ASCII, ที่แทนแต่ละตัวอักษรด้วยไบต์เดียว UTF-8, อย่างไรก็ตาม, รองรับอักขระหลากหลาย, ใช้ 1 ถึง 4 ไบต์ต่อตัว

เมื่อคุณเรียก `len()`, Rust นับไบต์ในสตริง, ซึ่งเร็วแต่ไม่จำเป็นต้องตรงกับจำนวนตัวอักษรเสมอไป ตัวอย่างเช่น, อิโมจิหรือตัวอักษรที่มีเครื่องหมายอักขระต่างๆ นั้นใช้ไบต์มากกว่าหนึ่งไบต์ นั่นเป็นเหตุผลว่าทำไม `.chars().count()` จึงสำคัญ — มันวนซ้ำผ่านตัวอักษรและให้จำนวนค่า Unicode scalar, ซึ่งเป็นจำนวนตัวอักษรที่คนส่วนใหญ่คาดหวัง

สำหรับทางเลือก, `.chars().count()` มีความแม่นยำแต่ช้าสำหรับสตริงยาวๆ เพราะต้องวนซ้ำผ่านตัวอักษรทุกตัว ถ้าประสิทธิภาพเป็นสิ่งสำคัญ, และคุณมั่นใจว่ากำลังจัดการกับอักขระ ASCII หรือ Unicode ที่มีขนาดคงที่, `len()` จึงมีประสิทธิภาพมากกว่า

ในที่สุด, จำไว้ว่าการดัชนีสตริงของ Rust ไม่อนุญาตให้เข้าถึงโดยตรงโดยตำแหน่งตัวอักษร เนื่องจากการทำงานของรหัส UTF-8 Rust ป้องกันการดำเนินการที่อาจทำให้สตริงแตกหรือตัดที่จุดที่ไม่ถูกต้อง ซึ่งอาจไม่แสดงถึงตัวอักษรเต็ม

## อ่านเพิ่มเติม
- คู่มือการใช้งานสตริงอย่างเป็นทางการของ Rust: [https://doc.rust-lang.org/std/string/](https://doc.rust-lang.org/std/string/)
- Rust Book เกี่ยวกับสตริง: [https://doc.rust-lang.org/book/ch08-02-strings.html](https://doc.rust-lang.org/book/ch08-02-strings.html)
- เพื่อเข้าใจเพิ่มเติมเกี่ยวกับ UTF-8 และ ASCII, ดูที่ [https://tools.ietf.org/html/rfc3629](https://tools.ietf.org/html/rfc3629)
