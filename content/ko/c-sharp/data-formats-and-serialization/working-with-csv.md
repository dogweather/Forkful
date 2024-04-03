---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:19:14.640446-07:00
description: "CSV(\uC27C\uD45C\uB85C \uAD6C\uBD84\uB41C \uAC12) \uD30C\uC77C\uC740\
  \ \uD45C \uD615\uC2DD \uB370\uC774\uD130\uB97C \uC77C\uBC18 \uD14D\uC2A4\uD2B8\uB85C\
  \ \uB098\uD0C0\uB0B4\uBA70, \uAC1C\uBCC4 \uAC12\uC744 \uAD6C\uBD84\uD558\uAE30 \uC704\
  \uD574 \uC27C\uD45C\uB97C \uC0AC\uC6A9\uD558\uB294 \uC77C\uBC18\uC801\uC778 \uB370\
  \uC774\uD130 \uAD50\uD658 \uD615\uC2DD\uC785\uB2C8\uB2E4. \uD504\uB85C\uADF8\uB798\
  \uBA38\uB4E4\uC740 \uC774\uB97C \uD1B5\uD574 \uB2E4\uC591\uD55C \uC751\uC6A9 \uD504\
  \uB85C\uADF8\uB7A8 \uBC0F \uC11C\uBE44\uC2A4\uC5D0\uC11C \uB370\uC774\uD130\uB97C\
  \ \uC27D\uAC8C \uAC00\uC838\uC624\uAE30, \uB0B4\uBCF4\uB0B4\uAE30 \uBC0F \uC870\uC791\
  \uD558\uAE30 \uC704\uD574 CSV\u2026"
lastmod: '2024-03-13T22:44:55.267734-06:00'
model: gpt-4-0125-preview
summary: "CSV(\uC27C\uD45C\uB85C \uAD6C\uBD84\uB41C \uAC12) \uD30C\uC77C\uC740 \uD45C\
  \ \uD615\uC2DD \uB370\uC774\uD130\uB97C \uC77C\uBC18 \uD14D\uC2A4\uD2B8\uB85C \uB098\
  \uD0C0\uB0B4\uBA70, \uAC1C\uBCC4 \uAC12\uC744 \uAD6C\uBD84\uD558\uAE30 \uC704\uD574\
  \ \uC27C\uD45C\uB97C \uC0AC\uC6A9\uD558\uB294 \uC77C\uBC18\uC801\uC778 \uB370\uC774\
  \uD130 \uAD50\uD658 \uD615\uC2DD\uC785\uB2C8\uB2E4."
title: "CSV\uC640 \uD568\uAED8 \uC791\uC5C5\uD558\uAE30"
weight: 37
---

## 사용 방법:
C#에서 CSV 파일을 작업하는 것은 기본 작업을 위해 `System.IO` 네임스페이스를 통해, 그리고 더 복잡한 조작을 하거나 큰 파일을 원활하게 처리하기 위해서는 `CsvHelper`와 같은 타사 라이브러리를 고려할 수 있습니다. 다음은 이러한 접근 방식을 사용하여 CSV 파일을 읽고 쓰는 방법의 예시입니다.

### System.IO를 사용하여 CSV 파일 읽기
```csharp
using System;
using System.IO;

class ReadCSV
{
    static void Main()
    {
        string filePath = @"path\to\your\file.csv";
        // CSV 파일의 모든 줄을 읽기
        string[] csvLines = File.ReadAllLines(filePath);
        
        foreach (string line in csvLines)
        {
            string[] rowData = line.Split(',');
            Console.WriteLine($"첫 번째 열: {rowData[0]}, 두 번째 열: {rowData[1]}");
        }
    }
}
```

**샘플 출력:**
```
첫 번째 열: 이름, 두 번째 열: 나이
첫 번째 열: John Doe, 두 번째 열: 30
```

### System.IO를 사용하여 CSV 파일 쓰기
```csharp
using System;
using System.Collections.Generic;
using System.IO;

class WriteCSV
{
    static void Main()
    {
        string filePath = @"path\to\your\output.csv";
        var lines = new List<string>
        {
            "이름,나이",
            "John Doe,30",
            "Jane Smith,25"
        };
        
        File.WriteAllLines(filePath, lines);
        Console.WriteLine("CSV 파일이 작성되었습니다.");
    }
}
```

**샘플 출력:**
```
CSV 파일이 작성되었습니다.
```

### CsvHelper를 사용하여 CSV 읽기
CsvHelper를 사용하려면, 먼저 NuGet 패키지 관리자를 사용하여 프로젝트에 `CsvHelper` 패키지를 추가합니다.

```csharp
using CsvHelper;
using System.Globalization;
using System.IO;
using System.Linq;
using CsvHelper.Configuration;

class ReadCSVWithCsvHelper
{
    static void Main()
    {
        string filePath = @"path\to\your\file.csv";

        using (var reader = new StreamReader(filePath))
        using (var csv = new CsvReader(reader, CultureInfo.InvariantCulture))
        {
            var records = csv.GetRecords<dynamic>().ToList();
            foreach (var record in records)
            {
                Console.WriteLine($"첫 번째 열: {record.Name}, 두 번째 열: {record.Age}");
            }
        }
    }
}
```

**샘플 출력:**
```
첫 번째 열: John Doe, 두 번째 열: 30
첫 번째 열: Jane Smith, 두 번째 열: 25
```

### CsvHelper를 사용하여 CSV 쓰기
```csharp
using CsvHelper;
using System.Globalization;
using System.IO;
using System.Collections.Generic;
using CsvHelper.Configuration;

class WriteCSVWithCsvHelper
{
    public class Person
    {
        public string Name { get; set; }
        public int Age { get; set; }
    }

    static void Main()
    {
        string filePath = @"path\to\your\output.csv";
        var records = new List<Person>
        {
            new Person { Name = "John Doe", Age = 30 },
            new Person { Name = "Jane Smith", Age = 25 }
        };

        using (var writer = new StreamWriter(filePath))
        using (var csv = new CsvWriter(writer, CultureInfo.InvariantCulture))
        {
            csv.WriteRecords(records);
        }
        
        Console.WriteLine("CsvHelper로 CSV 파일이 작성되었습니다.");
    }
}
```

**샘플 출력:**
```
CsvHelper로 CSV 파일이 작성되었습니다.
```
