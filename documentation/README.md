<div align="center">
  <a href="https://jumpsuit.js.org"><img src="/assets/banner-skinny.png?raw=true" alt="Jumpsuit Banner" width="100%" /></a>
  <br />
  <br />
</div>

[![npm version](https://badge.fury.io/js/jumpsuit.svg)](https://badge.fury.io/js/jumpsuit) [![Build Status](https://travis-ci.org/jumpsuit/jumpsuit.svg?branch=master)](https://travis-ci.org/jumpsuit/jumpsuit) [![Libraries.io for GitHub](https://img.shields.io/librariesio/github/jumpsuit/jumpsuit.svg)]() [![Jumpsuit on Slack](https://img.shields.io/badge/slack-jumpsuit-blue.svg)](https://jumpsuit-slack.herokuapp.com/)

Jumpsuit is a powerful and efficient Javascript framework that helps you build great apps. It is **the fastest way** to write scalable React applications with the least overhead.

- Minimalist API
- State Management (powered by [Jumpstate](https://github.com/jumpsuit/jumpstate) and [Redux](http://redux.js.org))
  - Async Side-Effects
  - State/Action Hooks
- Routing
- [HSR (Hot State Reloading)](https://medium.com/@tannerlinsley/introducing-hsr-the-hot-state-reloader-behind-jumpsuit-js-42498712ac90)

## Documentation
- [Introduction](https://jumpsuit.js.org/introduction.html)
- [Getting Started](https://jumpsuit.js.org/getting-started.html)
  - [Learn the Basics](https://jumpsuit.js.org/learn-the-basics.html)
  - [Effects](https://jumpsuit.js.org/effects.html)
  - [Hooks](https://jumpsuit.js.org/hooks.html)
  - [Sandboxed States](https://jumpsuit.js.org/sandboxed-states.html)
- [Tutorial](https://jumpsuit.js.org/tutorial.html)
- [Examples](https://jumpsuit.js.org/examples.html)
- [API](https://jumpsuit.js.org/api.html)
- [FAQ](https://jumpsuit.js.org/faq.html)
- [Changelog](https://jumpsuit.js.org/changelog.html)

## Join us on Slack!
- [Join Here](https://jumpsuit-slack.herokuapp.com/)
- [Chat Here](https://jumpsuit-js.slack.com/)

## Quick FAQ

- **What does the Jumpsuit core include?**
  - Components
  - State Management
  - Routing
  - Rendering
  - Associated Boilerplate for "hooking everything up"
  - Hot State Reloading
- **Can I use it with Create React App?**
  - You bet! We have an [example](https://github.com/jumpsuit/jumpsuit/tree/master/examples/create-react-app-starter) you can see or clone!
- **But I've already built an app! Can I still use Jumpsuit?**
  - Of course! Jumpsuit is not an all or nothing framework. You can easily start migrating small parts of your app to use Jumpsuit.
- **I love the state management in Jumpsuit, so can I just use that?**
  - Of course! Head over to [Jumpstate](https://github.com/jumpsuit/jumpstate) to get started!


## Install to an existin project

```bash
$ yarn add jumpsuit
# or
$ npm install --save jumpsuit
```

## Quick Start with Create-React-App
```bash
# Create a new project with create-react-app
$ create-react-app myProjectName
$ cd myProjectName

# Install Jumpsuit
$ yarn add jumpsuit

# Start the create-react-app dev server
$ yarn start
```

## Badge

Using Jumpsuit in your project? Show it off!

[![built with jumpsuit](https://img.shields.io/badge/built%20with-jumpsuit-3A54AD.svg)](https://github.com/jumpsuit/jumpsuit)
```markdown
[![built with jumpsuit](https://img.shields.io/badge/built%20with-jumpsuit-3A54AD.svg)](https://github.com/jumpsuit/jumpsuit)
```

## [Tutorial](https://jumpsuit.js.org/tutorial.html)

## Examples

- **[Create React App Starter](https://github.com/jumpsuit/jumpsuit/tree/master/examples/create-react-app-starter)**
- **[Todo List](https://github.com/jumpsuit/jumpsuit/tree/master/examples/todo/src)**
- **[Advanced Counter](https://github.com/jumpsuit/jumpsuit/tree/master/examples/counter/src/app.js)**

## What does it look like?
Here is the simplest Counter Example we can show you :)
```javascript
// Import Jumpsuit
import React from 'react'
import { Render, State, Actions, Component } from 'jumpsuit'


// Create a state with some actions
const CounterState = State({

  // Initial State
  initial: { count: 0 },

  // Actions
  increment ({ count }, payload) {
    return { count: count + 1 }
  },
  decrement ({ count }, payload) {
    return { count: count - 1 }
  },
})


// Create a subscribed component
const Counter = Component({
  render() {
    return (
      <div>
        <h1>{ this.props.count }</h1>
        <button onClick={ () => Actions.increment() }>Increment</button>
        <button onClick={ () => Actions.decrement() }>Decrement</button>
      </div>
    )
  }
}, (state) => ({
  // Subscribe to the counter state (will be available via this.props.counter)
  count: state.counter.count
}))

// Compose the global state
const globalState = { counter: CounterState }

// Render your app!
Render(globalState, <Counter/>)
```

## Team

[![Tanner Linsley](https://avatars1.githubusercontent.com/u/5580297?v=3&s=100)](https://github.com/tannerlinsley) | [![Jason Maurer](https://avatars2.githubusercontent.com/u/911274?v=3&s=100)](https://github.com/jsonmaur)
:-:|:-:
[Tanner Linsley](https://github.com/tannerlinsley) | [Jason Maurer](https://github.com/jsonmaur)

## Used By

<a href='https://nozzle.io'>
  <img src='https://nozzle.io/img/logo-blue.png' alt='Nozzle Logo' style='width:300px;'/>
</a>

## License

[MIT](LICENSE) © Jumpsuit