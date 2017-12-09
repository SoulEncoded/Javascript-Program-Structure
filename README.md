# Javascript Program Structure

This challenge will cover the lessons learned from Chapter 2 of the Eloquent Javascript Book [link](http://eloquentjavascript.net/02_program_structure.html). I recommend you to go ahead an read through the chapter yourself, but this tutorial will give you the bare essentials.

After this section you will finally be able to write something that can be called a program.

## Expressions and Statements

An expression is code that produces a value and statements is a single unit of code that can be executed.

for example: `!false;` is a statement and it has the expression `!false`

## Variables

In Javascript there is a keyword called `var`, this allows you to store data into variables.

for example: `var myName = "John Kim";`

Now if I want to access the string "John Kim" I can simply refer to the variable `myName`

for example: `console.log("hello my name is", myName);`

There are other keywords that allows your to store variables, such as `let` and `const` but we will go over that in another lesson.

## Keywords and Reserved Words

In Javascript there are a list of keywords that should not be used as variable names.

Here is the full list. You do not need to remember all of them right now.

`break case catch class const continue debugger
default delete do else enum export extends false
finally for function if implements import in
instanceof interface let new null package private
protected public return static super switch this
throw true try typeof var void while with yield`

All of these keywords are part of Javascript and they have specfic uses for them. For example we have used `typeof` multiple times in the previous challenge.

## Functions
functions are a very important concept in programming. Just think of functions as small programs that are packaged up and ready to be used.

The anatomy of a function is as follows:

`functionName (argument) { code goes here }`

you can then execute this function by invoking it with `()` for example `functionName()` would invoke the function.

Javascript also has a handful of built in functions that you can use. Actually we have already been using them in our previous challenges.

the `console.log(argument)` is a function that takes in a value and prints the value to the terminal.

Before we move on you should understand that not all functions are equal. Please take some time to understand the below two concepts.

- `pure functions`: a function that does not effect anything outside of itself

example:
```
pureFunc(arg) {
    return arg;
}
```

- `non pure functions`: a function that creates side effects and effects things outside of itself

example:
```
var count = 1;

nonPureFunc(arg) {
  count += 1;
  return arg;
}
```

Notice that no matter how many times the `pureFunc` is invoked the result and environment is the same. However, when we invoke the `nonPureFunc` multiple times, the `count` variable will increment in value every time.

## Return Values

Functions can output a value which is usually called return and the keyword `return` is used to denote the value that needs to be returned

## Control Flow

Imagine for a second if you had one statement after another and they executed in that order without repeating, branching, or looping. In this case you would call this a straight control flow. However, most programs do not follow this straight flow. The following sections describes ways to alter this control flow.

### Conditional Execution
In the conditional execution the program can choose between two Boolean based values.

Below is a simple conditional execution.

```
var age = 21;
if (age >= 21) {
  console.log('welcome to the bar');
} else {
  console.log('you are too young to come in');
}
```

In this example the program will only execute the statement inside the true condition. e.a. `console.log('welcome to the bar');` because the `age` value of 21 meets the conditional.

### While and Do Loops

While and Do Loops is one way for us to repeat execution of some segment of our program.

The loop will continue to repeat the segment of our code until a condition has been made. It is possible to be stuck in a infinite loop so be careful!

```
 var count = 0;
 while (count <= 10) {
   console.log('the count is', count);
   count += 1;
 }
```

The `do` loop is similar to the `while` loop but the `do` loop guarantees that it will execute it's body at least once before looping the body.

TODO: do while example

### For Loops

A `For` loop is similar to a while loop, but it requires a counter. Basically you are telling the program to execute the segment of the code until a certain count.

```
for (var i = 0; i <= 10; i++) {
  console.log ('the count is', i);
}
```

the `var i = 0` denotes the number to start the count, the `i <= 10` denotes the condition when the loop should stop, and finally the `i++` denotes the amount to count up by for each step.

NOTE: `i++` and `i += 1` is a short hand way of writing `i = i + 1`, also another thing to keep in mind is that you don't need to only update the count by one. For example you can go up by 3, `i += 3`;

### Break Statements
Sometimes you need to forcefully stop the loop before it meets its conditional statement. To do this we use the `break keyword`

```
for (var i = 0; i <= 10; i++) {
  console.log ('the count is', i);
  if (i === 5) {
    break;
  }
}
```

In the above example, the loop will stop execution once the `if` conditional statement has been met.

### Switch Statements

when you are using the `if` statements, sometimes the statements can get too long to manage. When this happens, you should use the `switch` statement. Switch statements are used when you have a condition that can be many different values and it needs to output different results.

```
var mood = 'happy'
switch (mood) {
  case "happy":
    console.log('time to go to work');
    break;
  case "gloomy":
    console.log('go work out');
    break;
  case "sad":
    console.log('call your mom');
  default:
    console.log('work on something amazing');
    break
}
```

Things to note for switch statements is that you need to add a `break`
statement after each `case` statement. also you need to a `default` case for when the value doesn't meet any of the other cases.

## Comments

Don't write fake comments. This is kinda of a joke but comments should be used sparingly as your code should read like well written pros. More on this later. Comments are denoted using the `//`

`// this is a comment`

You can also comment multiple lines by surrounding `/*` and `*/`

```
/*
 this is a multiple line comment.
 here is another line.
*/
```

## Challenges

### Loop Me

In this challenge we will practice control flows. Using any form of looping, console log a number from 0 to 100.

### FizzBuzz

FizzBuzz is one of the most famous interview questions. It is mainly used as a sanity check as someone who cannot solve this problem generally will raise red flags as someone who does not have a foundation understanding of programing.

The FizzBuzz Challenge from the Book:
Write a program that uses console.log to print all the numbers from 1 to 100, with two exceptions. For numbers divisible by 3, print "Fizz" instead of the number, and for numbers divisible by 5 (and not 3), print "Buzz" instead. Also for numbers that are divisible by both 3 and 5 print "FizzBuzz" instead.
