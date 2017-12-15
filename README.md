# Weekly-Assignment Day 1:
1. closure is simply defined as Function and a part of lexical scope.

function closures actually have 3 scopes a.Local b. Global and c. to its own scope.
with closures Global scope can be made local(private).

2. Lexical scope:
	The word "lexical" refers to the fact that lexical scoping uses the location where a variable is declared within the source code to determine where that variable is available. Nested functions have access to variables declared in their outer scope.
	
3. How to Create a closure
	by adding a function inside another function.
	Eg: function fullName(firstName){
					return function(lastName){
					return firstName + " " + lastName;
				};
			}
		var addName =  fullName("Santoshmai");
		var addOneMoreName = fullName("smorampudi");
	
	In the above example addName and AddOneMoreName are closures.
	They share the same function body definition, but store different lexical environments. In addName's lexical environment, 		firstName is Santoshmai, while in the lexical environment for addOneMoreNmae, firstName is smorampudi.
	
		The inner function has access not only to the outer function’s variables, but also to the outer function’s parameters. 				Note that the inner function cannot call the outer function’s arguments object, however, even though it can call the outer 		 function’s parameters directly.
	
	4. Closures store references to the outer function’s variables
		
			eg:function UpdateName () {
    		var myName = prompt("Please enter a name");
    		return {
        getID: function ()  {
            return UpdateName;
        		},
        setID: function (newName)  {
            // This inner function will change the outer function's variable anytime
            UpdateName = newName;
        	}
   		 }
		}
		var name1 = UpdateName (); 
		name1.getID(); 
		name1.setID(prompt("please enter a name to update your previous name")); 
		alert("your updated name is" +" " + name1.getID()); 
		
		They do not store the actual value. Closures get more interesting when the value of the outer function’s variable 			changes before the closure is called. 
		
# Weekly-Assignment Day @2 Prototypes in JS
Every JavaScript object has a prototype. The prototype is also an object.All JavaScript objects inherit their 
properties and methods from their prototype.

  The above files contains a POC on prototypes concept in JS 
  and a detailed document on prototypes, how many types of proytotyes how they are used.
