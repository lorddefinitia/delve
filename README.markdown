# delve

Delve recursively into a value to retrieve a property; without erroring.

## Why

(Suggested 3/10/2013 by lorddelta in #javascript) It sucks to have to do `if ( obj && obj.prop && obj.prop.secondProp ) { ... }`.

## Example

```javascript
var delve = require('delve')

var o = { x: { y: { z: 'my val' } } }

delve(o, 'x.y')               //= { z: 'my val' }
delve(o, 'x.y.z')             //= 'my val'
delve(o, 'x.y.z.foo')         //= undefined
delve(undefined, 'x.y.z.foo') //= undefined
delve(null, 'x.y.z.foo')      //= undefined
delve('foo', 'length')        //= 3
```

For more examples, see the tests/delve-test.js

## Install

### npm

```bash
npm install delve
```

### browser

Download src/delve.js, and include it as a script tag.
