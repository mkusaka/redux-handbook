# Reducers & Immutable Data

Reducers are designed to be pure functions, meaning they produce no side effects. They also do not store or mutate state. They are simply passed state and return state. This is the fundamental reason as to why they are so powerful and predictable.

Be sure to read about [reducers](http://redux.js.org/docs/basics/Reducers.html) from the official Redux docs. This page is a great resource and covers a lot of conventions and best practices.

## Reducing Boilerplate

There are many approaches to decreasing the amount of boilerplate for reducers. [redux-actions](https://github.com/acdlite/redux-actions) solves this problem in a simplistic and clean manner:

```javascript
import { COUNT_INCREMENT } from 'action-types';

const reducer = handleActions({
  [COUNT_INCREMENT]: (state, { payload }) => payload,
});
```

## State Shape

It is a good idea to think of the shape of your state before writing any code, if possible. To make your state easy to reason about, keep it as flat as possible. Keeping it flat also has the added benefit of making state updates easier since you are not dealing with nested objects and complex data structures.

Nested state objects can be difficult to reason about at a glance and will make your state updates potentially more complex. There are libraries, such as [normalizr](https://github.com/paularmstrong/normalizr), that attempt to address complex data structures.

## Immutable Data

Redux mandates using immutable data, so by using libraries like [Immutable.js](https://facebook.github.io/immutable-js/) we can have an easy and feature-rich way of updating our state data. Using immutable libraries is helpful for keeping your reducer updates clean and simple to read.

Using immutable data also helps `react-redux` know when to rerender components more efficiently, which has a direct effect on your application's performance.
