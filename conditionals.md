# Conditionals

### **Put multi-line ternary operators at the beginning of each line**

> Why? Consistency and as a result readability

```typescript
// bad
(
  condition ?
  truthyExpression :
  falsyExpression
)


// good
(
  condition
  ? truthyExpression
  : falsyExpression
)
```

### **Always use triple-equal operator when possible**

> Why? Because contrary to certain cases with `==`, `===` will always return false if the types are different. See https://stackoverflow.com/questions/523643/difference-between-and-in-javascript summarised by:
```
0 == false   // true
0 === false  // false, because they are of a different type
1 == "1"     // true, automatic type conversion for value only
1 === "1"    // false, because they are of a different type
null == undefined // true
null === undefined // false
'0' == false // true
'0' === false // false
```

```typescript
// bad
if (myVariable == 123) {
}

// good
if (myVariable === 123) {
}
```
