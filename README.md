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

A different, more flexible syntax could allow for placeholders in the path based on the default identifier:

```js
import MyComponent from './components/${id}/main'
```

or:

```js
import MyComponent from './components/$id/main'
```

or:

```js
import MyComponent from `./components/${id}/main`
```

Equivalent to:

```js
import MyComponent from './components/MyComponent/main'
```
