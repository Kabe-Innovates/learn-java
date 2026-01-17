Yeah, even though I practiced OOP with Python back in my 1st sem, I'm planning to start again from the basics.
## Objects
- When ever I try to learn these topics, I came to hear these two magic words
	1. State
	2. Behavior
- Object is a ==bundle of state and behavior==
- **States** are stored in variables and **Behavior** is stored in methods.
- ### Example
	 - Dog 
		 1. State : name, color, breed
		 2. Behavior : bark(), shakeTail()
	- Mobile Phone
		1. State : model, color, spec
		2. Behavior : dialNumber(), receiveCall(), volumeUp() 
- Methods are nothing but functions which used to change the state.
- Following are the benefits of implement Objects 
	1. Modularity
	2. Code Re-Use
	3. Information Hiding
	4. Pluggability and Debugging ease
## Class
- A class is a blueprint for creating an individual objects.
- Multiple objects (instances) can be created from the same class.
- A class does not need a main() function
- Object creation and other usage were handled by other classes.
- Example:
	```java
	// Defining Class
	class Bicycle{
		int speed = 0;
		int gear = 0;
		
		void changeGear(int newValue) {
		gear = newValue;
		}
		
		void changeSpeed(int newValue) {
		gear = newValue;
		}
	}
	
	// Object Creation and defining main() function
	
	class BicycleDemo {
		public static void main(String[] args){
			// Creating two different Bicycles
			Bicycle bike1 = new Bicycle();
			Bicycle bike2 = new Bicycle();
			
			// Invoke methods
			bike1.changeGear(2);
			bike1.changeSpead(30);
			bike2.changeGear(2);
			bike2.changeSpead(25);
		}
	}
	
	// Here Bicycle is Class and 
	// bike1 and bike2 are Objects :)
	```
## Inheritance
- A subclass can be created from a super-class in which the subclass inherits the properties of super-class and also the members which makes the subclass unique
- Multiple sub-classes can be created from a super-class.
- In java, all sub-classes are allowed to have only one super-class and a super-class can have any number of sub-classes
- in java the syntax of creating the sub-class we have to declare the beginning of the class declaration using the `extend` keyword followed by the name of the class it inherits.
- Example:
	```java
	class MoutainBike extends Bicycle {
	// new fields and method defining
	}
	```

## Interface
- Interface defines what an object do.
- In simple terms it is a set of rules which must be defines when creating a sub-class, if you failed to do so, it raises an error.
- It is simply the behavior but not the implementation and forces to follow the same contract
- Example :
	```java
	interface VoiceControl {
		void volumeUp();
		void volumeDown();
	}
	
	class MobilePhone implements VoiceControl {
		int volume = 5;
		
		void volumeUp(){
		volume++;
		}
		
		void volumeDown(){
		volume--;
		}
	}
	```
- Here I have to add public keyword but I have to know the reason why I need to do so, So I skips it now.

Next to start with [[Basic Syntax - Java]]

