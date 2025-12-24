** For generating Unit test **
Write comprehensive unit tests in C# for every public method in the following class using MSTest,FluentAssertions and Moq.
className: MathUtil
Requirements:

Use the MSTest framework attributes ([TestClass], [TestMethod], [DataTestMethod], [DataRow], etc.).
Use parameterized tests ([DataTestMethod] with multiple [DataRow]s) wherever it makes sense (e.g., for different input/output combinations of the same method).
Use Moq to mock any external dependencies or collaborators used by class (e.g., interfaces injected via constructor or methods).
Cover normal cases, edge cases, and error conditions (e.g., null arguments, out-of-range values, exceptions).
Use clear, Arrange–Act–Assert structure inside each test.
Name test methods clearly, following a pattern like MethodName_Scenario_ExpectedResult.
Ensure tests are independent, deterministic, and do not rely on external state (files, network, database, etc.).
Assume the this class is already implemented and available in the main project. Generate only the test code file.
Use FluentAssertions for assertions
