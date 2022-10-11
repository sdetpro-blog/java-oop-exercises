## Design
* ```MoveAble Interface``` has an abstract method as ```speed```
* ```FlyAble Interface``` has an abstract method as ```flyAble```

* Dog, Horse, Eagle, Falcon..., etc. Assuming those classes are irrelevant classes (NOT in IS-A relationship)

## Example:

```
public class Dog implements MoveAble, FlyAble
```

## Controller
* Get the winner out