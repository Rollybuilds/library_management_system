# Library Management System

A simple console-based Library Management System written in Python. It is built using Object-Oriented Programming (OOP) concepts and saves all book records in a CSV file.

## What the project does

This project helps a library manage its books. A user can add new books, search for books, issue a book to a member, return a book, and view all the books that are currently available. All records are saved in `books.csv`, so the data is not lost when the program is closed.

## How the project works

1. When the program starts, it loads the saved records from `books.csv`. If the file does not exist, it starts with an empty library.
2. A menu is shown and the user selects an option (1 to 6).
3. Each book has a unique ID, a title, an author, and an `issued_to` field. If `issued_to` is empty, the book is available.
4. After every change (add, issue, return), the records are saved to `books.csv` automatically.
5. Invalid input (wrong ID, empty title, already issued book, file errors) is handled with exception handling, so the program does not crash.

## How to run the project

**Requirements:** Python 3.8 or above. No extra libraries are needed.

**On your computer:**

```
python library_management_system.py
```

**On Google Colab:**

1. Paste the code into a cell and run it.
2. Use the menu by typing a number and pressing Enter.
3. Choose option 6 to exit and save. The `books.csv` file will be created in the Colab files panel.

## Classes used

| Class | Type | Purpose |
|---|---|---|
| `LibraryError` | Custom exception | Raised when an action cannot be completed (book not found, already issued, etc.) |
| `LibraryItem` | Abstract base class (`abc`) | Defines the common structure for any lendable item, with private attributes and abstract methods `to_row()` and `__str__()` |
| `Book` | Derived class | Inherits from `LibraryItem` and adds the `author` attribute |
| `Library` | Manager class | Stores all books and handles adding, searching, issuing, returning, and saving records |

## Main features implemented

- **Add books:** adds a new book with an automatically generated ID
- **Search books:** finds books by title or author (not case-sensitive)
- **Issue books:** issues an available book to a member
- **Return books:** marks an issued book as available again
- **Display available books:** lists all books that are not issued
- **Save records:** reads and writes data using a CSV file (`books.csv`)

## OOP concepts demonstrated

| Concept | Where it is used |
|---|---|
| Classes & Objects | `LibraryItem`, `Book`, `Library` |
| Encapsulation | Private attributes (`__title`, `__issued_to`, etc.) with getters and setters using `@property` |
| Inheritance | `Book` inherits from `LibraryItem` |
| Abstraction | `LibraryItem` is an abstract class using the `abc` module |
| File Handling | Records are read from and written to `books.csv` |
| Exception Handling | `LibraryError`, `FileNotFoundError`, `ValueError`, and `OSError` are handled |
