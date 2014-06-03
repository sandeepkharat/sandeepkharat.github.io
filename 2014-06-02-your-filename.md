##  JavaScript Objects Part - I
The simple types of JavaScript are numbers, strings, booleans (true and false), null, and undefined.  All other values are objects, arrays are objects, functions are objects, regular expressions are objects, and, of course, objects are objects.

An object is a container of properties and functions, objects in JavaScript are class-free.
•**Properties** are **values** associated with objects. 

A property has a name and a value. A property name can be any string, including the empty string. A property value can be any JavaScript value except for undefined.
car.model = “Elantra”;	        //valid property <br/>
car[model] = “Elantra”;	       //valid property <br/>
myObject[“ “] = “some value”;  //even an empty string is a valid property

•	**Functions** are **actions** objects can perform.
car.start(); 
car.drive();

## Object Concepts
### 1.	Object Literal
Object literals provide a very convenient notation for creating new object values. An object literal is a comma-separated list of name-value pairs wrapped in curly braces.
This is an empty object
var car = {};

Add properties
var car = {
	make: “Hyundai”,
model: "Elantra",
	color: "Red",
	“seat-color”: “Black” 
//Because of special characters double quotes are used.
};

Add a method
car.start = function () {
	//implementation
};

### 2.	Object Retrieval
Properties of JavaScript objects can be accessed by wrapping a string expression in square brackets. If the string expression is a constant, and if it is a legal JavaScript name and not a reserved word, then the dot notation can be used instead.
car[“seat-color”]		//Black
car.make				//Hyundai
We can try to get any property from an object. There will be no error. But if the property does not exist, then undefined is returned.
car["body-color"] 		//undefined
car.mileage 			//undefined
car["CRUISE-CONTROL"] 	//undefined

The || operator can be used to fill in default values, this is just an OR operator, which works as null coalescing operator in JavaScript, car.mileage (i.e. undefined) OR 25. Since undefined is falsey value, 25 is output of the expression and it is assigned to mileage variable.
var mileage = car.mileage || 25;
var bodyColor = car["body-color"] || “unknown”;

If you try to retrieve values from undefined it will throw a TypeError exception. This is something similar to NULL.ToString() in C#. Since we tried to access property on undefined it threw exception. This can be handled using && operator.
car.exterier 				 //undefined 
car.exterier.color			 //throw "TypeError" 
car.exterier && car.exterier.color	 //undefined

### 3.	Updating object

A value in an object can be updated by assignment. If the property name already exists in the object then property value is replaced:
car.model = “civic”;

If the object does not already have that property name then it gets added
car.mileage = 30;

### 4.	Reference

In JavaScript objects are passed by reference, they are never copied. This means any modifications made to the passed object are being made to the original object and are not being made to a copy of that object.
var x = car;
x.model = “i20”;

//below cname is 'i20' because x and car are references to the same object
var cname = x.model

// x, y, and z each refer to a different empty object
var x = {}, y = {}, z = {};

//x, y, and z all refer to the same empty object
x = y = z = {};


Enter text in [Markdown](http://daringfireball.net/projects/markdown/). Use the toolbar above, or click the **?** button for formatting help.
