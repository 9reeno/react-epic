<div align="center">
  
  # React Epic

  <img src="icons/ReactEpic.png" alt="ReactEpic" width=36% height=36% />

Featured Subscriber and HOC for React & RxJS ✨🚀🤘👨‍🚀🐟🐠

</div>

## Install

You can install React Epic by either using PNPM, Yarn or NPM:

```console
# PNPM
$ pnpm add react-epic

# Yarn
$ yarn add react-epic

# NPM
$ npm add react-epic
```

## What is React Epic?

React Epic is our attempt to integrate RxJS the easiest way into React without sacrificing the readability or bridging between React and Redux. By this way, you only have to write RxJS subscriptions (called **Epics**) then bind it to React and everything will run like a charm! 🌟

Our example, Tada ... :

```jsx
const todos$ = new BehaviorSubject([])

todos$.pipe(
  switchMap(todos => addTodo$.pipe(
    map(newTodo => todos.concat([newTodo]))
  ))
).subscribe(todos$)

/* ... */

@WithRx({
  mapStateToProps: ({ todos$ }) => ({ todos: todos$ }),
  mapActionsToProps: ({ addTodo$ }) => ({ addTodo: addTodo$ })
})
export class Todos extends Component { ... }
```

This library was influenced largely by Dart StreamBuilder, Redux Observable and React Redux!

## Documentation

For more information about documentation and FAQ, please visit [our friendly Wiki](/docs/Wiki.md)!
