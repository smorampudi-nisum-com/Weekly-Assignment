# Weekly-Assignment @day 3
Call() and Apply()
	Call()
    syntax
			function.call(thisArg, arg1, arg2, ...)
		Syntax Explaination:
			thisArg
				The value of this provided for the call to a function. Note that this may not be the actual value seen by the method: 
				if the method is a function in non-strict mode, null and undefined will be replaced with the global object and primitive 
				values will be converted to objects.(it is an optional argument	)
			arg1 and arg2 are optional arguments
		Return Value
			The result of calling the function with the specified this value and arguments.
	Explaination of this keyword:
		1. this refers to the global object whether in strict mode or not.
		2. The this keyword is a shorthand for referencing the containing object of a method.
		3. The this reference ALWAYS refers to (and holds the value of) an object—a singular object—and it is usually used inside
				a function or a method, although it can be used outside a function in the global scope. Note that when we use strict mode, 
				this holds the value of undefined in global functions and in anonymous functions that are not bound to any object.

		4. this is used inside a function (let’s say function A) and it contains the value of the object that invokes function A. We need 
			this to access methods and properties of the object that invokes function A, especially since we don’t always know the name of the 				invoking object, and sometimes there is no name to use to refer to the invoking object. Indeed, this is really just a shortcut 						reference for the “antecedent object”—the invoking object.
			
	Exampe for Call()
							var person = {
							firstName:"John",
							lastName: "Doe",
							fullName: function() {
									return this.firstName + " " + this.lastName;
							}
					}
					var myObject = {
							firstName:"Mary",
							lastName: "Doe",
					}
					x = person.fullName.call(myObject); 
					console.log(x); 

The expected output: Mary Doe

Apply()
	The apply() method calls a function with a given this value, and arguments provided as an array (or an array-like object).
syntax:
	func.apply(thisArg, [argsArray])
	
syntax explaination
	An array-like object, specifying the arguments with which func should be called, or null or undefined if no arguments should be 				provided to the function. Starting with ECMAScript 5 these arguments can be a generic array-like object instead of an array. See below 	 for browser compatibility information.
Return value:
	The result of calling the function with the specified this value and arguments.
Apply():
apply is very similar to call(), except for the type of arguments it supports. You use an arguments array instead of a list of arguments (parameters). With apply, you can also use an array literal, for example, func.apply(this, ['eat', 'bananas']), or an Array object, for example, func.apply(this, new Array('eat', 'bananas')).

You can also use arguments for the argsArray parameter. arguments is a local variable of a function. It can be used for all unspecified arguments of the called object. Thus, you do not have to know the arguments of the called object when you use the apply method. You can use arguments to pass all the arguments to the called object. The called object is then responsible for handling the arguments.

Prime Difference between Apply() and call():
	the syntax of this function is almost identical to that of call(), the fundamental difference is that call() accepts an argument list, while apply() accepts a single array of arguments.
	
