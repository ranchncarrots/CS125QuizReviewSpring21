# Week 5 quiz prep
**Disclaimer: This document is meant to supplement other studying materials, not replace them**<br>

### Concepts
   * Objects, objects, more objects
   <br></br>
   
   You can use a code playground on the CS 125 website to follow along and test the code! https://cs125.cs.illinois.edu/
   

# Conceptual Check
<br></br>
**Quiz Prep**:
<br>
Create a Person class with a String name and int age <br></br>
Do you understand the difference between an instance, a class, and an object?
<br></br>
What Does a constructor do? Do you understand how they work?
<br></br>
How many constructors can we have?
<br></br>
What are instance variables and methods?
<br></br>
If I make two objects of the same class will they operate independently?
<br></br>
How do we format our class names?
<br></br>
Do you know the difference between a public variable and a private one?
<br></br>
How do we make getters and setters in 125?
<br></br>

 # Practice Problems
 **I will add solutions after the quiz prep session Monday.**<br>

 
 1. You are responsible for what your class stores. All internal components of your class should be private. I will only explain how we interface with it and what we want it to do. Create a class called `` BabyDfa ``. You will make two methods one called ``insert`` which accepts one int argument either 0 or 1 and is void. The other called ``isTrue`` which returns a boolean and takes no arguments. If the last two times we called insert the arguments were a 1 followed by a 0 `` isTrue `` should return true, else return false. That doesnt make much sense so view the example below. (15 minutes)
 Ex:
``` Java
  BabyDfa mu = new BabyDfa();
  mu.isTrue(); //return false
  mu.insert(1);
  mu.isTrue(); // return false
  mu.insert(0);
  mu.isTrue(); //returns true
  mu.insert(0);
  mu.isTrue(); // returns false
```
 <details>
	<summary>Solution!</summary>
	
```java
public class BabyDfa {
  private int firstVar;
  private int secondVar;
  BabyDfa() {
    firstVar = -1;
    secondVar = -1;
  }
  public void insert(int arg) {
    firstVar = secondVar;
    secondVar = arg;
  }
 
  public boolean isTrue() {
    if (firstVar == 1 && secondVar == 0) {
      return true;
    }
    return false;
  }
}
```
</details>



  <br></br>
 2. Write a class called `` MPGLeft``. Its constructor should take in two values, the number of gallons of fuel left in a car as a double, and the miles per gallon the car gets also as an double. It should not have a default constructor. Your goal is to create a method `` milesDriven`` that takes in the number of new miles the car has driven and then returns the number of gallons we have left as a double. All internal components of your class should be private. (10 mintues)
   <br>
 <details>
	<summary>Solution!</summary>
	
 ```java
 class MPGLeft {
  private double gallonsLeft;
  private double milesPerGallon; //miles/gallon
  MPGLeft(double setGallonsLeft, double setMilesPerGallon) {
    gallonsLeft = setGallonsLeft;
    milesPerGallon = setMilesPerGallon;
  }
  double milesDriven(double miles) {
    //returns gallonLeft
    gallonsLeft = gallonsLeft - (miles / milesPerGallon); 
    return gallonsLeft; 
  }
}
MPGLeft test = new MPGLeft(20, 2);
System.out.println(test.milesDriven(4)); //18.0
System.out.println(test.milesDriven(4)); //16.0
 ```
</details>
<br>
3. Let us now have some fun with Objects and Imperative Programming.(10 minutes) <br>
a. Create an object called `` Position ``. It has no constructor and has one public variable called spot. <br>
b. Make an array of Position objects. For reference this can be done with ``Position[] blah = new Position[LENGTH]``. What is the value at each index?<br>
c. Initialize each index with a Position instance and set the spot variable with its the Instances index in the array.<br>
<br>
 <details>
	<summary>Solution!</summary>
  
 ```java
public class Position {
  public int spot; 
}
Position[] array = new Position[2];
//array[0] = new Position();
//array[0].spot = 0; 
//array[1] = new Position();
//array[1].spot = 0; 
//replace the above lines with a for loop
for (int i = 0; i < array.length; i++) {
  array[i] = new Position();
  array[i].spot = i; 
}
System.out.println(array[0].spot); //0
System.out.println(array[1].spot); //1
 ```
</details>

<br>
FeedBack: https://forms.gle/yJLaYFaBtthPf3AP6 
  



