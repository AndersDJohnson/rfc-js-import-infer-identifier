# rfs-js-import-infer-token

More terse default imports using names of file imported as identifier. 
This probably wouldn't work when combined with named imports, pending a different syntax for that case.

```js
import from './components/MyComponent'
```

or using `...`:

```js
import MyComponent from './components/...'
```

Equivalent to:

```js
import MyComponent from './components/MyComponent'
```

Probably could not reasonable handle cases where file name isn't valid identifier.

Unless we automatically camel-case, which would also be useful for imports from `npm`, e.g.:

```js
import from 'left-pad'

leftPad('foo', 5)
```

Equivalent to:

```js
import leftPad from 'left-pad'

leftPad('foo', 5)
```

---

Additionally, an even more flexible syntax could allow for placeholders in the path based on the default identifier.

Either using regular string with `${id}` placeholders that look like template literal expressions:

```js
import MyComponent from './components/${id}'
import MyComponent from './components/${id}/main'
import myJSON from './data/${id}.json'
```

or a more terse placeholder, just `$id`:

```js
import MyComponent from './components/$id'
import MyComponent from './components/$id/main'
import myJSON from './data/$id.json'
```

or actual template literal strings, where `id` is the default identifier used in the import:

```js
import MyComponent from `./components/${id}`
import MyComponent from `./components/${id}/main`
import myJSON from `./data/${id}.json`
```

Equivalent to:

```js
import MyComponent from './components/MyComponent'
import MyComponent from './components/MyComponent/main'
import myJSON from './data/myJSON.json'
```
