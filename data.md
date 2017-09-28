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

### Validate First



