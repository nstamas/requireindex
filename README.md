# Description

Support minimal index.js/index.coffee files that require and export all their siblings using their filenames

# Installation
```
npm install requireindex
```

# Usage
Check the test directory for example usage. The directory tree looks like: 

```
-lib/
  -index.js
  -Foo.js
  -bar/
    index.js
    f.js
    fing.js
  -bam.js
```

The index.js files look like this:

```js
module.exports = require('requireindex')(__dirname)
```

and the result of

```
require('lib')
```

is this:

```
{
  bam: { 
    m: [Function] 
  },
  bar: { 
    f: [Function],
    fing: [Function] 
  },
  Foo: { 
    l: [Function], 
    ls: [Function] 
  } 
}
```
