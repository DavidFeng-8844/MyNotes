
## Defining Classes 

> The minimal class declaration 
```java
class _MyClass_ {
    // field, constructor, and 
    // method declarations
}
```

> We can add more info

```java
class _MyClass extends MySuperClass implements YourInterface_ {
    // field, constructor, and
    // method declarations
	}
```
means that `MyClass` is a subclass of `MySuperClass` and that it implements the `YourInterface` interface.


# Passing Info for a class 

> Arbitrary Number of Arguments
```java
public Polygon polygonFrom(Point... corners) {
    int numberOfSides = corners.length;
    double squareOfSide1, lengthOfSide1;
    squareOfSide1 = (corners[1].x - corners[0].x)
                     * (corners[1].x - corners[0].x) 
                     + (corners[1].y - corners[0].y)
                     * (corners[1].y - corners[0].y);
    lengthOfSide1 = Math.sqrt(squareOfSide1);

    // more method body code follows that creates and returns a 
    // polygon connecting the Points
}
```

> Passing Reference Data Type Arguments
Reference data type parameters, such as objects, are also passed into methods _by value_. This means that when the method returns, the passed-in reference still references the same object as before. _However_, the values of the object's fields _can_ be changed in the method, if they have the proper access level.
```java
public void moveCircle(Circle circle, int deltaX, int deltaY) {
    // code to move origin of circle to x+deltaX, y+deltaY
    //This would persist 
    circle.setX(circle.getX() + deltaX);
    circle.setY(circle.getY() + deltaY);
        
    // code to assign a new reference to circle
    circle = new Circle(0, 0);
}
```

# Objects

## Creating Objects
```java
Point originOne = new Point(23, 94);
```

Each of these statements has three parts (discussed in detail below):

1. **Declaration**: The code set in **bold** are all variable declarations that associate a variable name with an object type.
2. **Instantiation**: The new keyword is a Java operator that creates the object.
3. **Initialization**: The new operator is followed by a call to a constructor, which initializes the new object.

## Instantiating a Class
The new operator invokes the object constructor 
Instantiating = creating an object (when we create an object we create an instance of a class)
The new operator does not have to assign to a variable, it can be used directly in an expression: 
```java
int height = new Rectangle().height;
```


![[Pasted image 20240404121120.png]]
![[Pasted image 20240404121124.png]]

# More on Class

## Understanding Class Member

### Class Variable 

Fields that have the **static** modifier in their declaration are called static fields or class variables. They are associated with the class rather than with any object.
