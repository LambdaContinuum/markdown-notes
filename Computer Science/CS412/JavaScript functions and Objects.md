## Built-in types
---
- There are seven built-in types in JS
	- string
	- number
	- boolean
	- null
	- undefined
	- object
	- symbol
- Most of these behave as expected, except for null.

## Symbol type
---
- Symbols let us generate a unique identifier
- The identifier can be used as keys in structures such as maps, or as a way to uniquely identify a label, such as in enumeration.
- Note that JS doesn't have an 'enum' operator as do other languages - we write enums either as strings or in objects.
- Symbols have quite a few properties and methods, but they don't seem to be in heavy use yet.

## undefined vs null
---
- Both are JavaScript primitives.
- An uninitialized variable will be 'undefined' until a value is set.
- A few other operations will result in an 'undefined' value.

- 'null' represents the absence of a value.

- `null == undefined` is true but `null === undefined` is false.

- Best practice: Use null to explicitly set an empty variable, and let JS handle undefined, even though they behave roughly the same.

- `typeof(undefined)` is "undefined"
- `typeof(null)` is "Object"
- `typeof()` returns a string

- That null has a type of "Object" was a bug in an early specification that was incorporated into ECMAScript, and there's so much code that relies on it, fixing the bug is worse than letting it go.

## JS functions
---
- Functions are similar to to other languages
- We can declare a named function
```javascript
function adder(left, right) {
	return left + right;
}
console.log(`foo is ${adder(30, 12)}`);
(interprolated string)
```
- Or declare a variable, then point it to a function.
```javascript
let adder2;
adder2 = function (left, right) {
	return left + right;
}

console.log(`${adder2(30, 12)}`);
```
- Note that const doesn't work for adder2 since const requires a definition.
- adder2 has the address of the first executable statement in the function.

## Using const
---
- I tend to define functions as const like this
```javascript
const adder2 = function (left, right) {
	return left + right;
}

console.log(`${adder2(30, 12)}`);
console.log(adder2(30,12));
```
- Only if using older syntax


## =>
---
- ES6 introduced new function definition syntax based on CoffeeScript.
- It's a little more succinct but functionally equivalent.
- It's named 'fat arrow'
```javascript
const adder3 = (left, right) => left + right;
console.log(`${adder3(30, 12)}`);
```
- coffeescript -> transpiler -> javascript
- If a function has a single arg, no () is required.
```javascript
const adder4 = left => left + 12; //implicit return
console.log(`${adder4(30)}`);
```
- No args? use ()
```javascript
const adder5 = () => 30 + 12;
/* 
or const adder5 = _ => 30 + 12;
*/
console.log(`${adder5(30)}`)
```

## multi-line and =>
---
- Functions with multiple lines use { and } to enclose the function body
```javascript
const adder6 = () => {
	const thirty = 30;
	const twelve = 12;
	return thirty + twelve;
}
console.log(`${adder6()}`);
```
- lower dash -> lodash

## Passing Lambdas
---
- Passing unnamed (lambda) functions is extremely common
- We typically use them to handle asynchronous events
- These are called **callbacks** when used this way
- A somewhat contrived example:
```javascript
const adder7 = (left, right, cb) => cb(left + right);

let result = adder7(15, 6,
				   sum => sum*2
				   )
console.log(result)
```

## Functions as arguments
---
- Functions are first-class objects in JS, so they can be treated like any variable.
- This means that we can pass a function
```javascript
const doMath = (value, decorator) => decorator(value);

let result = doMath(
	30,
	const decorator = val => val + 12
)
console.log(result);
```
- Like the decorator pattern
- or return a function
```javascript
const getOperation = operator => {
	switch (operator) {
		case '+':
			return (left, right) => left + right;
			break;
		case '-':
			return (left, right) => left - right;
			break;
		case '*': return left * right;
		default: return;
	}
}

let mathFunction = getOperation('-'):
console.log(mathFunction(30, 12))
```

