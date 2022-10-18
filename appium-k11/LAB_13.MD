# Book Management

**Menu:**

```
======= Book Management Program (CRUD)============
1. New book
2. Find a book(ISBN)
3. Update a book
4. Delete a book
5. Print the book list
0. Exit
```

## Options explanations

### 1. New book
```
Please input ISBN: 
Please input title: 
Please input author: 
Please input year: 

The book is saved into DB wit info: Book {ISBN, title, author, year}
```

### 2. Find a book(ISBN)
```
Please input ISBN: 
```

* If the book found -> print the Book {ISBN, title, author, year}
* If the book is not found -> Book with ISBN <1234> is not found

### 3. Update a book

```
Please input ISBN: 
    (control if the book is not existing...)
Please input new title: 
Please input new author name: 
Please input new year: 

The book is now updated with new content: Book {ISBN, title, author, year}
```

### 4. Delete a book
```
Please input ISBN: 
    (control if the book is not existing...)
```

## Print book list example

```
Book 01: Cuon theo chieu gio
    ISBN: 1234
    author: Teo
    year: 2022
    
Book 02: Tieng chim hot trong bui man gai
    ISBN: 12345
    author: Ti
    year: 2021
```

## Hints
* Add new: Get the old book list -> add new -> save again!
* Update: Get the book list -> find -> Update that book object -> save again!
* Delete: Get the book list -> find -> Delete that book object -> save again!
