- Racing animal with builder design pattern (adding attribute flyable)
- Eagle, Falcon, Tiger, Snake....

```
Animal tiger = new Animal.Builder().whithWings(false).....build();
Animal falcon = new Animal.Builder().whithWings(true).....build();
```

```
public Animal getWinner(List<Animal> animalList){
    List<Animal> raceableAnimals = gatAnimalRacer(animalList);
    
    // Logic to get winner
}
```