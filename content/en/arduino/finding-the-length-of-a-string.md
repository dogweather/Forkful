---
title:                "Finding the length of a string"
aliases:
- en/arduino/finding-the-length-of-a-string.md
date:                  2024-01-20T17:46:49.936306-07:00
model:                 gpt-4-1106-preview
simple_title:         "Finding the length of a string"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/en/arduino/finding-the-length-of-a-string.md"
---

{{< edit_this_page >}}

## What & Why?
Finding the length of a string means figuring out how many characters it contains. Programmers do it to validate input, loop through characters, align text, or manage data dynamically.

## How to:
```Arduino
void setup() {
  Serial.begin(9600); // Start the serial communication
  String myString = "Hello, Arduino!"; // Your string here
  int stringLength = myString.length(); // Finding the length of the string
  Serial.print("The length of the string is: ");
  Serial.println(stringLength); // Outputs the length
}

void loop() {
  // Nothing to do here.
}
```
Sample Output:
```
The length of the string is: 15
```

## Deep Dive
Back in the day, C programmers used the `strlen()` function from `<string.h>`, counting characters until a null-terminator. In Arduino's world, the `String` class makes life easier with its built-in `length()` method. But remember, using `String` objects can fragment your device's limited memory over time. An alternative? Use char arrays (C-style strings), which are more memory-friendly but trickier to handle.

For larger projects, always consider memory management. With the `length()` method, no extra computing is needed—the `String` object keeps track of its size. Internally, `length()` is a quick look-up, not a character count. That's efficient! But, if you're low on memory, go back to basics with char arrays and manual length calculations, just like the good ol’`strlen()` days.

## See Also
- Arduino `String` Reference: https://www.arduino.cc/reference/en/language/variables/data-types/stringobject/
- Arduino `strlen()` function for C-style strings: https://www.arduino.cc/reference/en/language/variables/data-types/string/functions/strlen/
- Discussion on `String` vs. char array in Arduino: https://forum.arduino.cc/t/string-vs-char-array/678207
