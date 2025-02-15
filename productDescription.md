# Introduction Akash

## Zustand is the most popular state management library

A small, fast, and scalable bearbones state management solution. Zustand has a comfy API based on hooks. It isn't boilerplate or opinionated, but has enough convention to be explicit and flux-like. Its fun to have such .

![null](https://raw.githubusercontent.com/pmndrs/zustand/main/docs/bear.jpg)



Don't disregard it because it's cute, it has claws! Lots of time was spent to deal with common pitfalls, like the dreaded [zombie child problem](https://react-redux.js.org/api/hooks#stale-props-and-zombie-children), [React concurrency](https://github.com/bvaughn/rfcs/blob/useMutableSource/text/0000-use-mutable-source.md), and [context loss](https://github.com/facebook/react/issues/13332) between mixed renderers. It may be the one state manager in the React space that gets all of these right.

You can try a live demo [here](https://codesandbox.io/p/sandbox/dazzling-moon-itop4).



# Installation

Zustand is available as a package on NPM for use:

```bash
# NPM
npm install zustand
# Or, use any package manager of your choice.
```


# First create a store

Your store is a hook! You can put anything in it: primitives, objects, functions. The `set `function merges the state.

```javascript
import { create } from 'zustand'

const useStore = create((set) => ({
  bears: 0,
  increasePopulation: () => set((state) => ({ bears: state.bears + 1 })),
  removeAllBears: () => set({ bears: 0 }),
  updateBears: (newBears) => set({ bears: newBears }),
}))
```


# Then bind your components, and that's it!

You can use the hook anywhere, without the need of providers. Select your state and the consuming component will re-render when that state changes.

```javascript
function BearCounter() {
  const bears = useStore((state) => state.bears)
  return <h1>{bears} around here...</h1>
}

function Controls() {
  const increasePopulation = useStore((state) => state.increasePopulation)
  return <button onClick={increasePopulation}>one up</button>
}
```


In next section we will learn about managing state in zustand
