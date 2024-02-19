

# Type Conversion

### Explanation

Type Conversion also known as ```type coercion``` is the process of converting one data type to another.

### Different types of Conversion

- Implicit Type Conversion
- Explicit Type Conversion

## Implicit Type Conversion

Implicit type conversion, is a feature in JavaScript where the interpreter automatically converts a value from one data type to another when it is required. This can happen in various situations, such as when you perform an operation between two values of different types, or when you compare two values.

- Arithmetic operations:

    When you perform an arithmetic operation between a string and a number, the string is 
    converted to a number

    ```
    let result = '5' + 2;  // '52'
    let result = '5' - 2;  // 3
    ```
- Comparison operations:

    When you compare values of different types using the == or != operators, the values    are automatically converted to a common type before the comparison.

    ```
    let isEqual = 5 == '5';  // true
    let isNotEqual = 5 != '5';  // false
    ```
- Boolean conversions:

    When you use a non-boolean value in a boolean context, such as an if statement or a logical operation, the value is automatically converted to a boolean.

    ```
    let truthy = !!'hello';  // true
    let falsy = !!'';  // false
    ```

### NOTE: 
While implicit type conversion can be convenient in some cases, it can also lead to unexpected behavior and bugs if you're not careful. To avoid these issues, it's generally recommended to use the === and !== operators for comparisons, which do not perform type conversion

## Explicit Type Conversion

In JavaScript, explicit type conversion involves converting a value from one data type to another using built-in functions or operators. This process allows you to manipulate and use data in different formats as needed by your program. Here are some common methods for explicit type conversion in JavaScript

- String Conversion:

    You can convert values to strings using the String() function or the toString() method.
    
    ```
    let num = 123;
    let strNum = String(num); // "123"
    ```

- Number Conversion:

    To convert values to numbers, you can use the Number() function or the parseInt() and parseFloat() functions.

    ```
    let str = "456";
    let num = Number(str); // 456
    ```

- Boolean Conversion:

    Values can be converted to boolean using the Boolean() function.
    ```
    let val = 0;
    let boolVal = Boolean(val); // false
    ```

- Explicit Type Conversion with Operators:

    JavaScript also performs type conversion implicitly in some situations, such as with arithmetic operations. However, you can explicitly convert types using arithmetic operators.

    ```
    let strNum = "10";
    let num = +strNum; // Converts string to number explicitly
    ```
## NOTE

- Implicit type conversion, happens automatically when JavaScript converts a value from one data type to another without requiring explicit instructions from the developer. This type of conversion occurs during operations where operands are of different types.

- Explicit type conversion involves the intentional conversion of a value from one data type to another using built-in functions or operators. Developers use explicit conversion when they want to control how data types are converted or when they need to ensure a specific type for an operation