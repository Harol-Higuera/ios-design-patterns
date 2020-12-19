
# Design Patterns For IOS Development

_This article is informative and does not have the purpose to strictly motivate developers to follow this patterns for the development of iOS applications. Neither to memorize the names mentioned in this article. However, it might be a good idea to understand them and considering using them for your particular problems._

### Types of Design Patterns.

1. **Structural**: Describe how objects are combined and composed to create complex structures. 
- MVC
- MVVM

2. **Behavioral**: Describe how objects communicate with each other.
- Delegation
- Strategy
- Observer

3. **Creational**: Describe how to create or instantiate objects.
- Builder
- Singleton
- Prototype

---
## Class Diagrams

As in this article, class diagrams are very useful for understanding Design patterns, so go through the require concepts that you already might be familiar with.

Class Diagrams include Classes, protocols, properties, methods and relationships.

Here is a class that we called Dog and a subclass SheepDog, in a class diagrams instead of saying _SheepDog inherits from Dog_ we can simply say _SheepDog is a Dog_. Makes sense right? The direction of the arrow defines de relationship. The arrows always point at the super class.

<img src="./resources/01.png" width="200"/> 

To indicate that a class has a property, we can use a plain arrow and it would be read as "has a". If there are multiple properties it could be read as "has one or more.."

<img src="./resources/02.png" width="200"/> 

Also, we could indicate multiple relationships in a single diagram.

<img src="./resources/03.png" width="200"/> 

Now, when we define a protocol, the right way would be adding a label "Protocol" surrounded by double brackets. 

<img src="./resources/04.png" width="200"/> 

This is the way we could add a class diagram to define a class that implements OR conforms to a protocol. 

<img src="./resources/05.png" width="200"/> 

But hold on. If we want to indicate "uses", we use a plain arrow and a dashed line. This is a relationship for **usage**, which means that indicates its purpose. 

<img src="./resources/06.png" height="120"/> 

We can add also add methods and properties in a class diagram.

<img src="./resources/07.png" height="200"/> 

Here it is a complete class diagram for a Farmer who has a SheepDog which is a Dog that delegates to the PetOwning object.

<img src="./resources/08.png" height="200"/> 

### Other Examples

1. Dog and Cat inherit from Animal, which defines an eat method.

<img src="./resources/09.png" height="200"/> 

2. Vehicle protocol has one Motor and one or more Wheel objects. Note that since the vehicle has one or more wheels an 1...* is added.

<img src="./resources/10.png" height="200"/> 

3. Professor is a teacher and conforms to a Person protocol. This is a bit ambiguous, so there could be two options. In the option 1 the Professor conforms to Person and Teacher also conforms to Person. In Option 2 Teacher does not conforms to Person.

Option 1 | Option 2
------------ | -------------
<img src="./resources/11.png" height="200"/>  | <img src="./resources/12.png" height="200"/> 

---
## MVC (Model-View-Controller)

The MVC separates data into 3 types:

<img src="./resources/13.png" height="200"/> 
<pre>
MVC is the Apple design pattern in the UIKit.
</pre>

- **Model**: Models hold onto application data. Usually Structs or simple classes.
- **Views**: Display visual elements and controls on the screen. Usually subclasses of UIView.
- **Controller**: Coordinates between Model and Views. Usually subclasses of UIViewController.

### Some rules
* Controllers are allowed to have strong properties for the Model or View so they can access directly.
* Controllers might have one or more Models and/or Views.
* Models and Views should not hold a strong reference of the ViewController. Instead Model communicate to the Controllers through Property Observers and Views communicate to Controller by IBActions.





