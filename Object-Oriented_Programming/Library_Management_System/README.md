# 📚 Library Management System

A professional, menu-driven **Library Management System** built entirely with
Python's standard library, showcasing intermediate-to-advanced
Object-Oriented Programming design suitable for a GitHub portfolio.

---

## 📖 Project Overview

This project simulates the core operations of a real library: managing a
book catalogue, registering members, issuing and returning books, tracking
overdue loans, and calculating late fines. It is implemented as a single,
dependency-free Python module (`library_management_system.py`) with a clean
console-based menu, so it can be run directly in **Google Colab**, a local
terminal, or any Python 3.9+ environment with zero installation steps.

The codebase is intentionally structured the way a production system would
be: a domain layer (`Person`, `Member`, `Librarian`, `Book`, `Loan`,
`Library`) that knows nothing about the console, and a thin CLI layer
(`LibraryCLI`) that only handles input/output and delegates all business
logic to the domain layer.

---

## ✨ Features

- **Catalogue management** — add books, restock existing titles, search by
  title/author/ISBN, and browse the full catalogue.
- **Member registration** — with tiered memberships (`Standard`, `Premium`,
  `Student`), each carrying its own borrowing limit and loan period.
- **Circulation workflow** — issue and return books with automatic due-date
  calculation and copy-availability tracking.
- **Fine management** — automatic overdue fine calculation, outstanding
  balance tracking per member, and a dedicated "pay fine" workflow.
- **Reporting** — an overdue-loans report and a library-wide statistics
  dashboard (titles, copies on loan, active members, etc.).
- **Robust validation** — emails, phone numbers, ISBNs, copy counts, and
  publication years are all validated before being accepted.
- **Rich exception hierarchy** — every failure mode (book not found, no
  copies available, borrowing limit exceeded, duplicate member, etc.) is
  raised as a specific, catchable exception rather than a generic error.

---

## 🧠 OOP Concepts Used

| Concept | Where it appears |
|---|---|
| **Encapsulation** | `Book`, `Person`, and `Member` keep internal state (`_available_copies`, `_active_loans`, `_outstanding_fine`) private and expose it only through validated properties and controlled methods. |
| **Abstraction** | `Person` is an `ABC` with an abstract `get_role()` method — it defines a contract without dictating implementation. |
| **Inheritance** | `Member` and `Librarian` both inherit shared identity/validation logic from `Person`. |
| **Polymorphism** | `get_role()` behaves differently for `Member` ("Member") and `Librarian` ("Librarian"), and both are used interchangeably wherever a `Person.__str__` is needed. |
| **Composition** | `Library` *has-a* dictionary of `Book`, `Member`, `Librarian`, and `Loan` objects — it coordinates them rather than inheriting from them. |
| **Data classes** | `Loan` uses `@dataclass` for a concise, immutable-by-convention transaction record with computed properties (`is_overdue`, `days_overdue`). |
| **Enums** | `BookGenre` and `MembershipType` replace "magic strings" with type-safe, self-documenting constants (`MembershipType` even carries per-tier business rules). |
| **Custom exceptions** | A dedicated `LibraryError` hierarchy (`BookNotFoundError`, `BorrowLimitExceededError`, etc.) enables precise error handling in the CLI layer. |

---

## 🛠️ Technologies Used

- **Python 3.9+**
- Standard library only:
  - `abc` — abstract base classes
  - `dataclasses` — the `Loan` transaction record
  - `datetime` — issue/due/return date arithmetic
  - `enum` — `BookGenre`, `MembershipType`
  - `typing` — type hints throughout
  - `uuid` — unique member, librarian, and loan IDs

No third-party packages are required, so the project runs unmodified in
Google Colab.

---

## ▶️ How to Run

### Option 1 — Google Colab
1. Create a new Colab notebook.
2. Copy the entire contents of `library_management_system.py` into a cell.
3. Run the cell — the menu will appear and accept input directly in the
   Colab output panel.

### Option 2 — Local terminal
```bash
python3 library_management_system.py
```

The system starts pre-seeded with a small demo catalogue (Clean Code, Dune,
A Brief History of Time) and one librarian, so you can start issuing and
returning books immediately.

---

## 🖥️ Sample Output

Below is an actual transcript from a session (adding a book, searching,
registering a member, issuing/returning a book, and viewing statistics):

```
Welcome to City Central Library Management System

==================== MAIN MENU ====================
 1. Add / Restock Book
 2. Search Books
 3. View Full Catalogue
 4. Register Member
 5. Issue Book
 6. Return Book
 7. View Member Details
 8. Pay Outstanding Fine
 9. Overdue Loans Report
10. Library Statistics
 0. Exit
====================================================
Enter your choice: 4

-- Register New Member --
Full name: John Smith
Email: john.smith@example.com
Phone: 5551234567
Membership types: Standard, Premium, Student
Membership type [Standard]: Premium

Success: Registered Member | John Smith (ID: 00000002, Email: john.smith@example.com).
Membership ID: 00000002

Enter your choice: 5

-- Issue Book --
Book ISBN: 9780132350884
Member ID: 00000002

Success: Book issued. Loan#00000003 | ISBN:9780132350884 | Member:00000002 | Due:2026-07-23 | ACTIVE

Enter your choice: 7

Member ID: 00000002

Member | John Smith (ID: 00000002, Email: john.smith@example.com)
Membership: Premium
Books currently borrowed: 1
Outstanding fine: $0.00
Active loans:
  - Loan#00000003 | ISBN:9780132350884 | Member:00000002 | Due:2026-07-23 | ACTIVE

Enter your choice: 6

-- Return Book --
Loan ID: 00000003

Success: Book returned on time. No fine incurred.

Enter your choice: 10

-- Library Statistics --
  Titles: 4
  Total Copies: 9
  Available Copies: 9
  On Loan: 0
  Members: 1
  Active Loans: 0
  Overdue Loans: 0
```

---

## 🚀 Future Improvements

- Persist data to disk (JSON/SQLite) so the catalogue survives restarts.
- Add reservation/hold queues for books that are fully checked out.
- Support multiple librarians with role-based permissions (e.g., only
  librarians can remove books).
- Email/SMS notifications for due-soon and overdue loans.
- Expose the domain layer through a REST API (e.g., with `FastAPI`) while
  reusing the exact same `Library` business logic.
- Add a unit test suite (`pytest`) covering the exception paths.

---

## 📄 License

This project is released under the MIT License — free to use and adapt for
learning or portfolio purposes.
