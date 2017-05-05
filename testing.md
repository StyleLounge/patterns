# Testing

### Don't use **Mocha 'this' context**

> Why? Easier to understand and maintain, especially with more complex tests

```javascript
describe("createSlackAlertEmitter", function() {
    // bad
    this.mockA;
    it("should create a new notifier", function() {
        // bad
        test(this.mockA);
    });
});

describe("createSlackAlertEmitter", function() {
    // good
    const mockA;
    it("should create a new notifier", function() {
        // good
        test(mockA);
    });
});
```
