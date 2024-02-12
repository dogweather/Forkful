---
title:                "Writing tests"
aliases:
- /en/c-sharp/writing-tests/
date:                  2024-02-03T19:03:30.729590-07:00
model:                 gpt-4-0125-preview
simple_title:         "Writing tests"
tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/en/c-sharp/writing-tests.md"
---

{{< edit_this_page >}}

## What & Why?

Writing tests in C# involves creating automated scripts to validate the functionality of your code, ensuring it behaves as expected. Programmers do it to catch bugs early, facilitate code refactoring, and ensure new changes don't break existing functions, thereby boosting software quality and reliability.

## How to:

C# developers primarily use the NUnit or xUnit frameworks for writing tests due to their flexibility and extensive feature set. Here’s a basic example using NUnit to test a simple addition function:

1. **Install NUnit and NUnit3TestAdapter** via NuGet Package Manager or the .NET CLI:
```powershell
dotnet add package NUnit
dotnet add package NUnit3TestAdapter
```

2. **Create a C# class library** project if you haven't done so already.

3. **Write a simple function** to test. For example, an addition method in a class named `Calculator`:
```csharp
public class Calculator
{
    public int Add(int a, int b)
    {
        return a + b;
    }
}
```

4. **Write a test class** using NUnit:
```csharp
using NUnit.Framework;

namespace CalculatorTests
{
    [TestFixture]
    public class CalculatorTests
    {
        [Test]
        public void Add_AddsTwoIntegers_ReturnsCorrectSum()
        {
            // Arrange
            var calculator = new Calculator();
            int expected = 5;

            // Act
            int actual = calculator.Add(2, 3);

            // Assert
            Assert.AreEqual(expected, actual);
        }
    }
}
```

5. **Run the test** using your IDE's test runner or the .NET CLI:
```powershell
dotnet test
```

### Sample Output:

Assuming your test passes, you should see output similar to this:
```
Test Run Successful.
Total tests: 1
     Passed: 1
 Total time: 1.2345 Seconds
```

### Using xUnit:

If you prefer xUnit, the setup is similar to NUnit. Here's how you'd rewrite the test example for the `Calculator` class using xUnit:

1. **Install xUnit and xUnit.runner.visualstudio**:
```powershell
dotnet add package xUnit
dotnet add package xUnit.runner.visualstudio
```

2. **Write a test class using xUnit**:
```csharp
using Xunit;

namespace CalculatorTests
{
    public class CalculatorTests
    {
        [Fact]
        public void Add_AddsTwoIntegers_ReturnsCorrectSum()
        {
            // Arrange
            var calculator = new Calculator();
            int expected = 5;

            // Act
            int actual = calculator.Add(2, 3);

            // Assert
            Assert.Equal(expected, actual);
        }
    }
}
```

3. **Run the test using the .NET CLI** or your IDE’s integrated test runner.

Both NUnit and xUnit provide powerful features for parameterized testing, setup/teardown operations, and organizing tests into categories, making them indispensable tools in the C# programmer’s toolkit for ensuring code quality and functionality.
