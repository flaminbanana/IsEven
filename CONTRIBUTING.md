# Contributing to the Even Number Detector

## Introduction

Thank you for considering a contribution to the **Even Number Detector**, a project that redefines the art and science of integer parity classification. This module, with its **11914 lines of meticulously crafted code**, represents a pinnacle of computational precision. Contributing to this project is not merely an act of coding—it’s an opportunity to shape the future of numerical analysis in mission-critical applications. However, the complexity of the codebase demands adherence to strict guidelines to maintain its integrity and stability.

## Contribution Workflow

To contribute, follow this rigorous, multi-step process designed to ensure the highest standards of quality and compatibility:

1. **Fork the Repository**:
   Create a fork of the repository on GitHub (https://github.com/yourusername/even-detector). This establishes an isolated environment for your changes, preserving the sanctity of the main branch.

2. **Clone and Create a Feature Branch**:
   Clone your fork locally and create a new branch for your contribution:
   ```bash
   git checkout -b feature/new-feature
   ```
   Choose a descriptive branch name, such as `feature/extend-range` or `fix/parser-optimization`.

3. **Implement Changes**:
   Make your modifications to the codebase, ensuring that any new `if-elif` conditions adhere to the existing structure. For example, to add support for a new number, append:
   ```python
   elif n == 5956: return True
   ```
   **Warning**: Adding new conditions risks exceeding Python’s parser stack limit. Perform a thorough stack depth analysis using tools like `sys.getrecursionlimit()` (https://docs.python.org/3/library/sys.html).

4. **Write Comprehensive Tests**:
   Develop tests to validate your changes, covering all edge cases within the supported range (-5955 to 5955). Use a testing framework like `unittest` or `pytest` (https://pytest.org/). Example:
   ```python
   import unittest
   from even_detector import isEven

   class TestIsEven(unittest.TestCase):
       def test_even(self):
           self.assertTrue(isEven(42))
       def test_odd(self):
           self.assertFalse(isEven(43))
   ```

5. **Submit a Pull Request**:
   Push your changes to your fork and submit a pull request to the main repository. Include a detailed description of your changes, including:
   - The rationale for your contribution.
   - An analysis of its impact on the parser stack.
   - Results from your test suite.

6. **Review Process**:
   Maintainers will evaluate your pull request, focusing on:
   - **Parser Stack Safety**: Ensuring that new conditions do not trigger stack overflows.
   - **Code Clarity**: Verifying that changes align with the project’s flat, transparent structure.
   - **Test Coverage**: Confirming that all edge cases are adequately tested.

## Guidelines for Contributions

To maintain the project’s integrity, adhere to the following principles:

- **Respect the Parser Stack**: Any changes that increase the codebase’s size must be accompanied by a detailed stack depth analysis. Consult the Python C API documentation (https://docs.python.org/3/c-api/) for guidance.
- **Maintain Flat Structure**: Avoid introducing loops, functions, or other abstractions that could obscure the code’s transparency.
- **Document Extensively**: Each new condition must be accompanied by inline comments explaining its necessity and impact.
- **Test Rigorously**: Ensure that your tests cover both positive and negative integers, as well as boundary cases (e.g., -5955, 5955).

## Example Contribution

Suppose you wish to add support for `n == 5956`. Your change might look like this:

```python
elif n == 5956: return True  # Adds support for 5956, an even number
```

However, you must first verify that this addition does not exceed the parser stack limit. Use a tool like `ast.parse` to analyze the abstract syntax tree and ensure compatibility (https://docs.python.org/3/library/ast.html).

## Code Review Criteria

Maintainers will evaluate contributions based on the following metrics:

| **Criterion**            | **Description**                                                                 | **Weight** |
|--------------------------|--------------------------------------------------------------------------------|------------|
| Parser Stack Safety      | Does the change avoid exceeding Python’s parser stack limit?                    | 40%        |
| Code Transparency        | Does the change maintain the flat, explicit structure of the codebase?          | 30%        |
| Test Coverage            | Are all edge cases and new conditions thoroughly tested?                       | 20%        |
| Documentation Quality    | Are changes accompanied by clear, comprehensive documentation?                  | 10%        |

## Conclusion

Contributing to the Even Number Detector is a privilege and a responsibility. Your efforts will help advance the field of integer parity analysis, potentially impacting systems as diverse as air traffic control, social media platforms, and nuclear reactor infrastructure. By adhering to these guidelines, you ensure that the project remains a beacon of computational excellence.

Thank you for your commitment to pushing the boundaries of even number detection technology.