---
date: 2024-02-01 21:12:05.342598-07:00
description: "Printing debug output involves strategically placing log statements\
  \ in your code to display variable values, execution flow, or message errors during\u2026"
lastmod: '2024-03-13T22:44:59.672355-06:00'
model: gpt-4-0125-preview
summary: Printing debug output involves strategically placing log statements in your
  code to display variable values, execution flow, or message errors during runtime.
title: Printing debug output
weight: 33
---

## How to:
Google Apps Script provides the `Logger` class for basic debugging, and for more advanced needs, the `console` class introduced in the V8 runtime.

**Using Logger:**

The Logger class allows you to log debug messages, which you can view after execution in the Apps Script Editor under `View > Logs`. Here's a simple example:

```javascript
function logSample() {
  var name = "Wired Reader";
  Logger.log("Hello, %s!", name);
}
```

After running `logSample()`, you can view the log with "Hello, Wired Reader!" in the Logs viewer.

**Using console.log with the V8 runtime:**

With the V8 runtime, `console.log` provides a more familiar syntax for developers coming from other languages:

```javascript
function consoleSample() {
  var status = 'active';
  var count = 150;
  console.log(`Current status: ${status}, Count: ${count}`);
}
```

After execution, access the Stackdriver Logging in `View > Stackdriver Logging` to view the output. It's more powerful, supporting string interpolation and object inspection, and integrates with Google Cloud's logging, offering persistent logs and advanced filtering capabilities.

**Sample Output from console.log:**

```
Current status: active, Count: 150
```

## Deep Dive
Initially, `Logger.log` was the primary tool for debugging in Google Apps Script, offering a simple, straightforward way to print output for inspection. However, as scripts become more complex and integrated with Google Cloud Platform services, the need for a more robust logging solution became evident.

Enter the V8 runtime, bringing `console.log` into the fold. This not only aligns Google Apps Script with standard JavaScript syntax, making the language more accessible to developers familiar with JavaScript but also leverages the powerful infrastructure of Google Cloud's logging capabilities. The introduction of `console.log` and its integration with Google Cloud Platform marks a significant evolution in debugging capabilities within Google Apps Script, providing developers with a more dynamic and scalable approach to monitoring and troubleshooting their scripts.

While `Logger.log` is sufficient for basic debugging needs and small projects, `console.log` with the V8 runtime offers a more comprehensive and future-proof solution. This includes the ability to retain logs beyond the execution session, search and filter logs within the Google Cloud console, and the overall alignment with modern JavaScript development practices. However, developers should gauge their needs against the complexity and scale of their projects when choosing between these options.
