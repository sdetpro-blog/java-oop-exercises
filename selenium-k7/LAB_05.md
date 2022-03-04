## LAB 05

* Create a simple menu
```
1. Input student info
2. Find Student by ID
0. Exit!
```

* Input student info: Name and ID
* Find Student by ID: [Name, ID], Student with ID ... not found!

## Data structure example 
```
Map<Integer, String> studentList = new HashMap<>();

int stuId = scanner.nextInt();
int stuName = scanner.nextLine();
studentList.put(stuId, stuName);

```