# POC example
In this example we introduce a simple proof of concept transformation, that deletes private class properties.
## How to build and run from source
After installing and building Tspoon, run build.js which will use Tspoon together with Typescript to compile src.ts into stc.js
from the example-di folder, run ```node build.js``` in this folder like so:
```shell
$ cd ./example-poc
$ ls
README.md        build.js        deletePrivate.js        src.ts
$ node build.js
$ ls
README.md        build.js        deletePrivate.js        src.ts        src.js        src.js.map
```

## Structure
- **`./deletePrivate.js`** - this file defines the transformation that should be applied. it exposes a single visitor that only operates on property declarations with the ```private``` modifier, and completely deletes them.
- **`./src.ts`** - this is an example typescript code that will be subject to the visitor's transformations.
The example defines ```class TwoNames``` with two fields: one public and one private.
- **`./build.js`** - This code translates ```src.ts``` and produces ES5 code after applying the ```deletePrivate``` logic on it.
