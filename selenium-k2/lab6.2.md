## lab 6.2
* Class Animal: flyAble 
* Eagle, Falcon, Snake....

* Applicable: !flyAble
* Builder Design Pattern
* --> Winner

```
final int TIGER_MAX_SPEDD = 100;
final int FALCON_MAX_SPEDD = 100;
Builder builder = new Builder();
Animal tiger =
        builder.flyAble(false).withSpeed(new SecureRandom.nextInt(TIGER_MAX_SPEDD));

Animal falcon =
        builder.flyAble(true).withSpeed(new SecureRandom.nextInt(FALCON_MAX_SPEDD));

// Controller

```