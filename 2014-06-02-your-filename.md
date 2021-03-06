##  JavaScript Objects Part - I
The simple types of JavaScript are numbers, strings, booleans (true and false), null, and undefined.  All other values are objects, arrays are objects, functions are objects, regular expressions are objects, and, of course, objects are objects.

An object is a container of properties and functions, objects in JavaScript are class-free.

•**Properties** are **values** associated with objects. 

A property has a name and a value. A property name can be any string, including the empty string. A property value can be any JavaScript value except for undefined.

car.model = “Elantra”;	        //valid property <br/>
car[model] = “Elantra”;	       //valid property <br/>
myObject[“ “] = “some value”;  //even an empty string is a valid property


•	**Functions** are **actions** objects can perform.

car.start(); <br/>
car.drive();

## Object Concepts
### 1.	Object Literal
Object literals provide a very convenient notation for creating new object values. An object literal is a comma-separated list of name-value pairs wrapped in curly braces.

This is an empty object<br/>
var car = {};

Add properties<br/>
var car = {<br/>
	make: “Hyundai”,<br/>
    model: "Elantra",<br/>
	color: "Red",<br/>
	“seat-color”: “Black” <br/>
//Because of special characters double quotes are used.<br/>
};

Add a method<br/>
car.start = function () {<br/>
	//implementation<br/>
};

<br/>
### 2.	Object Retrieval
Properties of JavaScript objects can be accessed by wrapping a string expression in square brackets. If the string expression is a constant, and if it is a legal JavaScript name and not a reserved word, then the dot notation can be used instead.

car[“seat-color”]		//Black<br/>
car.make				//Hyundai

We can try to get any property from an object. There will be no error. But if the property does not exist, then undefined is returned.

car["body-color"] 		//undefined<br/>
car.mileage 			//undefined<br/>
car["CRUISE-CONTROL"] 	//undefined<br/>

The || operator can be used to fill in default values, this is just an OR operator, which works as null coalescing operator in JavaScript, car.mileage (i.e. undefined) OR 25. Since undefined is falsey value, 25 is output of the expression and it is assigned to mileage variable.

var mileage = car.mileage || 25;<br/>
var bodyColor = car["body-color"] || “unknown”;<br/>

If you try to retrieve values from undefined it will throw a TypeError exception. This is something similar to NULL.ToString() in C#. Since we tried to access property on undefined it threw exception. This can be handled using && operator.

car.exterier 				 //undefined <br/>
car.exterier.color			 //throw "TypeError" <br/>
car.exterier && car.exterier.color	 //undefined<br/>

<br/>
### 3.	Updating object

A value in an object can be updated by assignment. If the property name already exists in the object then property value is replaced:

car.model = “civic”;

If the object does not already have that property name then it gets added

car.mileage = 30;

<br/>
### 4.	Reference

In JavaScript objects are passed by reference, they are never copied. This means any modifications made to the passed object are being made to the original object and are not being made to a copy of that object.

var x = car;<br/>
x.model = “i20”;<br/>

//below cname is 'i20' because x and car are references to the same object<br/>
var cname = x.model<br/>

// x, y, and z each refer to a different empty object<br/>
var x = {}, y = {}, z = {};<br/>

//x, y, and z all refer to the same empty object<br/>
x = y = z = {};<br/>


Enter text in [Markdown](http://daringfireball.net/projects/markdown/). Use the toolbar above, or click the **?** button for formatting help.
