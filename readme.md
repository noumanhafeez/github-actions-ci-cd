# GitHub Actions Demo – Collaborative Development Workflow

## Project Overview

## This repository demonstrates how GitHub Actions automates testing and quality checks in a collaborative development environment where multiple contributors are working on the same project.

## The goal of this repository is to show how automated workflows ensure code quality and prevent broken code from being merged into the main branch.

## The repository simulates a team environment with multiple contributors pushing code, creating pull requests, and triggering automated workflows.

---

# Contributors

## The project assumes a collaborative team structure.

## Example contributors:

* Alice – Backend Developer
* Bob – Machine Learning Engineer
* Charlie – Data Engineer
* Nouman – Project Maintainer

## Each contributor can push code, open pull requests, or update features.

---

# Repository Structure

## The repository follows a typical project structure.

```text
project-repo/

src/
   calculator.py
tests/
   test_calculator.py

.github/
   workflows/
       ci_pipeline.yml

requirements.txt
README.md
```

## Explanation of folders

### src/

## Contains application code.

### tests/

## Contains unit tests that validate the functionality of the application.

### .github/workflows/

## Contains GitHub Actions workflow files.

---

# Scenario: How Collaboration Works

## Multiple contributors work on different features.

### Example workflow

```text
Alice creates a new feature branch
        ↓
Alice pushes code to GitHub
        ↓
GitHub Action automatically runs tests
        ↓
If tests pass → Pull request can be merged
If tests fail → Developer must fix the code
```

---

# Example Python Code

## src/calculator.py

```python
def add(a, b):
    return a + b

def divide(a, b):
    return a / b
```

---

# Example Unit Test

## tests/test_calculator.py

```python
from src.calculator import add, divide

def test_add():
    assert add(2, 3) == 5

def test_divide():
    assert divide(10, 2) == 5
```

---

# GitHub Actions Workflow

## File location

```text
.github/workflows/ci_pipeline.yml
```

## Workflow configuration

```yaml
name: Python CI Pipeline

on:
  push:
    branches: [ main, dev ]
  pull_request:
    branches: [ main ]

jobs:
  test:

    runs-on: ubuntu-latest

    steps:
      - name: Checkout Repository
        uses: actions/checkout@v3

      - name: Setup Python
        uses: actions/setup-python@v4
        with:
          python-version: "3.10"

      - name: Install Dependencies
        run: pip install pytest

      - name: Run Tests
        run: pytest
```

---

# What This Workflow Does

## When the workflow runs

The workflow triggers when:

* code is pushed to `main`
* code is pushed to `dev`
* a pull request is created

---

## Steps performed automatically

### Step 1 – Checkout repository

## GitHub downloads the project code to a virtual machine.

### Step 2 – Setup Python

## A Python environment is installed on the runner.

### Step 3 – Install dependencies

## Required packages are installed.

### Step 4 – Run tests

## Unit tests are executed automatically.

---

# Example Team Scenario

## Bob pushes new feature

```text
Bob pushes new code
        ↓
GitHub Actions starts automatically
        ↓
Tests run on server
        ↓
If tests fail → Bob fixes code
```

---

## Charlie opens pull request

```text
Charlie creates Pull Request
        ↓
GitHub runs CI pipeline
        ↓
Maintainer reviews code
        ↓
If tests pass → Merge allowed
```

---

# Benefits of GitHub Actions in Teams

## Prevents broken code from entering main branch

## Ensures consistent code quality

## Automates testing process

## Provides instant feedback to developers

## Enables safe collaboration among multiple contributors

---

# Where to View Workflow Results

## Workflow results can be viewed inside the repository.

```text
Repository → Actions tab
```

## Inside the Actions tab you can see

* workflow runs
* logs
* errors
* success or failure status

---

# Example Workflow Execution

```text
Developer Pushes Code
        ↓
GitHub Action Triggered
        ↓
Environment Setup
        ↓
Tests Executed
        ↓
Status Report Generated
```

---

# Possible Extensions

## This repository can be extended to include

* linting checks
* Docker image builds
* automated deployment
* ML model training pipelines
* scheduled workflows

---

# Key Learning Objectives

## Understand how GitHub Actions workflows work

## Learn how CI pipelines are structured

## Understand collaboration workflows in GitHub

## Learn how automation improves code reliability

---

# Author

## Nouman Hafeez

## Machine Learning and Software Development Enthusiast
