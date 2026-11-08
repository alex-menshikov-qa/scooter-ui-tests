# Scooter UI Tests

UI test automation project for a scooter rental web application.

The project demonstrates automated browser testing with Python, pytest, Selenium WebDriver, the Page Object Model, and Allure reports: parametrized user flows, page objects with locators grouped by page, and step-by-step reporting.

## Tech stack

* Python
* pytest
* Selenium WebDriver (Firefox, headless)
* Page Object Model
* Allure

## Test suite at a glance

12 tests, including parametrized cases:

| File | Tests | What is covered |
|---|---|---|
| `test_main_page.py` | 8 | FAQ accordion: each of the 8 questions opens the expected answer text |
| `test_order_page.py` | 2 | end-to-end order flow from both "Order" buttons (header and page bottom), with two data sets: two-step form, metro-station search, date picker, rental period, confirmation |
| `test_switching_page.py` | 2 | logo navigation: the product logo returns to the main page; the company logo opens an external page in a new tab |

## Project structure

* `tests/` - UI test cases
* `pages/` - Page Object classes with page-specific actions
* `locators/` - Selenium locators grouped by page
* `conftest.py` - pytest fixtures: headless Firefox setup and page objects
* `data.py` - test data and configurable URLs
* `pytest.ini` - pytest configuration (verbose output, Allure results directory)
* `requirements.txt` - project dependencies
* `.env.example` - environment variables and their default values

## Requirements

* Python 3.10+
* Mozilla Firefox. Selenium Manager downloads a matching GeckoDriver automatically.
* [Allure CLI](https://allurereport.org/docs/install/), only to view reports

## How to run

Install dependencies:

```bash
pip install -r requirements.txt
```

Run tests:

```bash
pytest
```

Allure results are written to `allure_results/` on every run (set in `pytest.ini`). To open the report:

```bash
allure serve allure_results
```

## Environment

| Variable | Default | Purpose |
|---|---|---|
| `BASE_URL` | `https://qa-scooter.praktikum-services.ru/` | Application under test |
| `DZEN_URL` | `https://dzen.ru/?yredirect=true` | Expected external page opened by the company logo |

Example:

```bash
BASE_URL=https://example.com pytest
```

## Notes

This repository is a portfolio version of a UI test automation project.

The suite runs against a public demo environment that this project does not control, so the availability and behavior of the target site, and of the external page in the logo test, may affect results.
