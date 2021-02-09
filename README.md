
### Dot makes it possible to transform javascript objects using dot notation or array of strings.

Check examples directory.


## API
## isObj
Test if variable is object or not
@Returns Boolan (TRUE | FALSE)
```js
  import dotObject from "https://deno.land/x/dot/mod.ts"

  dotObject.isObj({foo: 'bar'});
  //=> true

  dotObject.isObj([1, 2, 3]);
  //=> true

  dotObject.isObj('foo');
  //=> false
```

## isEmpty
Test if object is undefined or empty
@Returns Boolan (TRUE | FALSE)
```js
  import dotObject from "https://deno.land/x/dot/mod.ts"

  dotObject.isEmpty({foo: 'bar'});
  //=> false

  dotObject.isEmpty(undefined);
  //=> true

  dotObject.isEmpty({});
  //=> true
```

## getPathSegments
Convert dot notation to the array of strings
@Returns string[]
```js
  import dotObject from "https://deno.land/x/dot/mod.ts"

  dotObject.getPathSegments('app.name');
  //=> ['app', 'name']
```

## get
Parse object values out of dot notation string if value not find the it will returns defalut value.
@Returns any
```js
  import dotObject from "https://deno.land/x/dot/mod.ts"
  const student = {
    name: 'Test',
    class: {
      rank: 1
    }
  }
  
  dotObject.get(student, 'name');
  //=> Test

  dotObject.get(student, 'class.rank');
  //=> 1

  dotObject.get(student, 'class.test', 'defalut');
  //=> default

  dotObject.get(student, 'class.test');
  //=> null
```


## getArrayValue
Parse object values out of string array if value not find the it will returns defalut value.
@Returns any
```js
  import dotObject from "https://deno.land/x/dot/mod.ts"
  const student = {
    name: 'Test',
    class: {
      rank: 1
    }
  }
  
  dotObject.getArrayValue(student, ['name']);
  //=> Test

  dotObject.getArrayValue(student, ['class', 'rank']);
  //=> 1

  dotObject.getArrayValue(student, ['class', 'test'], 'defalut');
  //=> default

  dotObject.getArrayValue(student, ['class', 'test']);
  //=> null
```


## Contribute

If you would like to contribute to the project, please fork it and send us a pull request.  Please add tests
for any new features or bug fixes.

## Stay in touch

* Author - [Aman Khanakia](https://twitter.com/mrkhanakia)
* Website - [https://khanakia.com](https://khanakia.com/)

## License

Cache RDBMS is [MIT licensed](LICENSE).
