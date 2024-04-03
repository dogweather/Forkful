---
date: 2024-03-08 21:33:32.467377-07:00
description: "Converting a date into a string in Dart is a common task when you need\
  \ to display date and time information in a human-readable format, or when you intend\u2026"
lastmod: '2024-03-13T22:44:59.830777-06:00'
model: gpt-4-0125-preview
summary: Converting a date into a string in Dart is a common task when you need to
  display date and time information in a human-readable format, or when you intend
  to serialize data for storage or transmission.
title: Converting a date into a string
weight: 28
---

## How to:
Dart provides the `DateTime` class for handling dates and times, and the `intl` package for formatting. First, ensure you have the `intl` package by adding `intl: ^0.17.0` (or the latest version) to your `pubspec.yaml` file.

### Using Dart's Core Library
```dart
DateTime now = DateTime.now();
String formattedDate = "${now.year}-${now.month}-${now.day}";
print(formattedDate); // Output: 2023-4-12 (for example, this depends on the current date)
```

This example directly constructs a string from the `DateTime`'s properties.

### Using `intl` package
First, import the package:

```dart
import 'package:intl/intl.dart';
```

Then, format the date:

```dart
DateTime now = DateTime.now();
String formattedDate = DateFormat('yyyy-MM-dd').format(now);
print(formattedDate); // Output: 2023-04-12
```

The `intl` package allows for much more complex formatting easily, including locale-specific formats:

```dart
String formattedDateLocale = DateFormat.yMMMMd('en_US').format(now);
print(formattedDateLocale); // Output: April 12, 2023
```

These examples show simple but powerful ways to convert and format dates into strings in Dart, either using Dart's core functionality or utilizing the `intl` package for more advanced formatting options.
