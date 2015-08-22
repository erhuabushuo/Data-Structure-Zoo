# 1: Object Oriented Programming

Note: This section has been pretty tricky to write, considering there's a lot of different skills levels reading
this. It will be reworked in the future.

![Imgur](http://i.imgur.com/AphDgOV.png)

Before we get started on object oriented programming a word of warning. Python's
ideas about Object Oriented programming differ quite a bit from Java's. First, because
Python is dynamically typed it doesn't require a strict type for an object you
declare. Unlike Java which has primitives such as int, bool, etc, everything in
Python is an object. The interpreter makes a guess as to the type at the time of
interpretation.

Now that's out of the way, let's dive right in. In the real world we break down
complex things like cars, houses, computers, into smaller parts that can be more
easily understood. This process of hiding the complexity of smaller parts is
called Abstraction and it's a central pillar of Software Engineering. The process
of hiding and organizing information within these abstract pieces is called
encapsulation. For sake of simplicity, we'll be sticking to Python's methodologies.

In general, the objects that we'll be creating have three main parts. State, which
is what variables the object encapsulates. Identity, which is how the object we
created is referred to as. Operations, methods which modify an object's state or
help other objects perform tasks.

In Python, everything is an object! These objects are generated by blueprints otherwise
known as Classes which are denoted by the ``class`` keyword. These essentially tell the
interpreter how to make the object and the functionality of that object. Take a look at
the source code in ``objects.py`` and you'll see a few examples. One keyword that you may
not be familiar with is the ``self`` keyword. This keyword is used to reference the current
object that a method is being called on. For your consideration:

```python
class Car(Vehicle):
    def __init__(self, name):
        super(Car, self).__init__(name)
        self.number_of_wheels = 4
```

Basically you'll see that the Car class inherits the Vehicle class. In the constructor
otherwise known as the ``__init__`` function, it sets the name using the super class
(Vehicle) constructor. It then goes to setup the number of wheels using the self variable
we mentioned earlier.

>>> import objects
>>> car = objects.Car('Ford')
>>> car2 = objects.Car('Lambolinguini')
>>> car.name = Tesla
>>> print car.name
Tesla

>>> print car.number_of_wheels
4
```


Let's talk some Python specifics. As I mentioned above we do things a bit differently
in Python from other languages. For instance Python has no keywords such as ``private``
``protected`` or ``public``. For example in the code included for this section
take a look at the ``MyObject`` class. If you're completely new to Python, this
syntax might be a bit strange. \_\_init\_\_? what's going on. In a nutshell ``__init__``
is the constructor (for our purposes ``__new__`` doesn't exist). So what about this
self variable all over the place? That's how the object refers to itself. In Java,
an object's functions have access to all the private member variables stored within.
In Python we do it to be explicit rather than implicit. The keyword self basically
separates the variables that we pass into our function and the state of our object.

Back to the simple MyObject class, we'll see that the variable ``my_member_variable``
is being assigned the string 'buh' using the self keyword. This member variable
is public! Consider the following.

```python
    obj = MyObject() # Instanciate my object
    var = obj.my_member_variable
```

Looks pretty simple right? The ``var`` variable is set to what we assigned our
variable internally. This is an example of how normal member variables are
automatically public.