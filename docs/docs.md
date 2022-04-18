# Boxlang Documentation

Boxlang is a language that is designed to be simple to use and implement while being versatile. 

# Comments

Boxlang also allows you to type comments, which are ignored by the interpreter and can be used to document your code.

Boxlang comments begin with a slash and an asterisk (  `/*`  ) and end with an asterisk and a slash (  `*/`  ). Comments will extend forever until an comment end (  `*/`  ) is encountered. This means that comments can extend across many lines by default.

```
/* Comments go
on forever
until this is seen -> */
```

# Outputing

Two functions can be used to add text to the output, `print` and `error`.

Note that the output may not always be shown in all applications where Boxlang is implemented.

## Print

Simply outputs something into the output.

```
print('Hello world!'); /* Outputs Hello world! into the console. */
```

Anything can be printed, including booleans and functions. When functions (**not the return value of the functions**) are printed, they give the code content of the function.

## Error

Outputs something into the output, and then ends the script. Usually, any text that is printed using the `error` are highlighted by the interpreter in some way, for example text being red.

```
error('This is an error!'); // Prints 'This is an error!' into the output, the stops the script
```

# Variables

Variables represent other data.

To create a variable, simply type the name of the variable, an equal sign, and the data the variable represents.

```
my_variable = 'I love Boxlang!';
```

Variables can only contain letters, numbers, and underscores (  `_`  ). They also cannot begin with a number.

Remember that to Boxlang, there is no difference between the variable and the data it represents. That means that where ever you can put values, booleans, or functions, you can variables.

Variables can store data of three types, values, booleans, or functions.

# Values

Values are data that can be numbers, text. **Values do not represent booleans; they are another type.**

All values are wrapped around quotation marks, including numbers. This might be different from other languages you have used, which do not wrap numbers with quotation marks.

Boxlang requires you to wrap all values with quotation marks as it is a weakly typed language, and so there isn't a large difference between numbers and text.

You can use both single quotes or double quotes for values. However, it is recommended that you use single quotes over double quotes.

Here are a few examples of values

```
'This is a value!';

'This is a value with numbers: 1337';

'Values can also only contain numbers.';

'123';

'and decimals!';

'69.420';
```

Values can also run across many lines.

```
'Values do not
have to be
on the same line!';
```

Let's say you want to use a single or double quote in a value, or you don't want to indicate a new line but don't want to seperate your value onto different lines. You can use escape characters to solve this problem.

Escape characters begin with a backslash (  `\`  ) and end with another character that indicates what the escape character represents.

Common escape characters include `\'`, which represents `'`, and `\n`, which represents a new line.

```
'Don\'t forget the backslash!'; /* Use of \' */

'Each\nword\nis\non\na\nnew\nline!'; /* Use of \n */
```

Remember that Boxlang sees all values as the same, and does not treat values differently. This means that a value with only numbers is exactly the same to a value with a mixture of text and numbers.

Boxlang does have built in functions that allow you to see if a value is only made up of text or numbers, or if the value is a mixture of text and numbers. You can find these functions, along with other functions that relate to values, in `value-module.md` in the `built-in-docs` folder.

## Storing Values

To store values inside of variables, simply type the variable name, an equals sign, and then the value.

```
my_variable = 'This value is stored inside a variable';
```

# Booleans

Booleans represent true and false values, and are one of the most important concepts in all programming languages.

Booleans are often used in if statements, which will be covered later.

Booleans begin with an exclaimation mark (  `!`  ) and has either a `t` or a `f` after the exclaimation mark.

`!t` represents `true`, while `!f` represents `false`.

```
!t; /* Represents true */
!f; /* Represents false */
```

## Storing Booleans

To store booleans inside a variable, simply type the variable name, an equals sign, and then the boolean.

```
true_variable = !t; /* This variable represents true */
```

# Functions

A function is a bunch of code, and is usually stored in variables so that it can be reused.

All statements in a function are wrapped with braces aka curly brackets (  `{ }`  ). After the ending brace, add starting and ending parentheses (  `( )`  )

Inside the braces can be whatever Boxlang code you want.

```
{
    print('Hello world!');
    print('This is inside a function!');
}();
```

Functions can also be stored in variables so that they can be reused.

```
my_function = {
    print('Hello world!')
    print('This is inside a stored function!')
}();
```

When you store a function inside a variable, that function is not automatically run. To run a function after you have stored it, you have to **call** the function.

To call a function, write the function name, and then parentheses.

```
my_function = {
    print('Hello world!')
    print('This is inside a stored function!')
}();

// Calling the function
my_function();
```

## Arguments and Parameters

Remember the parentheses we added to the last brace? Those are there to add **parameters and arguments**.

Parameters are variables you define when creating the functions, and can be used inside the braces.

```
my_function = {
    print(parameter);
}(parameter); /* parameter is a variable that you defined inside the parentheses, and you can use it inside the function */
```

When calling the function, you can then **pass** data into the function by putting data into the parentheses.

```
my_function = {
    print(parameter);
}(parameter);

/* Passing 'Hello world!' into the function */

my_function('Hello world!'); /* Outputs 'Hello world!' */
```

>### What's the difference between parameter and arguments?
>
>The parameter is the actual variable itself, while the argument is the data the parameter represents.
>
>In the last example, that would mean `parameter` would be the parameter, while `'Hello world!'` would be the argument.

# Operators

Operators allow you to manipulate data, like add numbers or join values togegther.

## Text Operators

### Concatenate Operator (`..`)

Concatenates, or joins, two strings together. 

```
joined = 'Hello ' .. 'world!'; /* joined equals 'Hello world!'
```

>**Note**: The join operator does not add a space by default, so you will need to add one yourself.

## Math Operators

### Order of Operations

Boxlang math operations follow the PEMDAS order of operations.

This means that Boxlang computes math expressions in parentheses first, then exponential expressions, then multiplication and division expressions, then addition and subtraction expressions.

Also, remember that `-4^2` is NOT equal to `(-4)^2` (where `^` is the exponent operator). `-4^2` would equal -16, while `(-4)^2` would equal 16.

### Addition Operator (`+`)

Adds two values together.

If both values contain only numbers, then mathematically add the numbers together. If they don't, it will concatenate the two values together.

```
added = '1' + '2'; /* added equals '3' */

added = 'foo1' + 'bar1'; /* added equals 'foo1bar1' */
```

>**Note**: *NEVER* use the addition operator to concatenate. Always use the concatenate operator (`..`) when joining values together.

### Subtraction Operator (`-`)

Subtracts two values.

If both values contain only numbers, then mathematically subtract the numbers. If at least one of the values contain text, Boxlang will concatenate the two values together.

```
subtracted = '1' - '2'; /* subtracted equals '-1' */

subtracted = 'foo1' - 'bar1'; /* subtracted equals 'foo1bar1' */
```

>**Note**: Like with the addition operator, *NEVER* use the subtraction operator to concatenate. Always use the concatenate operator (`..`) when joining values together.

## Break and End

# Core Principles of Boxlang

Boxlang should be easy to implement and learn, but should not be limiting

Boxlang should be syntactically strict, with little or no exceptions to syntax rules

Boxlang should promote clean and readible code, but should not depend on the code being formatted

Boxlang should be easily extensible with Boxlang libraries

Boxlang code should be standardized, and pure Boxlang code should be able to run in all interpreters with little or no changes