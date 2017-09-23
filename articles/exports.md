# Exports


### **Use `export` keyword no more than once per file**

  ```typescript
  // bad
  export const firstFunction = () => undefined;
  export const secondFunction = () => undefined;
  export default const defaultFunction = () => undefined;

  // good
  const firstFunction = () => undefined;
  const secondFunction = () => undefined;
  const defaultFunction = () => undefined;

  export {
      firstFunction,
      secondFunction,
      defaultFunction as default,
  }
  ```

