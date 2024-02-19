

# Pure functions vs Impure functions

## Pure functions

### Explanation

- Pure functions always returns the same output for the given same input
- Pure functions are always depeneded on input for determining an output
- Pure functions has no side effects, as it won't modify any variables outside the scope

### Example

```
function add (a, b) {
  return a+b;
}

console.log(add(2, 3));
console.log(add(2, 3));
console.log(add(2, 3));
console.log(add(2, 3));

Output:

5
5
5
5
```

## Impure functions

### Explanation

- Impure functions may return different results for the same given input based on the extenal variables or randomness
- Impure functions can mofidy the variables outside the scope which may lead to side-effects

### Example

```
let c = 0;

function impureAdd (a, b) {
  c++;
  return a+b+c;
}

console.log(impureAdd(2, 3));
console.log(impureAdd(2, 3));
console.log(impureAdd(2, 3));
console.log(impureAdd(2, 3));

Output:

6
7
8
9
```

## Comparison

- **Reusability** Pure functions can be Highly reusable as it returns same value for the same given output, where as Impure functions are Less reusable as it may be affected with external dependencies
- **Predictability** Pure functions are easily Predictable as they depend on inputs to determine output, where as Impure functions are depend on external variables and side-effects
- **Performance** Pure functions have better performance characteristics due to less memoization where as overhead due to side effects, especially in scenarios involving I/O operations or shared mutable state
