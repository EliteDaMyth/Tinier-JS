# Table Of Contents

- [Table Of Contents](#table-of-contents)
  - [What is Javascript Golfing?](#what-is-javascript-golfing)
  - [Why and when should minified code be used?](#why-and-when-should-minified-code-be-used)
  - [Arguments](#arguments)
    - [Function Variable Arguments Shorthand](#function-variable-arguments-shorthand)
    - [Use one-letter positional arguments, in alphabetical order](#use-one-letter-positional-arguments-in-alphabetical-order)
    - [Test argument presence instead of length](#test-argument-presence-instead-of-length)
    - [Embed functionality within arguments](#embed-functionality-within-arguments)
    - [Reuse parenthesis of the function call](#reuse-parenthesis-of-the-function-call)
    - [`setInterval` and `setTimeout` hacks](#setinterval-and-settimeout-hacks)
  - [Variables](#variables)
    - [Declaring variables Shorthand](#declaring-variables-shorthand)
    - [Implicit Casting](#implicit-casting)
    - [Use placeholder arguments instead of `var`](#use-placeholder-arguments-instead-of-var)
    - [Re-use variables where possible](#re-use-variables-where-possible)
    - [Assign wherever possible](#assign-wherever-possible)
    - [Use an array to swap variables](#use-an-array-to-swap-variables)
    - [Choose small data format](#choose-small-data-format)
    - [Null, Undefined, Empty Checks Shorthand](#null-undefined-empty-checks-shorthand)
  - [Loops](#loops)
    - [Fancy For Loops](#fancy-for-loops)
    - [Combine nested for loops](#combine-nested-for-loops)
    - [JavaScript foreach Loop Shorthand](#javascript-foreach-loop-shorthand)
    - [Omit loop bodies](#omit-loop-bodies)
    - [Use `for` over `while`](#use-for-over-while)
    - [Use index presence to iterate arrays of truthy items](#use-index-presence-to-iterate-arrays-of-truthy-items)
    - [Use `for..in` with assignment to get the keys of an object](#use-forin-with-assignment-to-get-the-keys-of-an-object)
    - [Use reverse loops where possible](#use-reverse-loops-where-possible)
    - [Use both `for` body and counting expression for multiple operations](#use-both-for-body-and-counting-expression-for-multiple-operations)
    - [for..in will not iterate over false - use this to trigger iteration](#forin-will-not-iterate-over-false---use-this-to-trigger-iteration)
    - [Decimal base exponents](#decimal-base-exponents)
  - [Operators](#operators)
    - [Understand operator precedence](#understand-operator-precedence)
    - [Understand bitwise operator hacks](#understand-bitwise-operator-hacks)
    - [Assignment Operators Shorthand](#assignment-operators-shorthand)
    - [Use `~` with indexOf to test presence](#use--with-indexof-to-test-presence)
    - [Use `,` to chain expressions on one conditional line](#use--to-chain-expressions-on-one-conditional-line)
    - [Use `[]._` instead of `undefined`](#use-_-instead-of-undefined)
    - [Remove unnecessary space after an operator](#remove-unnecessary-space-after-an-operator)
    - [Double Bitwise](#double-bitwise)
  - [Numbers](#numbers)
    - [Integer division by the power of two](#integer-division-by-the-power-of-two)
    - [Math.floor()](#mathfloor)
    - [Use `~~` and `0|` instead of `Math.floor` for positive numbers](#use--and-0-instead-of-mathfloor-for-positive-numbers)
    - [Use `A + 0.5 | 0` instead of `Math.round` for positive numbers](#use-a--05--0-instead-of-mathround-for-positive-numbers)
    - [Use `AeB` format for large denary numbers](#use-aeb-format-for-large-denary-numbers)
    - [Use `A<<B` format for large binary numbers](#use-ab-format-for-large-binary-numbers)
    - [Use `1/0` instead of `Infinity`](#use-10-instead-of-infinity)
    - [Use division instead of `isFinite()`](#use-division-instead-of-isfinite)
    - [Exploit the "falsiness" of 0](#exploit-the-falsiness-of-0)
    - [Use `~` to coerce any non-number to -1](#use--to-coerce-any-non-number-to--1)
    - [Check if variables have the same sign](#check-if-variables-have-the-same-sign)
    - [Use `^` to check if numbers are not equal](#use--to-check-if-numbers-are-not-equal)
    - [Use number base for character to number conversion](#use-number-base-for-character-to-number-conversion)
    - [Use current date to generate random integers](#use-current-date-to-generate-random-integers)
  - [Strings](#strings)
    - [Prefer `slice` over `substr` over `substring`](#prefer-slice-over-substr-over-substring)
    - [Split using `''`](#split-using-)
    - [Split using 0](#split-using-0)
    - [Use the little-known `.link` method](#use-the-little-known-link-method)
    - [Use `.search` instead of `.indexOf`](#use-search-instead-of-indexof)
    - [Use `.replace` or `.exec` for powerful string iteration](#use-replace-or-exec-for-powerful-string-iteration)
    - [Use `Array` to repeat a string](#use-array-to-repeat-a-string)
    - [CharAt Shorthand](#charat-shorthand)
  - [Conditionals](#conditionals)
    - [If true … else Shorthand](#if-true--else-shorthand)
    - [If Presence Shorthand](#if-presence-shorthand)
    - [Short IF'z](#short-ifz)
    - [Avoid braces by using commas](#avoid-braces-by-using-commas)
    - [Lookup Tables Shorthand](#lookup-tables-shorthand)
    - [Comparison Returns](#comparison-returns)
    - [Use `&&` and `||` where possible](#use--and--where-possible)
    - [Switch Nightmare](#switch-nightmare)
    - [XOR Swap](#xor-swap)
    - [Toggle between two values](#toggle-between-two-values)
    - [Coercion to test for types](#coercion-to-test-for-types)
    - [Type-specific methods to test for types](#type-specific-methods-to-test-for-types)
  - [Arrays](#arrays)
    - [Test array length](#test-array-length)
    - [Use elision](#use-elision)
    - [Use coercion to do `.join(',')`](#use-coercion-to-do-join)
    - [String coercion with array literal ```[]```](#string-coercion-with-array-literal-)
    - [Use coercion to build strings with commas in them](#use-coercion-to-build-strings-with-commas-in-them)
    - [Use Arrays as Objects](#use-arrays-as-objects)
    - [Test if Array has Several Elements](#test-if-array-has-several-elements)
    - [Object Array Notation Shorthand](#object-array-notation-shorthand)
    - [Associative Array Notation Shorthand](#associative-array-notation-shorthand)
  - [Regular Expressions](#regular-expressions)
    - [RegExp Object Shorthand](#regexp-object-shorthand)
    - [Use shortcuts](#use-shortcuts)
    - [Denormalize to shorten](#denormalize-to-shorten)
    - [Don't escape](#dont-escape)
    - [`eval()` for a regexp literal can be shorter than `RegExp()`](#eval-for-a-regexp-literal-can-be-shorter-than-regexp)
    - [`eval()` around String.replace() instead of callback](#eval-around-stringreplace-instead-of-callback)
  - [Booleans](#booleans)
    - [Use `!` to create booleans](#use--to-create-booleans)
  - [Functions](#functions)
    - [Use Array-Access for repeat function calls](#use-array-access-for-repeat-function-calls)
    - [Shorten repetitive function calls](#shorten-repetitive-function-calls)
    - [Short Function Calling](#short-function-calling)
    - [Shorten function names](#shorten-function-names)
    - [Use named functions for recursion](#use-named-functions-for-recursion)
    - [Use named functions for saving state](#use-named-functions-for-saving-state)
    - [Omit `()` on `new` calls w/o arguments](#omit--on-new-calls-wo-arguments)
    - [Omit the `new` keyword when possible](#omit-the-new-keyword-when-possible)
    - [The `return` statement](#the-return-statement)
    - [Use the right closure for the job](#use-the-right-closure-for-the-job)
    - [Shorten functions with Arrow Declaration](#shorten-functions-with-arrow-declaration)
    - [One-liners](#one-liners)
    - [Embed functionality in function calls](#embed-functionality-in-function-calls)
  - [Delimiters](#delimiters)
  - [Minification and compression](#minification-and-compression)
  - [JavaScript coding competitions](#javascript-coding-competitions)
  - [Other resources](#other-resources)
  - [Sources for this list](#sources-for-this-list)

## What is Javascript Golfing?

Javascript golfing is the process of writing the smallest amount of javascript code to do something awesome. It tests your ability to reduce, reuse, and recycle for the purpose of achieving the tiniest footprint possible.

## Why and when should minified code be used?

The purpose of code golfing is to test one's abilities, during challenges. That said, you should not use techniques like this in your normal code, as it compromises readability. Ideally, you should only use these tricks during a challenge. 

## Arguments

### Function Variable Arguments Shorthand

Object literal shorthand can take a little getting used to, but seasoned developers
usually prefer it over a series of nested functions and variables.

```javascript
// Longhand
function myFunction(myString, myNumber, myObject, myArray, myBoolean) {
  // do something...
}

myFunction('String', 1, [], {}, true);

// Shorthand

function myFunction() {
  for (i = 0; i < arguments.length; i++) {
    console.log( typeof arguments[i] ); // Returns string, number, object, object, boolean
  }
}

myFunction('String', 1, [], {}, true);
```

### Use one-letter positional arguments, in alphabetical order

Since arguments will need to be as short as possible, and will likely be reused within their lifetime, it's best to treat them as positionals instead of trying to give them meaning through their name. While using one-letter names marginally aids readability for a single function, keeping a consistent approach helps readability across all functions.

```javascript
function(t,d,v,i,f){...} // before
function(a,b,c,d,e){...} // after
```

### Test argument presence instead of length

Use `in` to check whether a given argument was passed

```javascript
arguments.length>1||(cb=alert) // before
1 in arguments||(cb=alert)     // after
```

If only truthy arguments are of interest, you can even boil that down to

```javascript
arguments[0]&&(cb=alert)       // works only if arguments[0] coerces to true
```

### Embed functionality within arguments

Save delimiters by processing stuff within (unused) arguments

```javascript
a=b<<1+a;x(a,1); // before
x(a=b<<1+a,1);   // after
```

### Reuse parenthesis of the function call

There are some functions which take no argument, and obviously you can reuse the parentheses when calling them.

```javascript
((a=b.pop(),b.pop())+c+a); // before
(b.pop(a=b.pop())+c+a);    // after
```

If you're not sure if a function really takes no arguments, see if its ```.length``` is 0.

### `setInterval` and `setTimeout` hacks

Use strings instead of functions in setInterval and setTimeout.

```javascript
setInterval(function(){console.log("z")},100) // before
setInterval('console.log("z")',100) // after
```

`setInterval` and `setTimeout` default to the browser's fastest possible time interval (usually 1ms in most modern browsers) if the second argument is left out.

```javascript
setInterval('console.log("z")',1) // before
setInterval('console.log("z")') // after
```

[&uarr; Back to top](#table-of-contents)

## Variables

```javascript
var o = {}       // Object literal
var a = []       // New Array
var r = /.*/     // New Regex
var s = ''+0;    // Convert to string
var n = +'7';    // Convert to number (7)
var b = !!b;   // Converts to a boolean
var f = ~~3.434; // Same as Math.floor(3.434)
var g = -~3.434; // Same as Math.ceil(3.434)
var x = 5e3;     // Same as 5000
var c = c || z;  // Coalesce, if c is null then set it to z.
'abcde'[1];      // charAt shorthand, results in 'b'.
+new Date();     // Shorthand for (new Date()).getTime();
var a = x?y:z;   // Ternary operator, short for: var a;if(x){a=y;}else{a=z;}
!0      // Shorthand for true
!1      // Shorthand for false
void 0     // Shorthand for undefined
```

### Declaring variables Shorthand

It is sometimes good practice to including variable assignments at the beginning
of your functions. This shorthand method can save you lots of time and space
when declaring multiple variables at the same time.

```javascript
// Longhand
var x;
var y;
var z = 3;

// Shorthand
var x, y, z = 3;
```

### Implicit Casting

Don't check your types, just use them as they are. parseInt() costs 10 characters. If you need to cast out of a string, be creative:

```javascript
a='30';
b='10';
c = a + b; // failure
c = parseInt(a) + parseInt(b) // too long

c = -(-a-b); // try these
c = ~~a+~~b;
c = +a+ +b;
c = a- -b;
```

### Use placeholder arguments instead of `var`

Save bytes on the `var` declaration by putting placeholder arguments in the function declaration.

```javascript
function(a){var b=1;...} // before
function(a,b){b=1;...}   // after
```

Please be careful as sometimes `var` declaration is shorter. Take the right decision in each case.

```javascript
function(a,b,c,d){b=1;c=2;d=3;...} // before
function(a){var b=1,c=2,d=3;...}   // after
```

### Re-use variables where possible

Careful reuse of a variable that is no longer needed can save bytes.

```javascript
setTimeout(function(){for(var i=10;i--;)... }, a) // before
setTimeout(function(){for(a=10;a--;)... }, a)     // after
```

### Assign wherever possible

Since assignment returns the assigned value, perform assignment and evaluation at the same time to save bytes.

```javascript
a=this.localStorage;if(a){...} // before
if(a=this.localStorage){...}   // after
```

### Use an array to swap variables

An array can be used as a temporary placeholder to avoid declaring another variable.

```javascript
var a=1,b=2,c;c=a;a=b;b=c // before
var a=1,b=2;a=[b,b=a][0]  // after
var a=1,b=2;a=b^a^(b=a)   // after - not as useful, but can come in handy
```

Alternatively, for numbers you can save another two bytes:

```javascript
var a=1,b=2;a=[b,b=a][0]  // before
var a=1,b=2;a+=b-(b=a)    // after
```

### Choose small data format

Required data will often be represented as Array or Object. In many cases, these byte-hungry formats can be replaced by strings. The [Date.parse polyfill](https://gist.github.com/1053863) shows a great example of a conversion table that'd usually be an Object.

### Null, Undefined, Empty Checks Shorthand

When creating new variables sometimes you want to check if the variable your
referencing for it’s value isn’t null or undefined. I would say this is a very
common check for JavaScript coders.

```javascript
// Longhand
if (variable1 !== null || variable1 !== undefined || variable1 !== '') {
  var variable2 = variable1;
}

// Shorthand
var variable2 = variable1  || '';

// Browser Test:
//null value example
var variable1 = null,
variable2 = variable1  || '';

console.log(variable2); // output: '' (an empty string)

//undefined value example
var variable1 = undefined,
variable2 = variable1  || '';

console.log(variable2); // output: '' (an empty string)

//normal value example
var variable1 = 'hi there',
variable2 = variable1  || '';

console.log(variable2); // output: 'hi there'
```

[&uarr; Back to top](#table-of-contents)

## Loops

### Fancy For Loops

You can use the standard for loop in non-standard ways.

```javascript
for (a; b; c)

// is essentially equivalent to:
a;
while (b)
{
  ...
  c;
}
```

So a good trick is to write your code with a while loop, and then split it into the a,b,c parts in a for loop.

```javascript
// Examples
for(x=y=n;!z;x--,y++)z=i(x)?x:i(y)?y:0
for(a=b=1;b<n;c=a+b,a=b,b=c);
```

### Combine nested for loops

```javascript
// Before
for(i=5;i--;)for(j=5;j--;)dosomething(i,j)

// After
for(i=25;i--;)dosomething(0|i/5,i%5)
```

Example with different values for i/j

```javascript
// Before
for(i=4;i--;)for(j=7;j--;)dosomething(i,j)

// After
for(i=28;i--;)dosomething(0|i/7,i%7)
```

### JavaScript foreach Loop Shorthand

This little tip is really useful if you want plain JavaScript and hence can’t
use jQuery `$.each` or `Array.forEach()`.

```javascript
// Longhand
for (var i = 0; i < allImgs.length; i++)

// Shorthand
for (var i in allImgs)

// Shorthand for Array.forEach
function logArrayElements(element, index, array) {
  console.log('a[' + index + '] = ' + element);
}

[2, 5, 9].forEach(logArrayElements);
// logs: a[0] = 2, a[1] = 5, a[2] = 9
```

### Omit loop bodies

If you can perform all the logic you need within the conditional part of a loop, you don't need the loop body.

### Use `for` over `while`

`for` and `while` require the same number of bytes, but `for` gives you more control and assignment opportunity.

```javascript
while(i--){...} // before
for(;i--;){...} // after

i=10;while(i--){...} // before
for(i=10;i--;){...}  // after
```

FYI, the second argument to a for-loop can be omitted, too - it will only stop the loop if it returns anything false-y at all.

### Use index presence to iterate arrays of truthy items

When iterating over an array of objects that you know are truthy, short circuit on object presence to save bytes.

```javascript
for(a=[1,2,3,4,5],l=a.length,i=0;i<l;i++){b=a[i];...}
for(a=[1,2,3,4,5],i=0;b=a[i++];){...}
```

### Use `for..in` with assignment to get the keys of an object

```javascript
a=[];i=0;for(b in window)a[i++]=b // before
a=[];i=0;for(a[i++]in window)     // after
```

Coercion Hint: you can coerce the counter from an array: `i=a=[];for(a[i++]in window);`

### Use reverse loops where possible

If an array can be iterated reversely, it may save some bytes:

```javascript
for(a=0;a<x.length;a++)...     // before
for(a=x.length;a--;)...        // after
```

### Use both `for` body and counting expression for multiple operations

```javascript
for(i=3;i--;foo(),bar());   // before
for(i=3;i--;)foo(),bar();   // before
for(i=3;i--;bar())foo();    // after
```

### for..in will not iterate over false - use this to trigger iteration

If for..in encounters anything but an object (or string in any browser but ye olde IE), e.g. false or 0, it will silently continue without iteration.

```javascript
if(c)for(a in b)x(b[a]); // before
for(a in c&&b)x(b[a]);   // after
```

### Decimal base exponents

You may have seen this one around it’s essentially a fancy way to write without
the zeros. 1e7 essentially means 1 followed by 7 zeros – it represents a decimal
base (JS interprets as a float type) equal to 10,000,000.

```javascript
// Longhand
for (var i = 0; i < 10000; i++) { ... }

// Shorthand
for (var i = 0; i < 1e7; i++) {
```

You can use 1 and 0 to represent true and false. I’ve seen this used in
JavaScript game development in shorthand while loops. Note that if you use the
negative start your array may be in reverse. You can also use `while(i++ < 10)`
and you don’t have to add the `i++` later on inside the while.

```javascript
// Longhand
var i=0;
while (i<9) {
  //do stuff
  i++; //say
}

// Shorthand
var i=9;

// goes until i=0
while(i--) { ... }

// or

var i = -9;
// goes until i=0
while (i++) { ... }
```

[&uarr; Back to top](#table-of-contents)

## Operators

### Understand operator precedence

[This Mozilla page](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence) is an excellent resource to get started.

### Understand bitwise operator hacks

### Assignment Operators Shorthand

Assignment operators are used to assign values to JavaScript variables and no
doubt you use arithmetic everyday without thinking (no matter what programming
language you use Java, PHP, C++ it’s essentially the same principle).

```javascript
// Longhand
x = x + 1;
minusCount = minusCount - 1;
y = y * 10;

// Shorthand
x++;
minusCount --;
y *= 10;

x += y; // Result 15
x -= y; // Result 5
x *= y; // Result 50
x /= y; // Result 2
x %= y; // Result 0
```

### Use `~` with indexOf to test presence

```javascript
hasAnF="This sentence has an f.".indexOf("f")>=0 // before
hasAnF=~"This sentence has an f.".indexOf("f")   // after

// Longhand
if (str.indexOf(ndx) == -1) {
 // Char not found
}

// Shorthand
if (~str.indexOf(ndx)) {
 // Char not found.
}
```

### Use `,` to chain expressions on one conditional line

```javascript
with(document){open();write("hello");close()}
with(document)open(),write("hello"),close()
```

### Use `[]._` instead of `undefined`

`""._`, `1.._` and `0[0]` also work, but [are slower](http://jsperf.com/undefineds). `void 0` is faster than `undefined` but longer than the alternatives.

### Remove unnecessary space after an operator

Whitespace isn't always needed after an operator and may sometimes be omitted:

```javascript
typeof [] // before
typeof[]  // after
```

### Double Bitwise

The double bitwise trick provides us with some pretty nifty shorthand tricks.
Read more about it here: [Double bitwise NOT (~~)](http://james.padolsey.com/javascript/double-bitwise-not/).

```javascript
// Longhand
Math.floor(4.9) === 4  // true

// Shorthand
~~4.9 === 4  // true
```

[&uarr; Back to top](#table-of-contents)

## Numbers

### Integer division by the power of two

```javascript
// Longhand
Math.floor(x/2);

// Shorthand
x>>1;
```

### Math.floor()

```javascript
// Longhand
Math.floor(4.9); // 4

// Shorthand
4.9 | 0; // 4
~~4.9;   // 4
```

### Use `~~` and `0|` instead of `Math.floor` for positive numbers

Both of these operator combos will floor numbers (note that since `~` has lower precedence than `|`, they are not identical).

```javascript
rand10=Math.floor(Math.random()*10) // before
rand10=0|Math.random()*10           // after
```

If you are flooring a quotient where the divisor is a multiple of 2, a bit-shift-right will perform both operations in one statement:

```javascript
Math.floor(a/2) // before
a>>1            // after

Math.floor(a / 4) // before
a>>2            // after
```

### Use `A + 0.5 | 0` instead of `Math.round` for positive numbers

```javascript
Math.round(a) // before
a+.5|0        // after
```

Also, for negative number just change `+.5|0` to `-.5|0`

```javascript
Math.round(-a) // before
-a-.5|0        // after
```

### Use `AeB` format for large denary numbers

This is equivalent to `A*Math.pow(10,B)`.

```javascript
million=1000000 // before
million=1e6     // after
```

### Use `A<<B` format for large binary numbers

This is equivalent to `A*Math.pow(2,B)`.

```javascript
color=0x100000 // before
color=1<<20    // after
```

### Use `1/0` instead of `Infinity`

It’s shorter. Besides, division by zero gets you free internet points.

```javascript
[Infinity,-Infinity] // before
[1/0,-1/0]           // after
```

### Use division instead of `isFinite()`

Division of 1 by any finite number results nonzero "truthy" value.

```javascript
if(isFinite(a)) // before
if(1/a)         // after
```

### Exploit the "falsiness" of 0

When comparing numbers, it's often shorter to munge the value to 0 first.

```javascript
a==1||console.log("not one") // before
~-a&&console.log("not one")  // after
```

### Use `~` to coerce any non-number to -1

Used together with the unary `-`, this is a great way to increment numerical variables not yet initialized.

```javascript
i=i||0;i++ // before
i=-~i      // after
```

It can also be used to decrement a variable by flipping around the negation and complement:

```javascript
i=i||0;i-- // before
i=~-i      // after
```

### Check if variables have the same sign

```javascript
// Longhand
Math.sign(x) == Math.sign(y);

// Shorthand
(x ^ y) >= 0;
```

### Use `^` to check if numbers are not equal

```javascript
if(a!=123) // before
if(a^123) // after
```

### Use number base for character to number conversion

`parseInt(n, 36)` is not only a very small character to number conversion, it also has the added value of being case-insensitive, which may save a `.toLowerCase()`, like in [subzey's parseRoman function](https://gist.github.com/1040240).

### Use current date to generate random integers

As seen in [aemkei's Tetris game](https://gist.github.com/1672254#file_annotated.js).

If you need a random boolean (0 or 1):

```javascript
new Date&1 // Equivalent to Math.random()<0.5
```

If you need a random integer 0 <= n < 1337:

```javascript
new Date%1337 // Equivalent to Math.floor(Math.random()*1337))

i=0|Math.random()*100 // before
i=new Date%100 // after
```

This works because a Date is stored internally in JavaScript as the amount of milliseconds since an epoch, so the new Date is being coerced into 123somebignumber456 when you try to do integer math on it.
Of course, these "random" numbers really won't be as random, especially if you call them multiple times in quick succession, so keep that in mind.

_Note:_ Do not use in fast loops, because the milliseconds might not change!

[&uarr; Back to top](#table-of-contents)

## Strings

### Prefer `slice` over `substr` over `substring`

Prefer `slice(start,stop)` over `substr(start,length)` over `substring(start,stop)`. Omit the second parameter to fetch everything to the end of the string. Do not use negative positions. It may be shorter (e.g. `s.substr(-n)` fetches the last _n_ characters) but does not work in Internet Explorer (including version 9).

### Split using `''`

Use `s.split('')` to create a character array from a string. Unfortunately you can not use `s[i]` to access the characters in the string. This does not work in Internet Explorer (including version 9).

```javascript
var chars = 'loremipsum'.split('');
```

### Split using 0

Save two bytes by using a number as a delimiter in a string to be split.

```javascript
"alpha,bravo,charlie".split(",") // before
"alpha0bravo0charlie".split(0)   // after
```

### Use the little-known `.link` method

Strings have a built-in `.link` method that creates an HTML link.

```javascript
html="<a href='"+url+"'>"+text+"</a>" // before
html=text.link(url)                   // after
```

Strings also have several other methods related to HTML, as documented [here](http://www.hunlock.com/blogs/The_Complete_Javascript_Strings_Reference#quickIDX6).

### Use `.search` instead of `.indexOf`

First, because this RegExp implicit is 1 byte shorter, but you get the added value of coercion of undefined to /undefined/ instead of '' being matched at position zero.

**Warning:** This will fail when you search with an invalid regular expression. For example, ```'.'``` as ```/./``` matches any character, ```'+'``` as /+/ gives an error so you'd want to ensure you know what the value is.

### Use `.replace` or `.exec` for powerful string iteration

Since the `.replace` method can take a function as its second argument, it can handle a lot of iteration bookkeeping for you.

### Use `Array` to repeat a string

```javascript
for(a="",i=32;i--;)a+=0 // before
a=Array(33).join(0)     // after
```

### CharAt Shorthand

You can use the eval() function to do this but this bracket notation shorthand
technique is much cleaner than an evaluation, and you will win the praise of
colleagues who once scoffed at your amateur coding abilities!

```javascript
// Longhand
'myString'.charAt(0);

// Shorthand
'myString'[0]; // returns 'm'

### Use coercion to build strings with commas in them

Pretty useful for RGB declarations.

```javascript
"rgb("+(x+8)+","+(y-20)+","+z+")"; // before
"rgb("+[x+8,y-20,z]+")";            // after

"rgb(255,"+(y-20)+",0)";           // before
"rgb(255,"+[y-20,"0)"];            // after
```

[&uarr; Back to top](#table-of-contents)

## Conditionals

### If true … else Shorthand

This is a great code saver for when you want to do something if the test is true,
else do something else by using the ternary operator.

```javascript
// Longhand
var big;

if (x > 10) {
  big = true;
} else {
  big = false;
}

// Shorthand
var big = (x > 10) ? true : false;
```

If you rely on some of the weak typing characteristics of JavaScript, this can
also achieve more concise code. For example, you could reduce the preceding code
fragment to this:

```javascript
var big = (x > 10);

//further nested examples
var x = 3,
big = (x > 10) ? 'greater 10' : (x < 5) ? 'less 5' : 'between 5 and 10';

console.log(big); // "less 5"

var x = 20,
big = { true: x > 10, false : x< =10 };

console.log(big); // "Object {true=true, false=false}"
```

### If Presence Shorthand

This might be trivial, but worth a mention. When doing “if checks” assignment
operators can sometimes be ommited.

```javascript
// Longhand
if (likeJavaScript === true)

// Shorthand
if (likeJavaScript)

// Other Examples:
// If 'a' is NOT equal to true, then do something.
// Longhand
var a;

  if (a !== true) {
    // do something...
  }

// Shorthand
var a;

  if (!a) {
    // do something...
  }
```

### Short IF'z

If you have mutiple IF variable value comparisons you can simply ass them to
an array and check for presence. You could use $.inArray as an alternative.

```javascript
// Longhand
if(myvar == 1 || myvar == 5 || myvar == 7 || myvar == 22)  {
  console.log('ya');
}

// Shorthand
([1,5,7,22].indexOf(myvar) !=- 1) && alert('yeah baby!');
```

### Avoid braces by using commas

Shorter sentence when using commas (1 char saved).

```javascript
if (i<10) {m+=5;n-=3} // before
if (i<10) m+=5,n-=3;  // after
```

### Lookup Tables Shorthand

If you have code that behaves differently based on the value of a property, it
can often result in conditional statements with multiple else ifs or a switch
cases. You may prefer to use a lookup table if there is more than two options
(even a switch statement looks ugly!).

```javascript
// Longhand
if (type === 'aligator') {
  aligatorBehavior();
}
else if (type === 'parrot') {
  parrotBehavior();
}
else if (type === 'dolphin') {
  dolphinBehavior();
}
else if (type === 'bulldog') {
  bulldogBehavior();
} else {
  throw new Error('Invalid animal ' + type);
}

// Shorthand
var types = {
  aligator: aligatorBehavior,
  parrot: parrotBehavior,
  dolphin: dolphinBehavior,
  bulldog: bulldogBehavior
};

var func = types[type];
(!func) && throw new Error('Invalid animal ' + type); func();
```

### Comparison Returns

We’re no longer relying on the less reliable == as !(ret == undefined) could be
rewritten as !(ret) to take advantage of the fact that in an or expression,
ret (if undefined or false) will skip to the next condition and use it instead.
This allows us to trim down our 5 lines of code into fewer characters and it’s
once again, a lot more readable.

```javascript
// Longhand
if (!(ret == undefined)) {
 return ret;
} else{
 return fum('g2g');
}

// Shorthand
return ret || fum('g2g');
```

### Use `&&` and `||` where possible

These operators reduce the script size rather that using if statements like the ones in the examples.

```javascript
if(a)if(b)return c // before
return a&&b&&c     // after

if(!a)a=Infinity // before
a=a||Infinity    // after

if (p) p=q;  // before
p=p&&q;      // after

if (!p) p=q; // before
p=p||q;      // after
```

### Switch Nightmare

Everyone loves switch statements, *cough*. Here is how you might avoid switch
case syndrome.

```javascript
// Longhand
switch (something) {
  case 1:
    doX();
  break;

  case 2:
    doY();
  break;

  case 3:
    doN();
  break;
  // And so on...
}

// Shorthand
var cases = {
  1: doX,
  2: doY,
  3: doN
};

cases[something] && cases[something]();
```

### XOR Swap

```javascript
// Longhand
var a = 1;
var b = 2;
var tmp = a;
a = b;
b = tmp;

// Shorthand
var a = 1;
var b = 2;
a^=b, b^=a, a^=b;
```

### Toggle between two values

```javascript
Longhand
if (x == a) {
 x = b;
}
else if (x == b) {
 x = a;
}
// x = 1, a = 1, b = 2
// 1st run: x = 2
// 2nd run: x = 1
// 3rd run: x = 2
// 4th run: x = 1
// ...

// Shorthand
x = a ^ b ^ x;
```

### Coercion to test for types

Instead of using `typeof x=='string'`, you can use `''+x===x`.

Instead of using `typeof x=='number'`, you can use `+x===x`. `+x` will coerce x to a number or NaN, so if it is anything else but a number, this will turn false. **Warning:** If someone goes really crazy on the prototypes, this will probably fail.

Instead of using `typeof x=='function'`, you can use `/^f/.test(typeof x)`.

### Type-specific methods to test for types

Another way to test types is to check if type-specific methods are available.

Test the variable x with the shortest type specific method:

| Type | Test |
|------|------|
| String | x.big |
| Number | x.toFixed |
| Array | x.pop (x.map works on fewer browsers)|
| Function | x.call |
| textNode | x.data |

This technique is even faster than string comparison!

**Warning:** This will lead to wrong results if properties or methods with those names were added.

[&uarr; Back to top](#table-of-contents)

## Arrays

### Test array length

```javascript
if(array.length>1) // before
if(array[1])       // after
```

### Use elision

Array elision can be used in some cases to save bytes.

```javascript
[undefined,undefined,2] // before
[,,2]                   // after

// Note: Be mindful of elided elements at the end of the element list
[2,undefined,undefined] // before length is 3
[2,,]                   // after length is 2
```

You may notice that the ```undefined``` turns empty. In fact, when we coerce an array into a string, the ```undefined``` turns to empty string.

```javascript
b="";b+=x // before
b=[b]+x   // after
// Bonus: b=x+[b] uses same bytes as b=[b]+x, while b="";b=x+b uses one more byte over b="";b+=x.
```

Another exploitation is also useful:

```javascript
((b=[1,2][a])?b:'') // before
[[1,2][a]]          // after
```

### Use coercion to do `.join(',')`

You can use `''+array` instead of `array.join(',')` since the default separator of arrays is ",".

Warning: this will only work if the contents of the Array are true-ish (except false) and consist of Strings (will not be quoted!), Numbers or Booleans, Objects and Arrays within arrays may lead to unwanted results:

```javascript
''+[1,true,false,{x:1},0,'',2,['test',2]]
// "1,true,false,[object Object],0,,2,test,2"
```

### String coercion with array literal ```[]```

```javascript
''+1e3+3e7 // before
[1e3]+3e7  // after
```

### Use coercion to build strings with commas in them

```javascript
"rgb("+(x+8)+","+(y-20)+","+z+")"; // before
"rgb("+[x+8,y-20,z]+")";           // after
```

Or if the first or last values are static:

```javascript
"rgb(255,"+(y-20)+",0)"; // before
"rgb(255,"+[y-20,"0)"];  // after
```

### Use Arrays as Objects

When you need to return an Object, re-use an already declared Array to store properties. An Array is of type 'object', after all. Make sure the field names don't collide with any of Array's intrinsic properties.

### Test if Array has Several Elements

You can write `if(array[1])` instead of `if(array.length > 1)`.

**Warning:** This doesn't work when the item `array[1]` is falsy! So only use it when you can be sure that it's not. You can use `if(1 in array)` in that case.

### Object Array Notation Shorthand

Useful way of declaring small arrays on one line.

```javascript
// Longhand
var a    = new Array();
a[0] = 'myString1';
a[1] = 'myString2';
a[2] = 'myString3';

// Shorthand
var a = ['myString1', 'myString2', 'myString3'];
```

### Associative Array Notation Shorthand

The old school way of setting up an array was to create a named array and then
add each named element one by one. A quicker and more readable way is to add
the elements at the same time using the object literal notation. Please note
that Associative Array are essentially JavaScript Objects with properties.

```javascript
// Longhand
var skillSet = new Array();
skillSet['Document language'] = 'HTML5';
skillSet['Styling language'] = 'CSS3';
skillSet['Javascript library'] = 'jQuery';
skillSet['Other'] = 'Usability and accessibility';

// Shorthand
// Don’t forget to omit the final comma otherwise certain
// browsers will complain (not naming any names, IE).
var skillSet = {
  'Document language': 'HTML5',
  'Styling language': 'CSS3',
  'Javascript library': 'jQuery',
  'Other': 'Usability and accessibility'
};
```

[&uarr; Back to top](#table-of-contents)

## Regular Expressions

### RegExp Object Shorthand

Example to avoid using the RegExp object.

```javascript
// Longhand
var regex  = new RegExp('\d+(.)+\d+','igm'),
    result = regex.exec('padding 01234 text text 56789 padding');

    console.log(result); // '01234 text text 56789'

// Shorthand
var result = /d+(.)+d+/igm.exec('padding 01234 text text 56789 padding');

  console.log(result); // '01234 text text 56789'
```

### Use shortcuts

`\d` is short for `[0-9]` and `\w` is short for `[A-Za-z0-9_]`. `\s` matches whitespace. Upper case shortcuts are inverted, e.g. `\D` matches non-digits. You can use these shortcuts inside character classes, e.g. `[\dA-F]` matches hex characters.

`\b` does not match a character but a word boundary where a word and a non-word character met (or vice versa). `\B` matches everywhere except at word boundaries. Some other shortcuts do _not_ work, e.g. `\Q...\E`. For a full list check the ECMA column in the [Regular Expression Flavor Comparison](http://www.regular-expressions.info/refflavors.html).

`/a|b/` is the same as `/(a|b)/`.

Sometimes it's shorter to use `<.*?>` (ungreedy matching) instead of `<[^>]*>` to match (for example) an HTML tag. But this may also change the runtime and behavior of the regular expression in rare cases.

In the replacement string, `$&` refers to the entire match and ``$` `` and `$'` refer to everything before and after the match, so `/(x)/,'$1'` can be replaced with `/x/,'$&'`.

### Denormalize to shorten

While `/\d{2}/` looks smarter, `/\d\d/` is shorter.

### Don't escape

In many cases almost no escaping (with `\`) is needed even if you are using characters that have a meaning in regular expressions. For example, `[[\]-]` is a character class with the three characters `[`, `]` (this needs to be escaped) and `-` (no need to escape this if it's the last character in the class).

### `eval()` for a regexp literal can be shorter than `RegExp()`

Prefer `/\d/g` over `new RegExp('\\d','g')` if possible. If you need to build a regular expression at runtime, consider using `eval()`.

```javascript
// we escape the first curly bracket so if `p` is a number it won't be
// interpreted as an invalid repetition operator.
r=new RegExp("\\\\{"+p+"}","g") // before
r=eval("/\\\\{"+p+"}/g")    // after
```

### `eval()` around String.replace() instead of callback

If a callback is used to achieve a certain effect on the output, one can use replace to build the expression that achieves the same effect and evaluate it (the more complicated the matches are, the less this will help):

```javascript
x.replace(/./,function(c){m=m+c.charCodeAt(0)&255})  // before
eval(x.replace(/./,'m=m+"$&".charCodeAt(0)&255;'))   // after
```

[&uarr; Back to top](#table-of-contents)

## Booleans

### Use `!` to create booleans

`true` and `false` can be created by combining the `!` operator with numbers.

```javascript
[true,false] // before
[!0,!1]      // after
```

Boolean coercion can be useful, too. If coerced to Number (e.g. by prefixing a +), true will coerce to 1, false to 0. So a program that will test one condition to output 2 and another one to output 1 and 0 if none is met, can be reduced:

```javascript
x>7?2:x>4?1:0 // before
+(x>7)+(x>4)  // after
```

One way that minifiers are able to shave bytes off of JavaScript code is changing the way booleans are used, from David Walsh [blog](http://davidwalsh.name/javascript-booleans):

```javascript
true === !0 // before, save 2 chars
false === !1 // after, save 3 chars
```

[&uarr; Back to top](#table-of-contents)

## Functions

### Use Array-Access for repeat function calls

This is definitely a balancing act between variable/function name length and number of invocations. Instead of calling a.longFunctionName() twice, it's shorter to save the name and call the function via array-access:

```javascript
a.longFunctionName(b)
a.longFunctionName(c)
//42

// vs

f='longFunctionName'
a[f](b)
a[f](c)
//34
```

this is especially effective with functions like document.getElementById which can be reduced to `d[e]()`.

Note:
For a single call, the relative cost is `8 + name.length` characters. Each subsequent call has a relative cost of 2 characters.
For standard invocation, all calls cost name.length characters. Use this method if `8 + name.length + (2 * invocations) < invocations * name.length`

`i = invocations len = minimum function length to get advantage`

```javascript
i | len
=======
1 |  ∞
2 | 12
3 |  7
4 |  6
5 |  5
6 |  4
```

### Shorten repetitive function calls

Saves lot of chars when the script contains many function calls. 20 chars shorter in the second example.

```javascript
i=[Math.random()*2,Math.random()*3,Math.random()*4); // before
r=Math.random;i=[r()*2,r()*3,r()*4];                 // after

i=Math.cos(10)*Math.cos(20)*Math.cos(30);
j=Math.sin(10)*Math.sin(20)*Math.sin(30);
k=Math.random(10)*Math.random(20)*Math.random(30);    // before

with(m=Math)C=cos,S=sin,R=random;
i=m.C(10)*m.C(20)*m.C(30);
j=m.S(10)*m.S(20)*m.S(30);
k=m.R(10)*m.R(20)*m.R(30);                            // after
```

### Short Function Calling

Just like #1 you can use ternary operators to make function calling shorthand
based on a conditional.

```javascript
// Longhand
function x () {
  console.log('x');
};

function y () {
  console.log('y');
};

var z = 3;
if (z == 3) {
  x();
} else {
  y();
}

// Shorthand
(z == 3 ? x:y)();
```

### Shorten function names

Assign prototype functions to short variables. This may also be faster in more complex cases.

```javascript
a=Math.random(),b=Math.random() // before
r=Math.random;a=r(),b=r()       // after
```

### Use named functions for recursion

Recursion is often more terse than looping, because it offloads bookkeeping to the stack.

### Use named functions for saving state

If state needs to be saved between function calls, name the function and use it as a container.

```javascript
function(i){return function(){console.log("called "+(++i)+" times")}}(0) // before
(function a(){console.log("called "+(a.i=-~a.i)+" times")})           // after
0,function a(){console.log("called "+(a.i=-~a.i)+" times")}           // another alternative
```

### Omit `()` on `new` calls w/o arguments

`new Object` is equivalent to `new Object()`

```javascript
now = +new Date() // before
now = +new Date   // after
```

### Omit the `new` keyword when possible

Some constructors don't actually require the `new` keyword.

```javascript
r=new RegExp(".",g) // before
r=RegExp(".",g)     // after

l=new Function("x","console.log(x)") // before
l=Function("x","console.log(x)")     // after
```

### The `return` statement

When returning anything but an expression starting with an alphanumeric character, there’s no need to use a space after `return`:

```js
return ['foo',42,'bar']; // before
return['foo',42,'bar'];  // after
return {x:42,y:417}; // before
return{x:42,y:417};  // after
return .01; // before
return.01;  // after
```

### Use the right closure for the job

If you need to execute a function instantly, use the most appropriate closure.

```javascript
;(function(){...})() // before
new function(){...}  // after, if you plan on returning an object and can use `this`
!function(){...}()   // after, if you don't need to return anything
```

### Shorten functions with Arrow Declaration

This is most useful with multiple function calls. However, both parameters must be strings, which may be a good or bad thing, so use this wisely.

```javascript
function a(a){return a}
function b(b){return b}
function c(c){return c} //before

var a = a => a;
var b = b => b;
var c = c => c; //after
```

### One-liners

Save on brackets by shoving as much as possible into single lines, or parameters:

```javascript
a(realParam1, realParam2, fizz='buzz')
```

### Embed functionality in function calls

Save chars by processing stuff within (unused) arguments.

```javascript
i=j<<1+i;x(i,1); // before
x(i=j<<1+i,1);   // after
```

[&uarr; Back to top](#table-of-contents)

## Delimiters

Only use `;` where necessary. Encapsulate in other statements if possible, e.g.

```javascript
x=this;a=[].slice.call(arguments,1); // before
a=[x=this].slice.call(arguments,1);  // after
```

[&uarr; Back to top](#table-of-contents)

## Minification and compression

- [RegPack](http://siorki.github.io/regPack.html)
- [JS Crush](http://www.iteral.com/jscrush/)
- [Google Closure Compiler](http://closure-compiler.appspot.com/home)
- [UglifyJS](http://marijnhaverbeke.nl/uglifyjs)
- [JS Compress](http://jscompress.com/)

[&uarr; Back to top](#table-of-contents)

## JavaScript coding competitions

- [JS1k](http://js1k.com/)
- [js13kGames](http://js13kgames.com/)

[&uarr; Back to top](#table-of-contents)

## Other resources

- [Suggested Closure Compiler optimizations](http://code.google.com/p/closure-compiler/issues/detail?id=36)
- [StackExchange Codegolf](http://codegolf.stackexchange.com/questions/2682/tips-for-golfing-in-javascript)

## Sources for this list

Most of the tips, if not all, are gathered from stack overflow code golf threads.
