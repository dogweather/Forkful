---
title:                "编写测试"
date:                  2024-03-08T21:57:59.664849-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## 什么 & 为什么？

在 Dart 中编写测试，涉及创建测试用例以自动验证程序的不同部分是否按预期工作。程序员这样做是为了确保他们的代码可靠且无缺陷，从而便于更容易地更新和重构，同时防止回归。

## 如何操作：

在 Dart 中，通常使用 `test` 包来编写测试。首先，将 `test` 包添加到你的 `pubspec.yaml` 中：

```yaml
dev_dependencies:
  test: ^1.0.0
```

然后，为一个简单的函数编写测试。假设你有一个添加两个数字的函数：

```dart
int add(int a, int b) {
  return a + b;
}
```

接着，在 `test` 目录中创建一个名为 `add_test.dart` 的文件，并编写你的测试用例：

```dart
import 'package:test/test.dart';
import '../lib/add.dart'; // 假设你的 `add` 函数在 lib/add.dart 中

void main() {
  test('两数相加', () {
    var expected = 3;
    expect(add(1, 2), equals(expected));
  });
}
```

要运行测试，使用 Dart 命令：

```bash
$ dart test
```

样本输出可能类似于：

```
00:01 +1: 所有测试通过！
```

### 使用第三方库：Mockito 进行模拟

对于具有复杂依赖关系的代码测试，你可能会使用 Mockito 来创建模拟对象。首先，将 Mockito 添加到你的 `pubspec.yaml`：

```yaml
dev_dependencies:
  mockito: ^5.0.0
```

假设你有一个 `UserRepository` 类，用于获取用户数据，并且你想测试一个依赖于 `UserRepository` 的 `UserService`，而不触及真实数据库：

```dart
import 'package:mockito/mockito.dart';
import 'package:test/test.dart';
import 'package:your_project/user_repository.dart';
import 'package:your_project/user_service.dart';

// 使用 Mockito 创建一个 Mock 类
class MockUserRepository extends Mock implements UserRepository {}

void main() {
  group('UserService 测试', () {
    test('成功获取用户', () {
      // 创建模拟实例
      final mockUserRepository = MockUserRepository();
      final userService = UserService(mockUserRepository);

      // 设置模拟行为
      when(mockUserRepository.fetchUser(1)).thenReturn(User(id: 1, name: '测试用户'));

      // 断言模拟方法使用预期参数被调用
      expect(userService.getUserName(1), '测试用户');
      verify(mockUserRepository.fetchUser(1)).called(1);
    });
  });
}
```

运行此测试确认 `UserService` 正确地与 `UserRepository` 交互，使用模拟来以受控方式模拟真实交互。
