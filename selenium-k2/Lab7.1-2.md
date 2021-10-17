## Lab 7.1
* Animal Racing by abstraction: Integer speed(random), Boolean flyable

## Lab 7.2
* Book: String ISBN, String title, String author
* 1: Add book(IN-memory storage) | 2: Retrieve Book INfo(ISBN) | 0: Exit!

## Example for BookMenu
```
public class BookMenu {

    // In-memory storage | Can use HashMap as well ... any it's up to use
    static List<Book> bookList = new ArrayList<>();

    public static void main(String[] args) {
        boolean isContinuing = true;

        while(isContinuing){
            System.out.println("=======MENU=========");
            System.out.println("1. Add book");
            System.out.println("2. Retrieve book(ISBN)");
            System.out.println("0. Exit!");

            Scanner scanner = new Scanner(System.in);
            int userOption = scanner.nextInt();
            switch (userOption){
                case 0:
                    System.out.println("Bye!");
                    isContinuing = false;
                    break;
                case 1:
                    addBook();
                    break;
                case 2:
                    retrieveBook();
                    break;

            }
        }

    }

    private static void addBook() {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Book ISBN: ");
        String ISBN = scanner.nextLine();
        System.out.print("Book title: ");
        String bookTitle = scanner.nextLine();
        System.out.print("Book's author name: ");
        String authorName = scanner.nextLine();
        Book book = new Book(ISBN, bookTitle, authorName);
        bookList.add(book);
    }

    private static void retrieveBook() {
        Scanner scanner = new Scanner(System.in);
        // TODO: Cover logic when Booklist is empty

        for (Book book : bookList) {
            System.out.println(book);
        }
    }
}
```