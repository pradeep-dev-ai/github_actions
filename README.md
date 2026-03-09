# GitHub Actions CI Pipeline Example

This project demonstrates how to use **GitHub Actions** to automate testing using a CI pipeline.
Whenever code is pushed to the repository, the workflow automatically runs unit tests.

---

## Project Overview

The goal of this project is to:

* Learn Continuous Integration (CI)
* Run automated tests using GitHub Actions
* Maintain a clean Python project structure
* Ensure code quality with automated pipelines

---

## Project Structure

```
github_actions_example/
│
├── .github/
│   └── workflows/
│       └── unittest.yml
│
├── src/
│   ├── __init__.py
│   └── math_operation.py
│
├── tests/
│   ├── __init__.py
│   └── test_operation.py
│
├── requirements.txt
└── README.md
```

---

## Features

* Automated CI pipeline
* Python unit testing
* Organized project structure
* GitHub Actions workflow

---

## Math Operations Module

The `math_operation.py` module contains simple mathematical functions such as:

* Addition
* Subtraction

Example:

```python
def add(a, b):
    return a + b

def subtract(a, b):
    return a - b
```

---

## Unit Tests

Unit tests are located inside the **tests** folder.

Example test:

```python
def test_add():
    assert add(2, 3) == 5
```

These tests verify that the functions behave correctly.

---

## Continuous Integration with GitHub Actions

The workflow file is located in:

```
.github/workflows/unittest.yml
```

The CI pipeline performs the following steps:

1. Trigger when code is pushed
2. Install Python
3. Install dependencies
4. Run unit tests
5. Report results

---

## Running Tests Locally

To run the tests locally:

```bash
pip install -r requirements.txt
pytest
```

---

## Example CI Workflow

```yaml
name: Python CI

on:
  push:
    branches: [ main ]

jobs:
  test:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v3

      - name: Setup Python
        uses: actions/setup-python@v4
        with:
          python-version: 3.11

      - name: Install dependencies
        run: pip install -r requirements.txt

      - name: Run tests
        run: pytest
```

---

## Learning Outcomes

This project helps understand:

* Continuous Integration
* GitHub Actions automation
* Python unit testing
* CI pipelines used in real-world projects

