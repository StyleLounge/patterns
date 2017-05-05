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
