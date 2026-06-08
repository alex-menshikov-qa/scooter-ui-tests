# Scooter UI Tests

UI test automation project for a scooter rental web application.

The project demonstrates automated browser testing using Python, Pytest, Selenium WebDriver, Page Object Model, and Allure.

## Tech stack

* Python
* Pytest
* Selenium WebDriver
* Page Object Model
* Allure
* Firefox headless mode

## Test coverage

The test suite covers the main user-facing flows of the application:

* FAQ section on the main page
* scooter order flow
* order form validation and completion
* navigation via the application logo
* navigation to the external Dzen page

## Project structure

* `tests/` - UI test cases
* `pages/` - Page Object classes and page-specific methods
* `locators/` - Selenium locators grouped by page
* `conftest.py` - Pytest fixtures and browser setup
* `data.py` - test data and configurable URLs
* `pytest.ini` - Pytest configuration
* `requirements.txt` - project dependencies

## How to run

Install dependencies:

```bash
pip install -r requirements.txt
```

Run tests:

```bash
pytest
```

Run tests with detailed output:

```bash
pytest -v
```

Run tests with Allure results:

```bash
pytest --alluredir=allure_results
allure serve allure_results
```

## Environment

By default, the tests run against the public demo site:

```text
https://qa-scooter.praktikum-services.ru/
```

The base URL can be overridden with environment variables:

```bash
BASE_URL=https://example.com pytest
```

The external Dzen URL can also be overridden:

```bash
DZEN_URL=https://example.com pytest
```

Default values are listed in `.env.example`.

## Notes

This repository is a portfolio version of a UI test automation project.

The tests depend on an external public demo environment, so availability and behavior of the target site may affect test results.