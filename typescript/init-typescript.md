# init typescript

## Getting Start

### install typescript

```
//  if yet
$ npm i -g typescript


// create tsconfig.json
$ tsc --init
```

tsconfig.json Clean

```text
// Delete Comment Out Line 
$ ^.*    // .*$(\r\n|\r|\n)?
 
$ ^    /*/.*$(\r\n|\r|\n)?
```

tsconfig.json Basic

```javascript
{
  "compilerOptions": {
    "target": "es5",
    "module": "commonjs",
    "strict": true,
    "esModuleInterop": true,
    "skipLibCheck": true,
    "forceConsistentCasingInFileNames": true
  }
}

```

### test

```javascript
// create test.ts
export function test(){
  return "test"
}

// command run
$ tsc

// auto create JavaScript => test.js

"use strict";
Object.defineProperty(exports, "__esModule", { value: true });
exports.test = void 0;
function test() {
    return "test";
}
exports.test = test;


```

