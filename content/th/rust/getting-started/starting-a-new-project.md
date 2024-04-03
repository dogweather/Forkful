---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 21:51:45.923442-06:00
description: "\u0E01\u0E32\u0E23\u0E40\u0E23\u0E34\u0E48\u0E21\u0E15\u0E49\u0E19\u0E42\
  \u0E1B\u0E23\u0E40\u0E08\u0E47\u0E01\u0E15\u0E4C\u0E43\u0E2B\u0E21\u0E48\u0E14\u0E49\
  \u0E27\u0E22 Rust \u0E2B\u0E21\u0E32\u0E22\u0E16\u0E36\u0E07\u0E01\u0E32\u0E23\u0E15\
  \u0E31\u0E49\u0E07\u0E04\u0E48\u0E32\u0E42\u0E04\u0E23\u0E07\u0E2A\u0E23\u0E49\u0E32\
  \u0E07\u0E1E\u0E37\u0E49\u0E19\u0E10\u0E32\u0E19\u0E40\u0E1E\u0E37\u0E48\u0E2D\u0E43\
  \u0E2B\u0E49\u0E42\u0E04\u0E49\u0E14\u0E02\u0E2D\u0E07\u0E04\u0E38\u0E13\u0E21\u0E35\
  \u0E17\u0E35\u0E48\u0E2D\u0E22\u0E39\u0E48. \u0E42\u0E1B\u0E23\u0E41\u0E01\u0E23\
  \u0E21\u0E40\u0E21\u0E2D\u0E23\u0E4C\u0E40\u0E23\u0E34\u0E48\u0E21\u0E15\u0E49\u0E19\
  \u0E42\u0E1B\u0E23\u0E40\u0E08\u0E47\u0E01\u0E15\u0E4C\u0E43\u0E2B\u0E21\u0E48\u0E40\
  \u0E1E\u0E37\u0E48\u0E2D\u0E41\u0E01\u0E49\u0E1B\u0E31\u0E0D\u0E2B\u0E32, \u0E40\
  \u0E23\u0E35\u0E22\u0E19\u0E23\u0E39\u0E49,\u2026"
lastmod: '2024-03-17T21:57:55.993473-06:00'
model: gpt-4-0125-preview
summary: "\u0E01\u0E32\u0E23\u0E40\u0E23\u0E34\u0E48\u0E21\u0E15\u0E49\u0E19\u0E42\
  \u0E1B\u0E23\u0E40\u0E08\u0E47\u0E01\u0E15\u0E4C\u0E43\u0E2B\u0E21\u0E48\u0E14\u0E49\
  \u0E27\u0E22 Rust \u0E2B\u0E21\u0E32\u0E22\u0E16\u0E36\u0E07\u0E01\u0E32\u0E23\u0E15\
  \u0E31\u0E49\u0E07\u0E04\u0E48\u0E32\u0E42\u0E04\u0E23\u0E07\u0E2A\u0E23\u0E49\u0E32\
  \u0E07\u0E1E\u0E37\u0E49\u0E19\u0E10\u0E32\u0E19\u0E40\u0E1E\u0E37\u0E48\u0E2D\u0E43\
  \u0E2B\u0E49\u0E42\u0E04\u0E49\u0E14\u0E02\u0E2D\u0E07\u0E04\u0E38\u0E13\u0E21\u0E35\
  \u0E17\u0E35\u0E48\u0E2D\u0E22\u0E39\u0E48."
title: "\u0E40\u0E23\u0E34\u0E48\u0E21\u0E15\u0E49\u0E19\u0E42\u0E04\u0E23\u0E07\u0E01\
  \u0E32\u0E23\u0E43\u0E2B\u0E21\u0E48"
weight: 1
---

## วิธีการ:
เพื่อเริ่มต้นโปรเจ็กต์ใหม่ด้วย Rust, คุณต้องการ Cargo—ตัวจัดการแพ็คเกจของ Rust ติดตั้ง Rust และ Cargo ผ่านตัวติดตั้งทางการ, rustup.

```sh
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

หลังจากนั้น, เพียงคำสั่งง่ายๆ เพื่อสร้างโปรเจ็กต์ใหม่:

```sh
cargo new my_project
```

คำสั่งนี้จะสร้างโฟลเดอร์ใหม่ที่ชื่อว่า 'my_project' พร้อมไฟล์ที่จำเป็นทั้งหมด:

- `Cargo.toml`: ไฟล์กำกับโปรเจ็กต์ของคุณพร้อมข้อมูลเมตาดาต้าและการพึ่งพา.
- `src`: โฟลเดอร์ที่ไฟล์ต้นฉบับของคุณอยู่.
- `main.rs`: จุดเริ่มต้นหลักสำหรับโปรแกรมของคุณ.

นี่คือรูปลักษณ์ง่ายๆ ของ `main.rs` หลังจากการสร้าง:

```rust
fn main() {
    println!("Hello, world!");
}
```

เพื่อคอมไพล์และรันโปรเจ็กต์ของคุณ:

```sh
cd my_project
cargo run
```

และเหมือนกับการใช้เวทมนตร์, คุณจะเห็นผลลัพธ์:

```
   Compiling my_project v0.1.0 (path/to/my_project)
    Finished dev [unoptimized + debuginfo] target(s) in 0.0 secs
     Running `target/debug/my_project`
Hello, world!
```

## ลงรายละเอียด
Rust มีตัวจัดการแพ็คเกจและระบบสร้างสิ่งของของตัวเอง, Cargo, ตั้งแต่ช่วงเริ่มแรก. สร้างขึ้นประมาณปี 2013, นี่คือวิธีของ Rust ในการจัดการโปรเจ็กต์, การพึ่งพา, และการสร้างสิ่งของ.

ทำไม Cargo ถึงดีสำหรับการเริ่มต้นโปรเจ็กต์ใหม่?

- **ความสอดคล้อง**: มันสร้างโครงสร้างโปรเจ็กต์ตามมาตรฐาน.
- **การพึ่งพา**: มันจัดการกับไลบรารีภายนอกได้อย่างง่ายดาย.
- **การคอมไพล์**: มันคอมไพล์โค้ดของคุณ, ใช้ประโยชน์จากคุณสมบัติความปลอดภัยและประสิทธิภาพของ Rust.

ภาษาอื่นๆ ใช้เครื่องมือที่แตกต่างกัน—Node.js มี npm, Ruby มี Bundler, และ Python มี Pip. Cargo เป็นคำตอบของ Rust ต่อเครื่องมือเหล่านี้และอาจทำได้มากกว่าจากกล่องโดยการรวมระบบสร้างเข้ากับตัวเอง, ซึ่งเครื่องมืออื่นๆ มักจะมอบหมายให้เครื่องมือแยกต่างหาก, เช่น Grunt หรือ Webpack ในระบบนิเวศของ JavaScript.

ทางเลือกในการเริ่มต้นโปรเจ็กต์ด้วย Rust? คุณอาจสร้างทุกอย่างด้วยตนเองหรือใช้ IDEs, แต่ทำไมต้องคิดใหม่เมื่อ Cargo ทำงานหนักให้?

## ดูเพิ่มเติม
- หนังสือ The Rust Programming Language: https://doc.rust-lang.org/book/
- คู่มือการติดตั้ง Rust และ Cargo: https://www.rust-lang.org/tools/install
- เอกสารของ Cargo: https://doc.rust-lang.org/cargo/
