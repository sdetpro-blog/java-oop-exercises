Credit: **[Nguyen Thinh Khang](https://github.com/thinhkhang97) (Dev)**, in Selenium K1 for contributing the exercise.
This is the first simple version racing contest problem.

## Racing animal simple version
* Horse: Max 75 km/h
* Tiger: Max 100 Km/h
* Dog: Max 60 KM/h

---
* Create an Animal class with a method speed() which return a **random** speeds
* Create 3 objects for those 3 animal type
* Run and see which animal is winner for racing
* Bonus: Default name with Class variable

Format: `Winner is <Animal name>, with speed: <speed>`

Hints:
* Class name can get from: `object.getClass().getSimpleName();`
* int randomSpeed = new SecureRandom().nextInt(50);