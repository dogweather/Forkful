---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:24:42.552560-07:00
description: "JSON\uFF08JavaScript Object\u2026"
lastmod: '2024-03-13T22:44:41.789132-06:00'
model: gpt-4-0125-preview
summary: "JSON\uFF08JavaScript Object Notation\uFF09\u3092\u4F7F\u3046\u4F5C\u696D\
  \u306F\u3001JSON\u30C7\u30FC\u30BF\u3092TypeScript\u3067\u6271\u3048\u308B\u5F62\
  \u5F0F\u306B\u89E3\u6790\u3057\u305F\u308A\u3001\u305D\u306E\u9006\u3092\u3057\u305F\
  \u308A\u3059\u308B\u3053\u3068\u3092\u542B\u307F\u307E\u3059\u3002\u30D7\u30ED\u30B0\
  \u30E9\u30DE\u30FC\u306F\u3053\u308C\u3092\u884C\u3046\u3053\u3068\u3067\u3001\u69CB\
  \u9020\u5316\u3055\u308C\u305F\u30C7\u30FC\u30BF\u3092\u7C21\u5358\u306B\u64CD\u4F5C\
  \u3001\u4FDD\u5B58\u3001\u307E\u305F\u306F\u9001\u4FE1\u3067\u304D\u307E\u3059\u3002\
  \u306A\u305C\u306A\u3089\u3001JSON\u306F\u8EFD\u91CF\u3067\u3001\u30C6\u30AD\u30B9\
  \u30C8\u30D9\u30FC\u30B9\u3067\u3042\u308A\u3001\u4EBA\u9593\u3068\u6A5F\u68B0\u306E\
  \u4E21\u65B9\u306B\u3068\u3063\u3066\u8AAD\u307F\u3084\u3059\u3044\u304B\u3089\u3067\
  \u3059\u3002."
title: "JSON\u3092\u6D3B\u7528\u3059\u308B"
weight: 38
---

## 方法：


### JSONをTypeScriptオブジェクトに解析する
JSON文字列をTypeScriptオブジェクトに変換するには、`JSON.parse()`メソッドを使用します。これは、WebサーバーからJSONデータを受信したり、JSONファイルを読み込んだりするときに役立ちます。

```typescript
const jsonStr = '{"name": "John Doe", "age": 30}';
const obj = JSON.parse(jsonStr);

console.log(obj.name); // 出力：John Doe
```

### TypeScriptオブジェクトをJSONに文字列化する
TypeScriptオブジェクトをJSON文字列に変換するには、`JSON.stringify()`メソッドを使用します。これは、データをWebサーバーに送信する必要があるときに特に便利です。

```typescript
const person = {
  name: "Jane Doe",
  age: 25,
};

const jsonStr = JSON.stringify(person);

console.log(jsonStr); // 出力：{"name":"Jane Doe","age":25}
```

### インターフェースの利用
TypeScriptのインターフェースを定義して、オブジェクトの構造を保証することで、JSONデータとシームレスに作業できます。

```typescript
interface Person {
  name: string;
  age: number;
}

const jsonStr = '{"name": "Alex", "age": 28}';
const person: Person = JSON.parse(jsonStr);

console.log(person.age); // 出力：28
```

### 人気のあるサードパーティ製ライブラリの使用
スキーマ検証や変換など、より複雑なシナリオの場合、`class-transformer`や`AJV`（Another JSON Schema Validator）などのライブラリを利用することがあります。

#### class-transformer
このライブラリを使うと、プレーンオブジェクトをクラスインスタンスに変換したり、その逆をしたりできます。これは、型チェックや操作に役立ちます。

```typescript
import "reflect-metadata";
import { plainToClass } from "class-transformer";
import { Person } from "./person";

const jsonStr = '{"name": "Mia", "age": 22}';
const person = plainToClass(Person, JSON.parse(jsonStr));

console.log(person instanceof Person); // 出力：true
console.log(person.name); // 出力：Mia
```

#### AJV
AJVは、高速なJSONスキーマ検証を可能にするライブラリです。これは、事前に定義されたスキーマに対してJSONオブジェクトを検証できることを意味します。

```typescript
import Ajv from "ajv";

const ajv = new Ajv();

const schema = {
  type: "object",
  properties: {
    name: { type: "string" },
    age: { type: "number" },
  },
  required: ["name", "age"],
  additionalProperties: false,
};

const validate = ajv.compile(schema);
const valid = validate({ name: "Tom", age: 24 });

console.log(valid); // 出力：true
if (!valid) console.log(validate.errors);
```

これらのツールとテクニックを利用することで、TypeScriptアプリケーションで効率的にJSONデータを扱うことができ、データの整合性を保ちながらTypeScriptの強力な型システムを活用できます。
