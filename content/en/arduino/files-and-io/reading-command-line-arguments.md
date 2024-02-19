---
aliases:
- /en/arduino/reading-command-line-arguments/
date: 2024-01-20 17:55:35.017411-07:00
description: "Reading command line arguments means grabbing the data passed to a program\
  \ when you start it from a terminal or command prompt. Programmers use arguments\u2026"
lastmod: 2024-02-18 23:09:11.330206
model: gpt-4-1106-preview
summary: "Reading command line arguments means grabbing the data passed to a program\
  \ when you start it from a terminal or command prompt. Programmers use arguments\u2026"
title: Reading command line arguments
---

{{< edit_this_page >}}

## What & Why?
Reading command line arguments means grabbing the data passed to a program when you start it from a terminal or command prompt. Programmers use arguments to customize a program's behavior without changing the code.

## How to:
Arduino doesn't do command line arguments like traditional programming environments, because sketches are uploaded to microcontrollers without an accessible OS command line. But you can mimic this feature using serial communication. Here's how:

```arduino
void setup() {
  // Initialize serial communication at 9600 bits per second:
  Serial.begin(9600);
}

void loop() {
  // Check if data is available to read.
  if (Serial.available() > 0) {
    // Read the incoming bytes until a newline is received.
    String receivedData = Serial.readStringUntil('\n');
    // Echo the received arguments back to the serial monitor.
    Serial.print("Received: ");
    Serial.println(receivedData);
  }
}
```

Sample Serial Monitor Output:
```
Received: argument1 argument2 argument3
```

## Deep Dive
Traditional command line arguments work where a full-fledged operating system (like Windows, Linux, or macOS) runs programs. The OS's command processor passes arguments to programs. Arduino doesn't have this; it's a microcontroller with a single program running repeatedly.

Serial communication is your workaround. It's like having a chat with your Arduino over a dedicated line. You send data over this line, which the Arduino program reads as input when it's ready.

Before the Serial Monitor in the Arduino IDE, programmers used physical switches or jumpers on the hardware to alter behavior. Serial communication was a game changer, simplifying this process massively.

Remember, Arduino Uno and many others have only one serial port shared with the USB connection, meaning you can't get serial data and upload a new sketch simultaneously. More advanced Arduino boards can have multiple serial ports, allowing simultaneous communication and sketch uploading.

Alternatives to serial communication for mimicking command line arguments include:

- Bluetooth modules (for wireless communication).
- Keypads or buttons for input.
- Saving arguments to EEPROM (non-volatile memory) and reading them on startup.

Each method has its use-case and complexity level, but serial is the simplest for quick prototyping and testing.

## See Also
- Arduino Serial Communication: [Arduino - Serial](https://www.arduino.cc/reference/en/language/functions/communication/serial/)
- Arduino EEPROM Reading and Writing: [Arduino - EEPROM](https://www.arduino.cc/en/Reference/EEPROM)
