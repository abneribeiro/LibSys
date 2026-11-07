<div align="center">
  <br />
  <h3><b>libsys</b></h3>
  <p>a library management system in c++: books, readers, loans and fines, from a terminal menu.</p>
</div>

<br />

<div align="center">

https://github.com/user-attachments/assets/4e5223fc-422d-408c-928c-01582e50bc84

<sub><i>the main menu, managing books, readers and loans</i></sub>

</div>

<br />

## **overview**

-   books: add, remove, edit and list newspapers, magazines, and scientific, educational and fiction books
-   readers: students, teachers, seniors and common readers, with their overdue books and fines
-   loans: requests, returns, extensions and fines
-   data is loaded from and saved to plain text files in `database/`, and saved automatically on exit
-   stack: `c++`, `g++`, `make`

## **design & trade-offs**

-   **inheritance for the domain:** every publication derives from `General` and every reader from `Person`, so the library handles one list of each through base-class pointers and virtual `showInfo()`.
-   **behaviour per reader type:** rules that differ by reader live in the subclass, such as the discount a `Senior` gets through `getDiscount()`.
-   **plain text over a database:** `books.txt`, `readers.txt` and `loans.txt` are `;`-separated files read with `ifstream` and written with `ofstream`. simple to inspect and edit by hand, with no dependency, at the cost of no concurrent access or schema checks.
-   **why it exists:** a personal challenge to apply polymorphism, classes and file handling to a real problem.

## **quickstart**

needs a c++ compiler (`g++`) and `make`.

```bash
git clone https://github.com/abneribeiro/LibSys.git
cd LibSys
make run      # builds ./main and starts the menu
make clean    # removes the objects and the binary
```

## **usage**

the main menu gives access to:

1. **manage books**: add, remove, edit and list books.
2. **manage readers**: add, edit, remove and list readers.
3. **manage loans**: book requests, returns, extensions and fines.
4. **advanced options**: save and load data, reports.
5. **exit**: leaves the program, saving the data.

## **license**

-   [mit](LICENSE)
