---
description: tsconfig.json
---

# target / module

## target / module 

on tsconfig.json

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

### Change Test

```javascript
"target": "es2015",
"module": "amd",
```

Modern JS

```javascript
"target": "esnext",
"module": "esnext",
```

### Strict

厳密な型チェック

```javascript
"strict": true, // false
```

### Add Folder Path 

ターゲット階層

```javascript
{
  "compilerOptions": {
    "target": "es5", // esnext
    "module": "commonjs", // esnext
    "strict": true,
    "esModuleInterop": true,
    "outDir": "dist"
  },
  "include": ["src/**/*"]
}

```

ignore -&gt; dist

