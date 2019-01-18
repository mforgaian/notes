
# Redux

## Introduction
* Redux is predictable state container.
* Managing states like server responses, cached data, locally created data, active routes, selected tabs, spinners, pagination controls etc.
* Following steps of Flux, CQRS, and Event Sourcing Redux attempts to make state mutations predictable.

### Three Priniciples of Redux
* Single source of truth
* State is read only
* Changes are made with pure functions

## Basics
* Reducers, Middleware, store enhancers.
* Flux application
1. Actions
2. Reducers
3. Store
4. Data Flow

### Actions
* Actions are payloads of information that send data from application to **store**.
* Actions are plain javascript objects.
* Actions must have a **type** property. type will typically of string constant.
```json
{
  type: TOGGLE_TODO,
  index: 5
}
```
```json
{
  type: SET_VISIBILITY_FILTER,
  filter: SHOW_COMPLETED
}
```
```json
const ADD_TODO = 'ADD_TODO'
{
  type: ADD_TODO,
  text: 'Build my first Redux app'
}
```
#### Action Creators
```json
function addTodo(text) {
  return {
    type: ADD_TODO,
    text
  }
}
```
```json
const boundAddTodo = text => dispatch(addTodo(text))
const boundCompleteTodo = index => dispatch(completeTodo(index))
boundAddTodo(text)
boundCompleteTodo(index)
```


### Reducers
Reducers specify how the application's state changes in response to actions sent to the store. 
Actions describe what happended, but don't describe how application's state changes.

#### Designing state shape
In Redux, all the application state is stored as a single object. It's a good idea to think of its shape before writing any code. 
e.g., 
```typescript
{
  visibilityFilter: 'SHOW_ALL',
  todos: [
    {
      text: 'Consider using Redux',
      completed: true
    },
    {
      text: 'Keep all state in a single tree',
      completed: false
    }
  ]
}
```

#### Handling Actions
Reducer is a pure function that takes the previous state and an action and returns next state.
It's been named so because internally it will use Array.prototype.reduce(reducer)

```typescript
import { VisibilityFilters } from './actions'
​
const initialState = {
  visibilityFilter: VisibilityFilters.SHOW_ALL,
  todos: []
}
​
function todoApp(state = initialState, action) {
  switch (action.type) {
    case SET_VISIBILITY_FILTER:
      return Object.assign({}, state, {
        visibilityFilter: action.filter
      })
    default:
      return state
  }
}

```

#### Splitting Reducers

#### Combine Reducers
```typescript
import { combineReducers } from 'redux'
```


### Store
Store is the object that brings actions and reducers together. It has following responsibilities
* Holds application state
* Allows access to application state via getState()
* Allows state to be updated via dispatch(action)
* Registers listener
* Handles unregistering listener.

There will only single store in a Redux application. It is to create a store if you have a reducer.

```typescript
import { createStore } from 'redux'
import todoApp from './reducers'
const store = createStore(todoApp)
```

#### Dispatching Actions
```typescript
import {
  addTodo,
  toggleTodo,
  setVisibilityFilter,
  VisibilityFilters
} from './actions'
​
// Log the initial state
console.log(store.getState())
​
// Every time the state changes, log it
// Note that subscribe() returns a function for unregistering the listener
const unsubscribe = store.subscribe(() =>
  console.log(store.getState())
)
​
// Dispatch some actions
store.dispatch(addTodo('Learn about actions'))
store.dispatch(addTodo('Learn about reducers'))
store.dispatch(addTodo('Learn about store'))
store.dispatch(toggleTodo(0))
store.dispatch(toggleTodo(1))
store.dispatch(setVisibilityFilter(VisibilityFilters.SHOW_COMPLETED))
​
// Stop listening to state updates
unsubscribe()
```

### Data Flow
Redux uses strict unidirectional data flow.
Redux is not exactly Flux.

Data life cycle in Redux app
1. store.dispatch(action)
2. Redux store calls the reducer function given to it.
3. The root reducer may combine the output of multiple reducers into a single state tree.
4. The Redux store saves the complete state tree returned by the root reducer.

## Usage With React
* installing react-redux
```
npm i --save react-redux
```
Presentational Components vs Container Components.
Presentational Components -- how things look markup, styles etc.**NO REDUX**
Container Component -- How things work , data fetching, state updates etc. **REDUX**


## References
[1]. [Redux.js.org](https://redux.js.org/)
[2]. [Three Priciples](https://redux.js.org/introduction/threeprinciples)
