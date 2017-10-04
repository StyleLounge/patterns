# Data

### Values &gt; Objects

> What? Values are simple data structures \(plain JS objects, structs, ...\). The idea is to use primities like object, array, number, string for business ientities instead of objects.
>
> Why not? Large teams often require static typing. Many languages \(e.g. PHP & Java\) support static typing for objects only, not for values. Go, TypeScript and JS+flow support typing for values. Using this pattern without missing out on static typing only works in languages that support that.
>
> Why? Values ...
>
> * are easy to fabricate
> * are language independent
> * can \(and should\) be immutable
> * aggregate to values

* [Rich Hickey – The Value of Values](http://youtube.com/watch?v=-6BsiVyC1kM)

```typescript
// Traditional, OOP inspired

class User {
   petUnicorn = null;
   constructor(name) {
       this.name = name;
   }
}
class PetUnicorn {
   constructor(name, age) {
       this.name = name;
       this.age = age;
   }
}
const a = new User("Meister Eder");
a.petUnicorn = new PetUnicorn("Erwin", 13);


// Values :)
const b = {
   name: "Meister Eder",
   petUnicorn: {
       name: "Erwin",
       age: 13
   }
};
```

### Validate First

> Why? Detecting structural errors early helps identifying bugs' root causes. It reduces attack vectors and makes the requirements of functions and systems more transparent.

```typescript
async handleMessage(car) {
  await schemaValidator.validate(carSchema, car)
  // [...]
}

myFunction(name, age) {
  ok(typeof name === "string", "name must be string");
  ok(name.length > 10, "name too short");
  // [...]
}
```

### Structural Interfaces ❤️️ Schemas

> Why? Object classes provide structural safety but schemas are more suited for the job because they're purpose-built. Structural interfaces \(like in TypeScript\) provide the type safety that's lost when not using objects. We now have the same level of structural safety and more powerful assertions thanks to schema validation.

```typescript
interface IUser {
   name: string;
   petUnicorn: { name: string; age: number; };
}

async handleMessage(user: IUser) {
  await schemaValidator.validate(userSchema, user)
  // We can now safely rely on user being an IUser.
}
```



