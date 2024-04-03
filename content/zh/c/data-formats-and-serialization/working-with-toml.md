---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 18:12:32.717937-07:00
description: "TOML\uFF08Tom's Obvious, Minimal Language\uFF0C\u6C64\u59C6\u7684\u660E\
  \u663E\u3001\u6700\u5C0F\u5316\u8BED\u8A00\uFF09\u662F\u4E00\u79CD\u914D\u7F6E\u6587\
  \u4EF6\u683C\u5F0F\uFF0C\u56E0\u4E3A\u5176\u6E05\u6670\u7684\u8BED\u4E49\u800C\u6613\
  \u4E8E\u9605\u8BFB\u3002\u7A0B\u5E8F\u5458\u5728\u5E94\u7528\u7A0B\u5E8F\u7684\u914D\
  \u7F6E\u6587\u4EF6\u4E2D\u4F7F\u7528\u5B83\uFF0C\u56E0\u4E3A\u5176\u7B80\u5355\u6027\
  \u548C\u6613\u8BFB\u6027\u4F7F\u5176\u5728\u67D0\u4E9B\u60C5\u5883\u4E2D\u6210\u4E3A\
  \u6BD4XML\u6216JSON\u7B49\u683C\u5F0F\u66F4\u4F18\u7684\u9009\u62E9\u3002"
lastmod: '2024-03-13T22:44:48.349114-06:00'
model: gpt-4-0125-preview
summary: "TOML\uFF08Tom's Obvious, Minimal Language\uFF0C\u6C64\u59C6\u7684\u660E\u663E\
  \u3001\u6700\u5C0F\u5316\u8BED\u8A00\uFF09\u662F\u4E00\u79CD\u914D\u7F6E\u6587\u4EF6\
  \u683C\u5F0F\uFF0C\u56E0\u4E3A\u5176\u6E05\u6670\u7684\u8BED\u4E49\u800C\u6613\u4E8E\
  \u9605\u8BFB\u3002\u7A0B\u5E8F\u5458\u5728\u5E94\u7528\u7A0B\u5E8F\u7684\u914D\u7F6E\
  \u6587\u4EF6\u4E2D\u4F7F\u7528\u5B83\uFF0C\u56E0\u4E3A\u5176\u7B80\u5355\u6027\u548C\
  \u6613\u8BFB\u6027\u4F7F\u5176\u5728\u67D0\u4E9B\u60C5\u5883\u4E2D\u6210\u4E3A\u6BD4\
  XML\u6216JSON\u7B49\u683C\u5F0F\u66F4\u4F18\u7684\u9009\u62E9\u3002."
title: "\u4F7F\u7528TOML\u8FDB\u884C\u5DE5\u4F5C"
weight: 39
---

## 如何操作：
要在C语言中使用TOML，首先需要一个能够解析TOML文件的库，因为C标准库中不包含这项功能。一个流行的选择是`tomlc99`，它是一个针对C99的轻量级TOML解析器。以下是读取一个简单TOML配置文件的快速指南：

首先，确保已在项目中安装并正确链接了`tomlc99`。

**示例 TOML 文件（`config.toml`）：**
```toml
[database]
server = "192.168.1.1"
ports = [ 8001, 8001, 8002 ]
connection_max = 5000
enabled = true
```

**解析此文件的C代码：**

```c
#include <stdio.h>
#include <stdlib.h>
#include "toml.h"

int main() {
    FILE *configFile;
    configFile = fopen("config.toml", "r");
    if (!configFile) {
        perror("无法打开文件");
        return EXIT_FAILURE;
    }

    toml_table_t *config = toml_parse_file(configFile, NULL, 0);
    if (!config) {
        fprintf(stderr, "文件解析错误\n");
        fclose(configFile);
        return EXIT_FAILURE;
    }

    toml_table_t *database = toml_table_in(config, "database");
    if (database) {
        const char *server = toml_raw_in(database, "server");
        printf("数据库服务器：%s\n", server);

        toml_array_t *ports = toml_array_in(database, "ports");
        for (int i = 0; i < toml_array_nelem(ports); i++) {
            int64_t port;
            toml_int_at(ports, i, &port);
            printf("端口 %d：%ld\n", i, port);
        }
    }

    toml_free(config);
    fclose(configFile);
    return EXIT_SUCCESS;
}
```

**输出：**
```
数据库服务器："192.168.1.1"
端口 0：8001
端口 1：8001
端口 2：8002
```

## 深入了解
TOML由GitHub的联合创始人Tom Preston-Werner创建，作为对他在其他配置文件格式中感知到的限制的回应。其目标是直白无歧义，对人和电脑来说，读写都不需要复杂的解析规则。在C生态系统中，TOML并不像在高级语言中那样是一等公民，比如Rust中的`serde_toml`或Python中的`toml`，这些语言拥有原生支持的库。相反，C开发者需要依赖像`tomlc99`这样的外部库，但鉴于C语言强调的极简主义和性能，这是典型的。

尽管TOML因其清晰而受到赞扬，在选择配置文件格式时，考虑项目的需求至关重要。在需要更复杂结构或与Web API交互的场景中，尽管它们的复杂性增加了，JSON或甚至YAML可能提供更好的适配。TOML在需要可读性和简单性的配置中脱颖而出，并不一定是在需要最高级数据结构的情况下。
