## OOP

Well what is it? Obeject Oriented Programming.

Look at the world. It's full of Object. Like you and me. I am an object. A Hooman. A Boy. A Son. And many things at the same time. I have properties that change like age. I have behavior like I play football. I have constant. Like name.

All piece in chessboard is a piece. Or a object. And then theres black and white pieces. Then theres Pawn, and King.

The OOP has 4 fundamental. 🍀

1. Encapsulation
2. Abstraction
3. Inheritance
4. Polymorphism

Let's talk about them.

### Encapsulation: 📨

Let's say you want to send an email. You can just say

```python
mail.location = "OlllOOOOOLlllllo"
```

But this location might not exist. So instead of assigning directly we use method.

```python
Like mail.send("OlllOOOOOLlllllo")
```

So the idea of encapsuling the properties and methods inside the class itself is encapsulation. Instead of sharing property we share the method.

### Abstraction:

The knight can not move if the king is in check. And the knight can know if the king is in check with a getter method from king. It doesnot need to bother itself how that works. There's two concept in abstraction

- Interface
- Implementation

### Inheritance

If a class extends from other class it will inherit the property of that before class. And that is the concept of inheritance.

### Polymorphism

A class may have many morph. Thing of _Select_, _textBox_, _Input_ they all render with element.render() but the outlook is different. And this is polymorphism in a nutshell

========================

Concept implementation with Chess Board:

- Inherit postion, color from parent class
- Encapsulate the logic of piece move.
- Abstraction when the piece needs to know the king check before moving
- Polymorphism for the same move using different orientation
