---
date: 2024-01-25 02:03:41.790707-07:00
description: "Logging is the process of recording application events while a program\
  \ runs, providing a breadcrumb trail for post-mortem analysis and real-time\u2026"
lastmod: '2024-03-13T22:44:59.713890-06:00'
model: gpt-4-1106-preview
summary: Logging is the process of recording application events while a program runs,
  providing a breadcrumb trail for post-mortem analysis and real-time monitoring.
title: Logging
weight: 17
---

## How to:
Python comes with a built-in module for logging. Here's a basic setup:
```Python
import logging

# Basic configuration of the logging
logging.basicConfig(level=logging.INFO)

# Logging messages
logging.debug('This is a debug message')
logging.info('Info about what your program just did')
logging.warning('A warning message')
logging.error('An error has occurred')
logging.critical('The program is unable to recover!')
```
When you run this code, you'll see the following output (since the default level is WARNING, debug and info messages will not be shown):
```
WARNING:root:A warning message
ERROR:root:An error has occurred
CRITICAL:root:The program is unable to recover!
```
You can also set up logging to write to a file instead of the console:
```Python
logging.basicConfig(filename='app.log', filemode='w', level=logging.INFO)
```
Now your logs will be directed to 'app.log' file.

## Deep Dive
Logging has been around since the early days of programming, with system logs being one of the oldest forms of persistent storage outside of actual files holding data. History aside, the main concept of logging remains essentially unchanged, though the tools have evolved.

Python's `logging` module is quite powerful and flexible. It allows programmers to set different log levels (DEBUG, INFO, WARNING, ERROR, CRITICAL) that can help in categorizing and filtering logs. It has a hierarchical logger system, meaning you can have parent-child relationships between loggers and propagate messages up the chain.

Alternatives include third-party libraries like Loguru or structlog which offer enhanced features and a simpler interface than the built-in logging module. They can provide prettier output, better serialization of structured data, and more intuitive ways to deal with log configuration.

Regarding implementation, when setting up logging it's important to do it once at the start of your application. Configuring it in a module-level is recommended using `logging.getLogger(__name__)` to follow the Python logging best practices.

Logging shouldn't drastically affect the performance of an application under normal circumstances. However, care should be taken with what is logged: overly verbose logging, especially at DEBUG levels, can slow down an application and quickly fill up log file storage.

## See Also
For more on Python's logging module, check out the official Python logging cookbook for some great examples and best practices: https://docs.python.org/3/howto/logging-cookbook.html

For an in-depth look at structured logging and how it can help make logs more informative and easier to analyze, Loguru is well-documented: https://loguru.readthedocs.io

Also, consider peeking at the 12-factor app methodology, specifically the section on logs for the modern view on app logging: https://12factor.net/logs
