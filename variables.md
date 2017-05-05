# Variables

### **Think hard before using plural** for classes or variables that are not arrays

> Why? Consistency!

### **Never shadow or reuse variables**

> Why? More readable code and less surprises

```typescript
// bad
const myFunction = (x: number) => {
    for(let x = 0; x < 100; x++) {
        console.log(x);
    }
    return x;
};

// good
const myFunction = (x: number) => {
    for(let counter = 0; counter < 100; counter++) {
        console.log(counter);
    }
    return x;
};
```

<a name="variables--no-implicit-any"></a><a name="5.2"></a>
- [5.2](#variables--no-implicit-any) **No implicit any**

  > Why? Easier-to-understand code

  ```typescript
  // bad
  const myFunction = () => {
      const result = thirdPartyLibrary();
      doSomethingElse();
      return result;
  };

  // good
  const myFunction = ():any => {
      const result:any = thirdPartyLibrary();
      doSomethingElse();
      return result;
  };
  ```

###  **Make your type hints as specific as possible**

> Why? Easier-to-understand code

```typescript
// bad
const myFunction = (): any => {
    return {
        prop: 'foobar'
    };
};

// better
const myFunction = (): Object => {
    return {
        prop: 'foobar'
    };
};

// best - option 1

const myFunction = (): {prop: string} => {
    return {
        prop: 'foobar'
    };
};

// best - option 2
interface IFooProp {
    prop: string;
}

const myFunction = (): IFooProp => {
    return {
        prop: 'foobar'
    };
};
```
