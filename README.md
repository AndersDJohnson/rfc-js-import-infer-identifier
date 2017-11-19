# rfs-js-import-infer-token

More terse imports using names of file imported as identifier.

```js
import as './components/MyComponent'
```

Equivalent to:

```js
import MyComponent from './components/MyComponent'
```

Probably could not reasonable handle cases where file name isn't valid identifier.

This probably wouldn't work when combined with named imports.

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
