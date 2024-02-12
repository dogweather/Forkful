---
title:                "处理CSV文件"
aliases:
- zh/google-apps-script/working-with-csv.md
date:                  2024-02-01T22:05:04.727161-07:00
model:                 gpt-4-0125-preview
simple_title:         "处理CSV文件"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/zh/google-apps-script/working-with-csv.md"
changelog:
  - 2024-02-01, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## 什么 & 为什么？

在Google Apps Script中处理CSV（逗号分隔值）文件涉及读取、修改和写入纯文本文件，其中每行代表一个数据记录，值之间通过逗号分隔。程序员之所以这样做，是因为便于在不同的应用程序、数据库或编程语言之间轻松交换数据，由于CSV作为一种简单的基于文本的数据交换格式，已被广泛采用。

## 如何操作：

### 读取CSV数据

要从存储在Google Drive中的文件读取CSV数据，您首先需要将文件的内容作为字符串获取，然后解析它。Google Apps Script通过DriveApp服务使获取文件内容变得简单。

```javascript
function readCSV() {
  var fileId = 'YOUR_FILE_ID_HERE'; // 替换为实际的文件ID
  var file = DriveApp.getFileById(fileId);
  var content = file.getBlob().getDataAsString();
  var rows = content.split("\n");
  
  for (var i = 0; i < rows.length; i++) {
    var cells = rows[i].split(",");
    Logger.log(cells); // 记录每行的单元格
  }
}
```

### 写入CSV数据

创建并写入CSV包括构建一个带有逗号分隔值和换行符的字符串，然后保存或导出它。这个例子展示了在Google Drive中创建一个新的CSV文件。

```javascript
function writeCSV() {
  var folderId = 'YOUR_FOLDER_ID_HERE'; // 替换为新文件将要创建的Drive文件夹的ID
  var csvContent = "Name,Age,Occupation\nJohn Doe,29,Engineer\nJane Smith,34,Designer";
  var fileName = "example.csv";
  
  var folder = DriveApp.getFolderById(folderId);
  folder.createFile(fileName, csvContent, MimeType.PLAIN_TEXT);
}
```

### 样本输出

当从读取CSV记录行单元格时：

```plaintext
[John, 29, Engineer]
[Jane, 34, Designer]
```

写入时，创建一个名为"example.csv"的文件，内容为：

```plaintext
Name,Age,Occupation
John Doe,29,Engineer
Jane Smith,34,Designer
```

## 深入了解

历史上，由于其简单性和人类可读性，CSV文件一直受到青睐，使它们对非程序员友好且对快速数据检查任务有用。然而，Google Apps Script操作在Google的生态系统内，其中Google Sheets充当了一个强大且用户友好的CSV操作替代品。Sheets不仅提供了一个GUI用于编辑数据，还支持复杂的公式、样式和许多原生CSV所缺乏的更多功能。

尽管Google Sheets提供了优势，但在Google Apps Script中直接操作CSV对于自动化任务仍然重要，特别是在处理生成或需要CSV格式数据的外部系统时。例如，与遗留系统集成、将数据导出以用于其他应用程序，或在将数据输入Google Sheets之前进行预处理。

此外，Google Apps Script处理CSV文件的能力可以通过Utilities服务扩展以满足高级编码需求，或与外部APIs接口以进行转换、解析或验证任务。然而，对于处理大型数据集或需要复杂操作的情况，考虑使用Google Sheets API或探索BigQuery以获得更强大的数据处理能力。

尽管简单性仍然是CSV流行的关键原因，这些替代方案为在广阔的Google Cloud生态系统中处理数据提供了更丰富的功能集。
