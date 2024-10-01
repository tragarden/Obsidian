# Python Classes

Classes in Python could be compared to the analogy of a recipe. While making a cake, the core ingredients ratio will be the same no matter what cake you are making, but the icing and toppings will be different.

This is how you could think of a class. It is a predefined object of a specific type that is produced the same way each time, and then modified per scenario.

Classes use the CapWords naming convention, MeaningThatTheyUseThisFormat.

### Cake Class

>class DreamCake:
>	# Measurements are in grams or units
>	eggs = 4
>	sugar = 300
>	milk = 200
>	butter = 50
>	flour = 250
>	baking_soda = 20
>	vanilla = 10
>	
>	topping = none
>	garnish = none
>	
>	is_baked = False
>	
>	def \_\_init\_\_(self, topping='No topping', garnish='No garnish'):
>		self.topping = topping
>		self.garnish = garnish
>		
>	def bake(self):
>		self.is_baked = True
>		
>	def is_cake_ready(self):
>		return self.is_baked

\_\_init\_\_ is what is known as a 'Magic Method', which is beyond the scope of this module.

Using the class created in the code above, we can now set variables for the different variations of cake we might want:

Plain cake:

>plain_cake = DreamCake()

Chocolate cake:

>chocolate_cake = DreamCake(topping='Chocolate Frosting)

Luxury cake:

>luxury_strawberry_cake = DreamCake(topping='Strawberry Frosting', garnish='Chocolate Bits')

You can also use this class without specifying the named parameters:

>luxury_strawberry_cake = DreamCake('Strawberry Frosting', 'Chocolate Bits')

### Calling the Function

Now that we have observed how the class is utilized, we can call a function that includes the class.

To bake a chocolate cake in the sense of the code written, use the following:

>chocolate_cake = DreamCake(topping='Chocolate Frosting')
>
>chocolate_cake.bake()    # call the bake function on the object
>is_cake_done = chocolate_cake.is_cake_ready()
>
>print(is_cake_done)     # Prints 'True' since 'bake' has been called

This is a basic style used in Object Oriented Programming ( #OOP).

### Magic Methods

Magic Methods are default methods that can be implemented in all classes. Class hierarchy in Python means that all classes inherit from a base class known as 'object'. For more information search 'Python class inheritance'. Simply put, it means that a class will inherit it's type, functions, and internal variables. This default features allows classes to be compared or represented as strings.

Here is an example of overriding magic methods in IDLE using the \_\_str\_\_ magic method:

>class Circle:
>	def \_\_init\_\_ (self, radius):
>		self.radius = radius'
>		
>	def \_\_str\_\_(self):
>		return f'Circle(r={self.radius})'
>		
>my_circle = Circle(5)
>str(my_circle)

Output:
>'Circle(r=5)'

If we did not override the \_\_str\_\_ function, the output would not be as straightforward:

Output:
>'<\_\_main\_\_.Circle object at 0x022FFb98>'

This means that within IDLE, the Circle object is located at the memory address: 0x022FFb98.

The two magic methods \_\_enter\_\_ and \_\_exit\_\_ allow us to create classes that can use the 'with' keyword:

>class Foo():
>
>	def \_\_enter\_\_(self):
>		print("Enter...")
>		
>	def \_\_exit\_\_(self, type, value, traceback):
>		print("...and exit.")

The above code does nothing but print a message to output. If we use the 'with' keyword, we can 'wrap' this boilerplate code around concrete code:

>with Foo():
>	print("Hello World")

Output:

>Enter...
>Hello World!
>...and exit.

If you have ever parsed files into Python, you have used these magic methods:

>with open('/path/to/file.txt', 'w') as file:

This can then be used to write to a file as follows:

>file.write('something')