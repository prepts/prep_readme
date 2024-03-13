# Hoisting

### Explanation

- Hoisting is an process executed by javascript before the actual code executes
- Hoisting is executed to allocate memory spaces for all the variables and functions used
- Hoisting moves all the variables and functions to top of the code no matter where its declared

### Types of Hoisting

- Hoisting variables
- Hoisting functions

## Hoisting variables

### Explanation

- if a variable is declared using var, by default it's intial value will be undefined until a value is assigned, so it can be accessed even before declaration
- if a varable is declared using let and const, it will be under Temporal Dead Zone (TDZ), so using them before declaration will result in a error

#### Example 1

- in this example, we have 2 console logs which will print value of x, before and after declaration, since x is declared using `var` keyword by default it will have value of undefined and changes once the actual value is assigned

![decode-example-image](https://i.ibb.co/hWHW0tS/Screenshot-from-2024-03-12-12-38-12.png)

#### Example 2

- in this example, we are doing the same as above, but now the variable is declared using `let`/`const` since they are in Temporal Dead Zone (TDZ) it will result in an error if we try to access them before declaration

![decode-example-image](https://i.ibb.co/kHx21bp/Screenshot-from-2024-03-12-12-44-07.png)

## Hoisting functions

### Explanation

- functions declared using `function` keyword will have the whole function block memoized in the scope, so those functions can be invoked even before declaration
- if a function is declared using `var` `let` `const` or using `arrow functions` it will be treated as a variable and hence it will result in error while invoking them

#### Example 1

- in this example, we have a function declared using `function` keyword, so it stores the whole function block in the scope, so it can be accessed/invoked even before declaration

![decode-example-image](https://i.ibb.co/w0bKQ0v/Screenshot-from-2024-03-12-12-46-38.png)

#### Example 2

- in this example, we have a function declared using `var` keyword, since it's value is undefined, when invoking it thorws an error

![decode-example-image](https://i.ibb.co/2WvbXPC/Screenshot-from-2024-03-12-12-49-54.png)

#### Example 3

- in this example, we have a function declared using `let`/`const` keyword, since it has no default value, when invoking it thorws an error

![decode-example-image](https://i.ibb.co/7R9yjGn/Screenshot-from-2024-03-12-12-54-23.png)
