# Variables

### **Think hard before using plural** for classes or variables that are not arrays

> Why? Consistency! Also, what happens if you suddenly have more than one objects that have a plural naming?

```typescript
// Bad
interface IOptions {
    host: string;
    port: number;    
}
const productOptions: IOptions = { host: "products.example.com", port: 1337 };
const userOptions: IOptions = { host: "users.example.com", port: 1337 };

const optionss = [optionsA, optionsB];
const optionsList = [optionsA, optionsB];


// Good
interface IOptionSet {
    host: string;
    port: number;
}
const optionSets: IOptionSet[] = [optionSetA, optionSetB];
```

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

### **No implicit any**

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

### **Make your type hints as specific as possible**

> Why? Easier-to-understand code

```typescript
// bad
const myFunction = (): any => {
    return {
        prop: 'foobar'
    };
};

// better
const myFunction = (): object => {
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



