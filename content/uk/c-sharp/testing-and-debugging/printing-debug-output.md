---
date: 2024-01-20 17:52:18.834576-07:00
description: "Printing debug output \u2013 \u0446\u0435 \u044F\u043A \u0431\u0440\u0430\
  \u0442\u0438 \u043D\u043E\u0442\u0430\u0442\u043A\u0438 \u0432 \u043F\u0440\u043E\
  \u0446\u0435\u0441\u0456 \u043F\u0438\u0441\u044C\u043C\u0430 \u043A\u043E\u0434\
  \u0443, \u0449\u043E\u0431 \u0431\u0430\u0447\u0438\u0442\u0438, \u0449\u043E \u0432\
  \u0456\u0434\u0431\u0443\u0432\u0430\u0454\u0442\u044C\u0441\u044F \u0432 \u0441\
  \u0435\u0440\u0435\u0434\u0438\u043D\u0456 \u043F\u0440\u043E\u0433\u0440\u0430\u043C\
  \u0438. \u041F\u0440\u043E\u0433\u0440\u0430\u043C\u0456\u0441\u0442\u0438 \u0440\
  \u043E\u0431\u043B\u044F\u0442\u044C \u0446\u0435, \u0449\u043E\u0431 \u043B\u0435\
  \u0433\u0448\u0435\u2026"
lastmod: '2024-03-13T22:44:49.293465-06:00'
model: gpt-4-1106-preview
summary: "Printing debug output \u2013 \u0446\u0435 \u044F\u043A \u0431\u0440\u0430\
  \u0442\u0438 \u043D\u043E\u0442\u0430\u0442\u043A\u0438 \u0432 \u043F\u0440\u043E\
  \u0446\u0435\u0441\u0456 \u043F\u0438\u0441\u044C\u043C\u0430 \u043A\u043E\u0434\
  \u0443, \u0449\u043E\u0431 \u0431\u0430\u0447\u0438\u0442\u0438, \u0449\u043E \u0432\
  \u0456\u0434\u0431\u0443\u0432\u0430\u0454\u0442\u044C\u0441\u044F \u0432 \u0441\
  \u0435\u0440\u0435\u0434\u0438\u043D\u0456 \u043F\u0440\u043E\u0433\u0440\u0430\u043C\
  \u0438."
title: "\u0412\u0438\u0432\u0435\u0434\u0435\u043D\u043D\u044F \u043D\u0430\u043B\u0430\
  \u0433\u043E\u0434\u0436\u0443\u0432\u0430\u043B\u044C\u043D\u043E\u0457 \u0456\u043D\
  \u0444\u043E\u0440\u043C\u0430\u0446\u0456\u0457"
weight: 33
---

## How to: (Як це зробити:)
```C#
using System;

class DebugExample
{
    static void Main()
    {
        int a = 5;
        int b = 10;
        int sum = a + b;
        
        // Print to console
        Console.WriteLine("Debug Output: The sum is " + sum);
    }
}
```
Sample output:
```
Debug Output: The sum is 15
```

## Deep Dive (Поглиблений Розбір)
In the early days, debugging was often done using print statements. These statements let you peek inside the flow of your program at specific checkpoints. C# provides `Console.WriteLine()` for printing output to the console, which makes it a basic but powerful tool when debugging.

Alternatives to `Console.WriteLine()` include using advanced debugging tools like Visual Studio Debugger, which allows setting breakpoints, watching variables, inspecting the call stack, etc. Also, there's `Debug.WriteLine()` for output that only appears during debugging and `Trace.WriteLine()` for when you need detailed execution traces in production. These write to listeners and can be configured in the `app.config` file.

Implementation wise, writing debug output can also be managed by various logging frameworks like NLog or log4net. These frameworks offer more control and can direct your logs to different destinations like files, databases, or external monitoring services.

## See Also (Дивіться Також)
- [Microsoft Docs: Debugging in Visual Studio](https://docs.microsoft.com/en-us/visualstudio/debugger/)
- [Microsoft Docs: Trace Listeners](https://docs.microsoft.com/en-us/dotnet/framework/debug-trace-profile/trace-listeners)
- [NLog](https://nlog-project.org/)
- [log4net](http://logging.apache.org/log4net/)
