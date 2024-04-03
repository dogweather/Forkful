---
date: 2024-02-03 19:02:36.400359-07:00
description: "Checking if a directory exists in Clojure involves verifying the presence\
  \ of a file system directory from within your Clojure application. This task is\u2026"
lastmod: '2024-03-13T22:44:59.758531-06:00'
model: gpt-4-0125-preview
summary: Checking if a directory exists in Clojure involves verifying the presence
  of a file system directory from within your Clojure application.
title: Checking if a directory exists
weight: 20
---

## How to:
Clojure, being a JVM language, can utilize Java's `java.io.File` class for this purpose. You don't need any third-party library for such a basic operation. Here's how you can do it:

```clojure
(import 'java.io.File)

(defn directory-exists? [dir-path]
  (let [dir (File. dir-path)]
    (.exists dir)))

;; Usage example
(println (directory-exists? "/path/to/your/directory")) ;; true or false
```

This function, `directory-exists?`, takes a directory path as a string and returns `true` if the directory exists and `false` otherwise. This is achieved by creating a `File` object with the directory path and then calling the `.exists` method on this object.

In addition to raw Java interop, you can use Clojure libraries that abstract away some of the Java boilerplate. One such library is `clojure.java.io`. However, for checking if a directory exists, you would still use the `File` class, but you might find the library useful for other file operations. Example:

```clojure
(require '[clojure.java.io :as io])

(defn directory-exists?-clojure [dir-path]
  (.exists (io/file dir-path)))

;; Example usage
(println (directory-exists?-clojure "/another/path/to/check")) ;; true or false
```

This version is quite similar but uses the Clojure `io/file` function to create the `File` object. This method blends more naturally into Clojure codebases by leveraging Clojure's library for IO operations, rather than directly interfacing with Java classes.
