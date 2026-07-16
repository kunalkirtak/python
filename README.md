# 🐍 Python Projects

A growing collection of hands-on Python projects built while learning core and modern Python concepts — from fundamentals like variables and strings to decorators, generators, OOP, and data validation with Pydantic.

Each topic lives in its own folder as a set of runnable Jupyter notebooks (Google Colab friendly), paired with a dedicated README that documents the features, concepts, and learning outcomes for that topic.

![Python](https://img.shields.io/badge/Python-3.9%2B-3776AB?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green)

---

## 📖 Table of Contents

- [About](#-about)
- [Repository Structure](#-repository-structure)
- [Projects by Topic](#-projects-by-topic)
- [Technologies Used](#-technologies-used)
- [Getting Started](#-getting-started)
- [Python Concepts Covered](#-python-concepts-covered)
- [License](#-license)
- [Author](#-author)

---

## 📌 About

This repository is a personal Python learning journal turned portfolio. Instead of isolated snippets, each concept is reinforced through small, practical applications (calculators, trackers, management systems, validators) that mirror how the concept is actually used in real-world code.

It's a good reference if you're:
- Learning Python from the ground up
- Looking for practical, mini-project ideas per topic
- Preparing for interviews or building a GitHub portfolio

---

## 📂 Repository Structure

| Folder | Topic | Contents |
|---|---|---|
| [`Variables-DataTypes/`](./Variables-DataTypes) | Variables & Data Types | 4 notebooks |
| [`Strings/`](./Strings) | Strings & String Methods | 3 notebooks |
| [`List/`](./List) | Lists & Dictionaries | 3 notebooks |
| [`Functions/`](./Functions) | Functions & Modular Programming | 3 notebooks |
| [`Exception-Handling/`](./Exception-Handling) | try / except / raise | 2 notebooks |
| [`Functional-Programming/`](./Functional-Programming) | map, filter, reduce, lambda | 2 notebooks |
| [`Decorators/`](./Decorators) | Decorators & Wrapper Functions | 2 notebooks |
| [`Generators/`](./Generators) | Generators & yield | 2 notebooks |
| [`Object-Oriented_Programming/`](./Object-Oriented_Programming) | Classes, Inheritance, ABCs | 2 full systems |
| [`Modern-Python/`](./Modern-Python) | Type Hints, Dataclasses, Pathlib, Logging | 3 notebooks |
| [`Pydantic/`](./Pydantic) | Data Validation & Modeling | 3 notebooks |

Every folder contains its own `README.md` with feature breakdowns, concepts covered, and learning outcomes for that topic.

---

## 🚀 Projects by Topic

### Variables & Data Types
Temperature Converter · Age Calculator · EMI Calculator · Percentage Calculator

### Strings
Password Checker · Email Validator · Text Analyzer

### Lists
Student Marks Manager · To-Do List · Expense Tracker

### Functions
Calculator · Banking Menu · Employee Management System

### Exception Handling
ATM System · Login System

### Functional Programming
Student Result Analyzer · Employee Data Analyzer

### Decorators
Performance Profiler (Timing Decorator) · Application Logger (Logging Decorator)

### Generators
Log File Analyzer · Large Dataset Processor

### Object-Oriented Programming
**Hospital Management System** — patients, doctors, appointments, wards, billing, built with encapsulation, inheritance, abstraction (ABC), polymorphism, and composition.
**Library Management System** — catalogue, memberships, circulation, fines, and reporting, built entirely with the standard library.

### Modern Python
Student Record Manager · File Organizer · Expense Tracker with Logging — using dataclasses, type hints, `pathlib`, and `logging`.

### Pydantic
User Model · Product Model · Order Model — data validation and nested models with Pydantic v2.

---

## 🛠️ Technologies Used

- **Python 3.9+**
- **Jupyter Notebook** (developed and run in Google Colab)
- **Pydantic v2** and `email-validator` (Pydantic folder only — see [`requirements.txt`](./Pydantic/requirements.txt))
- Python standard library: `abc`, `dataclasses`, `enum`, `datetime`, `pathlib`, `logging`, `uuid`, `typing`

---

## ⚙️ Getting Started

Clone the repository:

```bash
git clone https://github.com/kunalkirtak/python-projects.git
cd python-projects
```

Most notebooks run out of the box in **Google Colab** — just upload the `.ipynb` file, or open it directly from GitHub via Colab's "Open notebook from GitHub" option.

To run locally with Jupyter:

```bash
pip install notebook
jupyter notebook
```

For the Pydantic notebooks, install the extra dependencies first:

```bash
pip install -r Pydantic/requirements.txt
```

---

## 🧠 Python Concepts Covered

Variables & Data Types · Type Casting · String Methods · Lists & Dictionaries · Loops & Conditionals · Functions & Modular Programming · Exception Handling (`try`/`except`/`raise`) · List & Dictionary Comprehensions · Lambda, `map()`, `filter()`, `reduce()` · Decorators & Wrapper Functions · Generators & `yield` · Object-Oriented Programming (Encapsulation, Inheritance, Abstraction, Polymorphism, Composition) · Custom Exceptions · Type Hinting & Dataclasses · `pathlib` & `logging` · Data Validation with Pydantic

---

## 📄 License

This project is licensed under the [MIT License](./LICENSE).

---

## 👨‍💻 Author

**Kunal B. Kirtak**
B.Tech Electronics & Computer Science | AI/ML | Python Developer

⭐ If you find this repository useful, consider giving it a star!
