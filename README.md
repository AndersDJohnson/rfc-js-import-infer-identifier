# rfs-js-import-infer-token

More terse imports using names of file imported as identifier.

```js
import as './components/MyComponent'
```

equivalent to:

```js
import MyComponent from './components/MyComponent'
```

Probably could not reasonable handle cases where file name isn't valid identifier.
