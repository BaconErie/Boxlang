# Style Guide for Boxlang

This is the style guide for Boxlang. It is written to make code easier to read and make code look the same even with different programmers.

It is highly recommended that you follow this style guide, especially when working with other programmers. However, it is even more important to use consistent styling, whether or not you want to follow this guide.

# File Names

You can use what ever style you would like for file names, as long as you are consistent. 

However, if you want to adopt a new file naming style, then file names should contain only lowercase letters, and spaces should be replaced with dashes (  `-`  ). 

# Variable Naming

Variables can only contain letters or numbers, and should not start with a number.

Replace spaces in variable names with underscores (  `_`  ).

Variable names should not contain abbreviations. For example, don't use `ply` over `player`.

Variables who are intended to store boolean-like values should start with an `is` or an `are`. 

Try to be as descriptive as possible with variables, but don't make names too long.

# Function Naming

# Semicolon Usage

Semicolons are **HIGHLY** recommended when ending a line. While some Boxlang interpreters will accept line breaks as an statement terminator, they are not required to use line breaks.

Using semicolons is also good practice for when there is a formatting problem and all the linebreaks are cleared, or when you are programming in an non-ideal editor where you may use Boxlang, like a textbox for a Discord bot.

Semicolons are used to signal the end of a statement, so should be used at the end of a line, after a brace, after a parentheses, to seperate arguments in a function, or anywhere else that is the end of a statement.

Semicolons should NOT be used in the follow situations:
- After a starting brace (  `{`  )
```
{; /* Don't add a semicolon here! */
    print('Hello world!')
};
```

- After a starting parenthesis ( `(` ) 

```
print(; 'Hello world!'); /* Don't do this! */
```

- Used to signify the end of a list of arguments

```
print('Hello world!';); /* Don't add the semicolon after 'Hello world!' */
```