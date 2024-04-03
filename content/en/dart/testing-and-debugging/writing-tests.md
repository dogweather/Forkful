---
date: 2024-03-08 21:33:44.626135-07:00
description: "Writing tests in Dart involves creating test cases to automatically\
  \ verify that different parts of your program work as expected. Programmers do this\
  \ to\u2026"
lastmod: '2024-03-13T22:44:59.823981-06:00'
model: gpt-4-0125-preview
summary: Writing tests in Dart involves creating test cases to automatically verify
  that different parts of your program work as expected.
title: Writing tests
weight: 36
---

## How to:
In Dart, the `test` package is commonly used for writing tests. First, add the `test` package to your `pubspec.yaml`:

```yaml
dev_dependencies:
  test: ^1.0.0
```

Then, write a test for a simple function. Suppose you have a function that adds two numbers:

```dart
int add(int a, int b) {
  return a + b;
}
```

Next, create a file named `add_test.dart` in the `test` directory and write your test case:

```dart
import 'package:test/test.dart';
import '../lib/add.dart'; // Assume your `add` function is in lib/add.dart

void main() {
  test('adds two numbers', () {
    var expected = 3;
    expect(add(1, 2), equals(expected));
  });
}
```

To run the tests, use the Dart command:

```bash
$ dart test
```

Sample output might resemble:

```
00:01 +1: All tests passed!
```

### Using a third-party library: Mockito for mocking
For testing code that has complex dependencies, you might use Mockito to create mock objects. First, add Mockito to your `pubspec.yaml`:

```yaml
dev_dependencies:
  mockito: ^5.0.0
```

Assuming you have a class `UserRepository` that fetches user data, and you want to test a `UserService` that depends on `UserRepository` without hitting a real database:

```dart
import 'package:mockito/mockito.dart';
import 'package:test/test.dart';
import 'package:your_project/user_repository.dart';
import 'package:your_project/user_service.dart';

// Create a Mock class using Mockito
class MockUserRepository extends Mock implements UserRepository {}

void main() {
  group('UserService Tests', () {
    test('Fetches user successfully', () {
      // Create mock instance
      final mockUserRepository = MockUserRepository();
      final userService = UserService(mockUserRepository);

      // Setting up mock behavior
      when(mockUserRepository.fetchUser(1)).thenReturn(User(id: 1, name: 'Test User'));

      // Asserting that the mocked method is called with expected arguments
      expect(userService.getUserName(1), 'Test User');
      verify(mockUserRepository.fetchUser(1)).called(1);
    });
  });
}
```

Running this test confirms that `UserService` correctly interacts with `UserRepository`, using mocking to simulate the real interactions in a controlled way.
