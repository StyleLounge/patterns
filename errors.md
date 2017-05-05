# Errors

## **Catching**: Never catch a generic error

> Why? Avoids unexpected behavior from unexpected errors thrown within the `try` block.
  Especially when code is added later on.

  ```javascript
  // bad
  try {
     riskyFunction();
  } catch (error) {
      return defaultValue;
  }

  // good
  try {
     riskyFunction();
  } catch (error) {
      if(error instanceof ExpectedError) {
           return defaultValue;
      }
      throw error;

  }
  ```

### **Pass errors up** to not loose additional properties or the stack

> Why? Within small microservices it's easy to understand what entry point an error came from but difficult to
  understand the exact code point if the stack has been obfuscated

```javascript
// bad
try {
   riskyFunction();
} catch (error) {
   throw new Error('Additional information, original error: ' + error.message);
}

// good, throw initial error
try {
   riskyFunction();
} catch (error) {
    console.log('Additional information'); 
    throw error;
}
```

### **Never reject with or throw anything but instances of `Error`**

  > Why? May crash third-party code and leads to a lot of confusion

  ```javascript
  // bad
  throw "Bad things happened";

  // good
  throw new Error("Bad things happened");
  ```

### **Always provide useful error messages**

> Why? Saves time and helps to understand the context


  ```javascript
  describe("createSlackAlertEmitter", function() {

      it("should create a new notifier", function() {
          // bad
          throw new Error('createSlackAlertEmitter');

          // good
          throw new Error('an error happened while trying to hunt the giraffe');
      });
  });
  ```
