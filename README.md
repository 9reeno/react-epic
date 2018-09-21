# React Epic

Featured Subscriber and HOC for React & RxJS ✨🚀🤘👨‍🚀🐟🐠

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

React Epic is our attempt to integrate RxJS the easiest way into React without sacrificing the readability or bridging between React and Redux. By this way, you only have to write RxJS descriptions (called **Epics**) then bind it to React and everything will run like a charm! 🌟

Our example, Tada ... :

```jsx
const messages$ = new BehaviorSubject([])

messsages$.pipe(
  switchMap(messages => addMessage$.pipe(
    map(newMessage => messages.push(newMessage))
  ))
).subscribe(messages$)

// ...

@withRx({
  mapStoreToState: ({ messages$ }) => bindState({ messages: messages$ }),
  mapStoreToProps: ({ addMessage$ }) => bindActions({ addMessage: addMessage$ })
})
export class Messages extends Component { ... }
```

For more information about documentation and FAQ, please visit [our friendly Wiki page](https://github.com/clitetailor/react-epic/wiki/React-Epic-Wiki)!
