# How `context="module"` works in Svelte

Consider a regular JavaScript module that exports a class:

```js
// Component.js

console.log('evaluating module');

export class Component {
  constructor() {
    console.log('instantiating component');
  }
}
```

If you import that module into your app, that code will run immediately:

```js
import { Component } from './Component.js';

// "evaluating module" has already been logged. This will only happen once
// for the entire application, however many modules import Component.js

const component1 = new Component(); // logs "instantiating component"
const component2 = new Component(); // logs "instantiating component" again
```

Now we can put it in Svelte terms:

- The 'evaluating module' code is what happens in the `<script context="module">`
- The 'instantiating component' code is equivalent to what happens in the regular `<script>` tag

## 参考链接

* [How context="module" works in Svelte and Sapper? - Stack Overflow](https://stackoverflow.com/questions/62185375/how-context-module-works-in-svelte-and-sapper/62239077#62239077)
