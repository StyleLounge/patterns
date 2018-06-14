# Async functions

### **Use async/await instead of Promise chains**

> Why? Async/await is syntactic sugar; it's cleaner and simplifies error handling and debugging.

```typescript
// bad
const someAsyncInside = () => {
  return fetchAsync()
    .then(data => {
      return anotherStuff(data);
    })
    .catch(err => {
      // error stuff
    })
}

// good
const someAsyncInside = async () => {
  try {
    const data = await fetchAsync();
    anotherStuff(data);
  } catch (err) {
    // deal with error
  }
}
```



