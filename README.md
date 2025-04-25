# pytest-history-bdd

`pytest-history-bdd` is a Pytest plugin that captures and stores BDD-style test results from Allure JSON reports into a structured SQLite database.

## ✅ Features
- Parses Allure JSON reports (`allure-results/` directory).
- Extracts test case and test step results.
- Supports BDD-style tagging using `labels.tag` with `IPC_*`.
- Records metadata like environment, execution time, and failure reasons.
- CLI and `pytest.ini` configuration support for environment info.

## 📦 Installation
```bash
pip install pytest-history-bdd
```

## 🧪 Usage
```bash
pytest --alluredir=allure-results --bdd-env=staging
```
Or via `pytest.ini`:
```ini
[pytest]
bdd_env = staging
```

## 🗂️ Output Schema
Creates a SQLite DB (`test_bdd.db`) with the following tables:
- `TestRun`
- `TestSuites`
- `TestCaseExecution`
- `TestStepExecutionResult`

## 📁 Project Structure
```bash
pytest_allure_db/
├── plugin.py              # Pytest plugin hooks
├── parser.py              # Allure JSON parser
├── db_handler.py          # SQLite database handler
setup.py
README.md
tests/
├── test_example.py        # Basic unit test
├── test_login_bdd.py      # Pytest-BDD + Allure integrated scenario
```

## 🧩 Integration
This plugin is compatible with `allure-pytest` and works best with `pytest-bdd` for BDD-style test frameworks.

---
MIT License © 2025
