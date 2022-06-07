## LAB 7.1
- Create a class Employee with a method salary to return employee’s salar
- There are 2 types of employee: Full time employee and contract employee
- Full time employee has salary is 50000 and contract employee has salary 40000
- Write a method to accept a list of Employee and calculate total salary
- For example, company has 3 FTE and 2 contractor

## LAB 7.2
Credit: **Nguyen Thinh Khang (Dev)**, in Selenium K1 for contributing the exercise.
* This is the first simple version racing contest problem.
## Racing animal simple version* 
* Horse: Max 75 km/h
* Tiger: Max 100 Km/h
* Dog: Max 60 KM/h*
---
* Create an Animal class with a method speed() which return a **random** speeds
* Create 3 objects for those 3 animal type
* Run and see which animal is winner for racing
* Bonus: Default name with Class variable
* Format: `Winner is <Animal name>, with speed: <speed>`
* Hints:* * Class name can get from: `object.getClass().getSimpleName();`
* ```int randomSpeed = new SecureRandom().nextInt(50);```