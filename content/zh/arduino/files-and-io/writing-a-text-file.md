---
title:                "编写文本文件"
date:                  2024-02-03T19:26:53.550265-07:00
model:                 gpt-4-0125-preview
simple_title:         "编写文本文件"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/zh/arduino/writing-a-text-file.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## 什么和为什么？
在Arduino中写入文本文件涉及到在SD卡或类似存储模块上保存数据，通常用于数据记录目的。程序员这样做是为了记录传感器读数、保存配置或随时间记录应用事件，这对于需要数据分析或跟踪的项目至关重要。

## 如何操作：
要使用Arduino在SD卡上写入文本文件，你首先需要包含`SD.h`库，该库提供与SD卡交互所需的函数。确保你的Arduino板连接到了SD卡模块。

```cpp
#include <SPI.h>
#include <SD.h>

File myFile;

void setup() {
  // 以每秒9600位的速度初始化串行通信：
  Serial.begin(9600);
  
  // 检查SD卡初始化
  if (!SD.begin(4)) {
    Serial.println("初始化失败！");
    return;
  }
  Serial.println("初始化完成。");
  
  // 打开文件。注意，每次只能打开一个文件，
  // 所以在打开另一个之前你必须关闭这个。
  myFile = SD.open("test.txt", FILE_WRITE);
  
  // 如果文件成功打开，写入它：
  if (myFile) {
    Serial.print("正在写入test.txt...");
    myFile.println("测试文本文件写入。");
    // 关闭文件：
    myFile.close();
    Serial.println("完成。");
  } else {
    // 如果文件没打开，打印一个错误：
    Serial.println("打开test.txt失败");
  }
}

void loop() {
  // setup之后不会发生任何事情
}
```

### 样本输出：
当你运行这段代码时，Arduino IDE串行监视器将显示：
```
初始化完成。
正在写入test.txt...完成。
```
要检查数据是否正确写入，你可以从Arduino中拿出SD卡，插入电脑，并打开`test.txt`文件查看消息"测试文本文件写入。"

对于需要更高级文件操作或处理的项目，考虑探索额外的库或编写定制函数以满足你的特定需求。
