# LAB 12

The main purpose of this lab is to explore Comparable and Comparator interfaces. 

# Model
Please create a standard class for Book with below class fields:
* ISBN
* year
* title
* author

# Controller
Please create one (or more) methods to sort a List<Book> for below fields (ASC or DESC)
* ISBN
* year
* title
* author

# Example method signature

```
public void printSortedBooksByISBN(List<Book> bookList){}

OR:
public void printSortedBooks(List<Book> bookList, SortingType sortingType){}

// And other support methods to make sure we use best practice for Single Reposibility
```