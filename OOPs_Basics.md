# OOPs Basics

Object Oriented Programming (OOP) is a programming model, not a programming language.
It focuses on data not on function/operation/procedure.

4 Pillers of OOP: Abstraction, Encapsulation, Polymorphism and Inheritance

## Abstraction
When we say Abstraction we talk about only what is relevant and leaving out unnecessary details.
It deals more at Design level.
It is of Externsic

Advantages:
Helps in simplifying the complexity of the system.
Increase in the level of abstraction makes system simpler and simpler.

Eg: When we talk about Vehicle, we say it can move, without worrying about how it moves, whether it moves on tyre, in sky or on water.

## Encapsulation
Binding together of data and operation in single unit.
It is also called a data hiding.
It hides internal structure. So the outside world don't see the internal data and doesn't change it directly. 
It deals more at implementation level.
It's intrensic.
By encapsulating, we hide implementation details, meaning we can change the implementation details without affecting clients.

Advantages:
Easy maintenance.

Eg:
//Team Object
Team team;

//won the match
team.won = true;
team.stamina += 10;
team.mood = 'GOOD';

If we do this outside the team class it cas be quite annoying & sometime can cause mistakes if we set incorrect values leaving syatem in inconsistent state. Suppose if we do like

//Team Object
Team team;

team.wonTheMatch();

void wonTheMatch(){
  this.won = true;
  this.stamina += 10;
  this.mood = 'GOOD';
}

By encapusulating we can perform all operation in one place. 
Usually we make all instance variables private and provide getters/setters for those instance methods.

BUT...

Making instance variables prvate and providing getters/setters != Encapsulation

Connsider below example of Stack

public class Stack {

  //Below instance varables, top and values are not required to be known outside the stack, 
  //So we dont provide getters/setters methods.
  //They are only needed to be used internally, with encapsulation we maintain internal structure.
  private int top = -1;
  private int[] values = new int[10];
  
  public void push(int val){
    values[top++] = val;
  }
  
  public int pop(){
    return values[top--];
  }
}

Another example it Collection class has size variable which is also not set from outside the collection, only it can be read only to know the size of the collection.

When writing getter/setter we need to ask question like:
  is variable for internal use only
  is it read only?
  
