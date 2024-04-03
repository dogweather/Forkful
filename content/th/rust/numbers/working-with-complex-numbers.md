---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 21:53:45.324089-06:00
description: "\u0E08\u0E33\u0E19\u0E27\u0E19\u0E40\u0E0A\u0E34\u0E07\u0E0B\u0E49\u0E2D\
  \u0E19\u0E1B\u0E23\u0E30\u0E01\u0E2D\u0E1A\u0E14\u0E49\u0E27\u0E22\u0E2A\u0E48\u0E27\
  \u0E19\u0E08\u0E23\u0E34\u0E07\u0E41\u0E25\u0E30\u0E2A\u0E48\u0E27\u0E19\u0E08\u0E34\
  \u0E19\u0E15\u0E20\u0E32\u0E1E\u0E41\u0E25\u0E30\u0E21\u0E35\u0E04\u0E27\u0E32\u0E21\
  \u0E2A\u0E33\u0E04\u0E31\u0E0D\u0E21\u0E32\u0E01\u0E43\u0E19\u0E2B\u0E25\u0E32\u0E22\
  \u0E2A\u0E32\u0E02\u0E32 \u0E40\u0E0A\u0E48\u0E19 \u0E27\u0E34\u0E28\u0E27\u0E01\
  \u0E23\u0E23\u0E21, \u0E1F\u0E34\u0E2A\u0E34\u0E01\u0E2A\u0E4C \u0E41\u0E25\u0E30\
  \u0E01\u0E23\u0E32\u0E1F\u0E34\u0E01\u0E04\u0E2D\u0E21\u0E1E\u0E34\u0E27\u0E40\u0E15\
  \u0E2D\u0E23\u0E4C\u2026"
lastmod: '2024-03-17T21:57:55.984188-06:00'
model: gpt-4-0125-preview
summary: "\u0E08\u0E33\u0E19\u0E27\u0E19\u0E40\u0E0A\u0E34\u0E07\u0E0B\u0E49\u0E2D\
  \u0E19\u0E1B\u0E23\u0E30\u0E01\u0E2D\u0E1A\u0E14\u0E49\u0E27\u0E22\u0E2A\u0E48\u0E27\
  \u0E19\u0E08\u0E23\u0E34\u0E07\u0E41\u0E25\u0E30\u0E2A\u0E48\u0E27\u0E19\u0E08\u0E34\
  \u0E19\u0E15\u0E20\u0E32\u0E1E\u0E41\u0E25\u0E30\u0E21\u0E35\u0E04\u0E27\u0E32\u0E21\
  \u0E2A\u0E33\u0E04\u0E31\u0E0D\u0E21\u0E32\u0E01\u0E43\u0E19\u0E2B\u0E25\u0E32\u0E22\
  \u0E2A\u0E32\u0E02\u0E32 \u0E40\u0E0A\u0E48\u0E19 \u0E27\u0E34\u0E28\u0E27\u0E01\
  \u0E23\u0E23\u0E21, \u0E1F\u0E34\u0E2A\u0E34\u0E01\u0E2A\u0E4C \u0E41\u0E25\u0E30\
  \u0E01\u0E23\u0E32\u0E1F\u0E34\u0E01\u0E04\u0E2D\u0E21\u0E1E\u0E34\u0E27\u0E40\u0E15\
  \u0E2D\u0E23\u0E4C \u0E42\u0E1B\u0E23\u0E41\u0E01\u0E23\u0E21\u0E40\u0E21\u0E2D\u0E23\
  \u0E4C\u0E43\u0E0A\u0E49\u0E1E\u0E27\u0E01\u0E21\u0E31\u0E19\u0E40\u0E1E\u0E37\u0E48\
  \u0E2D\u0E41\u0E01\u0E49\u0E2A\u0E21\u0E01\u0E32\u0E23\u0E17\u0E35\u0E48\u0E08\u0E33\
  \u0E19\u0E27\u0E19\u0E08\u0E23\u0E34\u0E07\u0E18\u0E23\u0E23\u0E21\u0E14\u0E32\u0E44\
  \u0E21\u0E48\u0E2A\u0E32\u0E21\u0E32\u0E23\u0E16\u0E08\u0E31\u0E14\u0E01\u0E32\u0E23\
  \u0E44\u0E14\u0E49."
title: "\u0E01\u0E32\u0E23\u0E17\u0E33\u0E07\u0E32\u0E19\u0E01\u0E31\u0E1A\u0E15\u0E31\
  \u0E27\u0E40\u0E25\u0E02\u0E0B\u0E31\u0E1A\u0E0B\u0E49\u0E2D\u0E19"
weight: 14
---

## วิธีการ:
Rust ไม่มีการสนับสนุนจำนวนเชิงซ้อนแบบในตัว แต่ crates เช่น `num-complex` ช่วยคุณได้ นี่คือวิธีการใช้งาน:

```rust
use num_complex::Complex;

fn main() {
    let a = Complex::new(2.0, 3.0); // 2 + 3i
    let b = Complex::new(1.0, -4.0); // 1 - 4i

    let sum = a + b;
    let product = a * b;

    println!("ผลรวม: {}", sum); // ผลรวม: 3 - 1i
    println!("ผลคูณ: {}", product); // ผลคูณ: 14 - 5i
}
```
คุณจำเป็นต้องเพิ่ม `num_complex` ลงใน `Cargo.toml` ของคุณเพื่อให้เกิดมายากลนี้

## ศึกษาลึก
จำนวนเชิงซ้อนถูกคิดค้นขึ้นในศตวรรษที่ 16 แต่จริงๆ แล้วเริ่มเป็นที่นิยมในศตวรรษที่ 18 เมื่อนักคณิตศาสตร์เช่น ยอเลอร์เริ่มเล่นกับพวกมัน

โดยไม่มีการดำเนินการจำนวนเชิงซ้อนแบบในตัว ภาษาเช่น Rust พึ่งพาไลบรารีของบุคคลที่สาม `num-complex` เป็นกระสอบหนึ่งแบบนั้นและเป็นส่วนหนึ่งของชุดกระสอบ `num` ที่มุ่งมั่นให้ประเภทตัวเลขและลักษณะเฉพาะสำหรับ Rust

ควรกล่าวถึงว่าบางภาษา (เช่น Python) มีการสนับสนุนจำนวนเชิงซ้อนแบบในตัว ในขณะที่ภาษาอื่นๆ (เช่น C++ ด้วยหัวข้อ `<complex>`) ให้บริการเป็นส่วนหนึ่งของไลบรารีมาตรฐาน ใน Rust การตัดสินใจที่จะทำให้ไลบรารีมาตรฐานมีขนาดเล็กหมายความว่าคุณจะมักจะเข้าถึงกระสอบที่สร้างโดยชุมชนสำหรับฟังก์ชั่นเพิ่มเติมบ่อยครั้ง

## ดูเพิ่มเติม
- [หนังสือ Rust](https://doc.rust-lang.org/book/): เพื่อเรียนรู้เพิ่มเติมเกี่ยวกับ Rust และวิธีการทำงานกับกระสอบภายนอก
- [วิกิพีเดีย จำนวนเชิงซ้อน](https://en.wikipedia.org/wiki/Complex_number): เพื่อความเข้าใจที่ลึกซึ้งเกี่ยวกับจำนวนเชิงซ้อน
