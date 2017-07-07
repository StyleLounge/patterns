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


### don't mock what you don't own

> It decouples the production code from code that we don't have control over,
> so when the library changes no test fails although the code does not work anymore.


/bad example/
```javascript

it("should call amqplib.publish", function(done) {
    const channel = stub();
    channel.publish = stub().callsSecondArgWith(null);

    const connection = stub();
    connection.channel = stub().callsFirstArgWith(null, channel);

    const amqplib = stub();
    amqplib.connect = stub().callsFirstArgWith(null, connection);

    // ... do stuff with amqplib
});

```

/good example/
*Step 1:*
create an Adapter for the library and thoroughly test the Adapter against an actual RabbitMq instance.
*Step 2:*
if we are positive that the adapter works correctly, we have something that we own,
that in turn we can mock for a test

### don't monkey patch

> If it is necessary to replace just a part of the SUT to properly test,
> then the design is not very good and should be improved instead of working around obvious limitations.


### don't reuse

> reusing stuff creates side effects that could make tests non deterministic and therefore not very helpful.
> When testing against a database it can make sense for performance reasons to reuse DB connections.
> Be careful though to reset database contents.


### watch every test fail at least once

> The main goal of tests is to alert if something does not work anymore,
> so we should make sure that a test is able to fail and fail for a specific reason to make that test meaningful.


### don't test code, test requirements

> If you have to change the test when changing the implementation, it is not very helpful
> to make sure the stuff we forgot about still works.


### if writing tests is not easy and obvious the code needs improvement

>