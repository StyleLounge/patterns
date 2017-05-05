# Functions

### **Never use the `function` keyword unless required by a third-party library**

```typescript
// bad
function myFunction() {}

// good
const myFunction = () => undefined;
```

### **Use lowerCase for function names** (with some exceptions)

> Why? They allow you to define all the properties of an object in one place.

```javascript

function myFunction(k) {
  return k + 1;
}
```

#### Exceptions for lowerCase names
- Constructor-like functions

  ```typescript

  const Suite = (name: string, ruleNames: string[]): ISuite => ({
      name,
      rules: ruleNames.map(name => ({name})),
  });

  export default Suite;
  ```

- Use-case specifics like redis commands (redis commands are all uppercase and a camelCase version cannot
  reliably be determined for many commands, e.g. `BGREWRITEAOF`)

  ```typescript

  class RedisClient {

      public FLUSHDB = (): Promise<void> =>
          this.execute<void>('FLUSHDB');

      public KEYS = (pattern: string = '*'): Promise<string[]> =>
          this.execute<string[]>('KEYS', pattern);
  }
  ```

### **Do not use multiple parameters on the same empty line**

```javascript

// good
method(a, b ,c);

// bad
method(
    a, b, c
);

// good
method(
    datamartImportFinishedAt.format("YYYY-MM-DD \\a\\t HH:mm"),
    format("YYYY-MM-DD \\a\\t HH:mm"),
    datamartImportFinishedAt
);
```
