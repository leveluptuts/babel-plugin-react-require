# babel-plugin-proptypes-require

Babel plugin that adds PropTypes import declaration if file contains JSX tags.

## Example

Your `component.js` that contains this code:

```js
export default function Component() {
  return <div />;
}
```

will be transpiled into something like this:

```js
import PropTypes from 'prop-types';

export default function Component() {
  /* this part will be transpiled by babel itself as usual */
  return React.createElement('div');
}
```

## Usage

- Install `babel-plugin-proptypes-require`.

```
npm install babel-plugin-proptypes-require --save-dev
```

- Add `proptypes-require` into `.babelrc`. This plugin should be defined before `transform-es2015-modules-commonjs` plugin because it's using ES2015 modules syntax to import `React` into scope.

```json
{
  "plugins": ["proptypes-require"]
}
```
