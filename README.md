## CI Pipeline Project (GitHub Actions + Python)

## Project Overview

This project demonstrates a **Continuous Integration (CI) pipeline** using GitHub Actions.

Whenever code is pushed to the repository, the pipeline automatically:

* Installs dependencies
* Runs tests
* Validates code quality

---

## Project Goal

* Automate testing process
* Ensure code quality
* Detect errors before deployment
* Implement real DevOps CI workflow

---

## Project Structure

```id="ps1"
project-ci/
│
├── app/
│   └── main.py
│
├── tests/
│   └── test_main.py
│
├── requirements.txt
│
└── .github/
    └── workflows/
        └── ci.yml
```

---

## Tech Stack

* Python
* Pytest
* GitHub Actions

---

## Implementation Steps

### 1️) Create Application

```python id="code1"
def add(a, b):
    return a + b
```

---

### 2️) Write Tests

```python id="code2"
from app.main import add

def test_add():
    assert add(2, 3) == 5
```

---

### 3️) Requirements File

```txt id="code3"
pytest
```

---

### 4️) GitHub Actions Workflow

```yaml id="code4"
name: CI Pipeline

on:
  push:
    branches: [ "main" ]
  pull_request:

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v3

      - name: Setup Python
        uses: actions/setup-python@v4
        with:
          python-version: "3.10"

      - name: Install dependencies
        run: pip install -r requirements.txt

      - name: Run tests
        run: pytest
```

---

## How It Works

1. Developer pushes code
2. GitHub Actions triggers workflow
3. Dependencies are installed
4. Tests are executed
5. Pipeline shows:

   *  Success (tests pass)
   *  Failure (tests fail)

---

### Fail Fast

* Pipeline stops if tests fail
* Prevents bad code from merging

---

## Key Learnings

* CI fundamentals
* GitHub Actions workflows
* Automated testing
* Debugging pipeline failures

---

## Author

Dhinakar M
