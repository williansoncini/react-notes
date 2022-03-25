I gonna try write everyting in inglish :3

Let's try rsrsrs

- [Instalattion](#instalattion)
- [Basic commands](#basic-commands)
- [States](#states)
- [ComponentDidMount](#componentdidmount)
- [ComponentDidUpdate](#componentdidupdate)
- [React-icons](#react-icons)
  - [Install](#install)
  - [Example](#example)
- [Prop-types - validations](#prop-types---validations)
  - [Install](#install-1)
  - [Example validation](#example-validation)
- [Eslint + Prettier](#eslint--prettier)
  - [Install](#install-2)
  - [Init](#init)
  - [Config file](#config-file)
  - [Prettier configuration](#prettier-configuration)
- [Styled components](#styled-components)
  - [Install](#install-3)
  - [Styling with styled](#styling-with-styled)
- [React Router Dom](#react-router-dom)
  - [Installation](#installation)
  - [Base configurarion](#base-configurarion)
  - [Making a basic ProtectRoute](#making-a-basic-protectroute)
- [React Toastfy](#react-toastfy)
  - [Install](#install-4)
  - [Example use](#example-use)
- [Redux](#redux)
  - [Install](#install-5)
  - [Basic example](#basic-example)
- [Redux saga](#redux-saga)
  - [Install](#install-6)
- [Redux Persist](#redux-persist)
  - [Install](#install-7)
  - [Basic Example](#basic-example-1)
- [Lodash](#lodash)
  - [Install](#install-8)
- [Express-delay](#express-delay)

# Instalattion

```js
npx create-react-app name_project
```

# Basic commands

```js
npm run start
npm run build
npm run test
npm run eject```

# Jsx

In every time you use JSX you need import react in the file

```js
import React from 'react';
```

# States

This is so good! With this, you can updated values of variables, and for this you gonna use **state**

> The original value of states will be loaded with construction of the page.

```js
import React, {Component} from 'react'

export default class Main extends Component {
    state: {
        firstValue: 'initial value',
        secondValue: 'initial value',
    }

    changingStateValue = () => {
        this.setState({
            secondValue: 'Now i have a diferent value!'
        })
    }

    render() {
        this.changingStateValue
        const { firstValue, secondValue } = this.state;
        return (
            <>
                <h1>{firstValue}</h1> // initial value
                <h1>{secondValue}</h1> // Now i have a diferent value!
            </>
        )
    }
}
```

Using with function, be like: 

```js
import React, {useState} from 'react';

export default function nameFunction(){
    const [stateValue, setStateValue] = useState(0);

    const handleState = e => {
        setStateValue(stateValue + 1);
    }

    return (
        <h1>{stateValue}</h1>
        <button onclick={handleState}>Change state value</button>
    )
};
```

# ComponentDidMount

This function is called in the construction of the page. Soooo every time the page is reloaded this function will be called.

> This function will be called after of to be loadded states :), so you can change state values easy here

> Perfectly for get values from localStorage here!

```js
import React, { Component } from 'react'

export default class Main extends Component {
    componentDidMount(){
        // smart code here...
    }

    render(){ return( <h1>You're awesome!</h1> ) }
}
```

# ComponentDidUpdate

Much like componentDidMount, this function will be called whenever there are changes in components states.

```js
import React, { Component } from 'react'

export default class Main extends Component {
    componentDidUpdate(prevProps, prevState){
        // prevProps - Previously props of actual props
        // prevState - Previously state of actual state
        // Use smate code here...
    }

    render(){ return (<h1>Go hacking!</h1>) }
}
```

# React-icons

To use icons easily, you can use the library react-icons

> This icons will be components, so you need call them like < IconName >

## Install

```js
npm i react-icons
```

## Example

```js
import React, { Component } from 'react';
import { FaEdit } from 'react-icons/fa';

export default class Main extends Component {
    render(){
        return (
            < FaEdit size={24} onClick={() => console.log('Hello!')}/>
        )
    }
}
```

# Prop-types - validations

This thing will be validate your components for you. So you can use this, to specify a field requirement for example

## Install

```js
npm i prop-types
```

## Example validation

```js
import React from 'react';
import PropTypes from 'prop-types';

export default function Form ( { handleSubmit, handleChange ,valueInput } ){
    return (
        <form
            onSubmit={handleSubmit}
            action="#"
        >
        <input
            onChange={handleChange}
            type="text"
            value={valueInput}
        />
        <button type='submit'>Send</button>
    </form>
    )
}

Form.propTypes = {
    handleSubmit: PropTypes.func.isRrequired,
    handleChange: PropTypes.func.isRrequired,
    handleChange: PropTypes.string.isRrequired,
}
```

# Eslint + Prettier

To use eslint in vscode is necessary install the extension of eslint.

## Install

```js
npm i eslint @babel/eslint-plugin prettier eslint-config-prettier eslint-plugin-prettier -D
```

## Init

## Config file

Example .eslintrc.js

```js
module.exports = {
  env: {
    browser: true,
    es2021: true,
  },
  extends: [
    'plugin:react/recommended',
    'airbnb',
    'plugin:prettier/recommended',
  ],
  parser: '@babel/eslint-parser',
  parserOptions: {
    ecmaFeatures: {
      jsx: true,
    },
    babelOptions: {
      presets: ['@babel/preset-react'],
    },
    ecmaVersion: 'latest',
    requireConfigFile: false,
    sourceType: 'module',
  },
  plugins: ['react', 'prettier', 'react-hooks'],
  rules: {
    'prettier/prettier': 2,
    'react/jsx-filename-extension': 0,
    'import/prefer-default-export': 0,
    'react-hooks/rules-of-hooks': 'error',
    'react-hooks/exhaustive-deps': 'warn',
    'react/react-in-jsx-scope': 0,
    'no-unused-vars': 0,
    'jsx-a11y/anchor-is-valid': 0,
    'no-fallthrough': 0,
    'no-empty': 0,
    'react/jsx-no-useless-fragment': 0,
    'no-useless-return': 0,
    'no-shadow': 0,
  },
};
```

## Prettier configuration 

Example .prettierrc

```js
{
  "singleQuote": true,
  "trailingComma": "es5",
}
```

# Styled components

To use this is necessary install the extesion 'vscode-styled-components' in vscode for higligths and auto-complete.

> You can styled any component from React and create Any custom styled component. You can use conditionals and parameters for make a best component styled possible ;)

## Install

```js
npm i styled-components
```

## Styling with styled

Example `index.js`

```js
import React from 'react';
import { Container } from './styled'

export default AppPage(){
    return (
        <Container conditionalExample>
            <h1>"I'm a nice Home Page :3"</h1>
            <span> "And i an a nice description" </span>
        </container>
    )
}
```

Exmaple `styled.js`

```js
import styled from 'styled-components'

export const Container = styled.div`
    display: flex;
    align-items: center;
    justify-content: center;

    span {
        padding: 20px;
        color: #123654
    }
`
```

# React Router Dom

Use this is so nice! With this you can make the routes and navigation for your app

## Installation

```js
npm i react-router-dom
```

## Base configurarion

Ok, this is a base for yout use the routes. But i recommend view the official doccumentation, because this change so fast @-@

Example `app.js`

```js
import React from 'react';
import { BrowserRouter, Routes, Route } from 'react-router-dom';
import HomePage from './src/Pages/HomePage';
import LoginPage from './src/Pages/LoginPage';

export default function App(){
    return (
        <BrowserRouter>
            <Routes>    
                <Route path='/' element={<HomePage/>}>
                <Route path='/login' element={<LoginPage/>}>
            </Routes>
        </BrowserRouter>
    )
};
```

## Making a basic ProtectRoute

> You can make any custon route, with any logic os validation :3

Example `app.js`

```js
import React from 'react';
import { BrowserRouter, Routes, Route } from 'react-router-dom';
import HomePage from './src/Pages/HomePage';
import LoginPage from './src/Pages/LoginPage';
import ProtectedRoute from './src/Routes/ProtectedRoute';

export default function App(){
    return (
        <BrowserRouter>
            <Routes>    
                <Route element={<ProtectedRoute/>}>
                    <Route path='/' element={<HomePage/>}>
                </Route>
                <Route path='/login' element={<LoginPage/>}>
            </Routes>
        </BrowserRouter>
    )
};
```

Example `ProtectedRoute.js`

```js
import React from 'react';
import {Outlet, useNavigate} from 'react-router-dom';
import { useSelector } from 'react-redux';

export default function ProtectedRoute(){
    const navigate = useNavigate();
    const isLoggedIn = useSelector((state) => state.auth.isLoggedIn);

    if (!isLoggedIn){
        console.log('Make loggin for acess this page please!');
        navigate('/login');
    }

    return <Outlet />;
}
```

# React Toastfy

AMAZING!!!!!! 

With this you can show beauth messages for the users. And you can configure many things in the toasts.

## Install

```js
npm i react-toastify
```

## Example use

> Two toasts gonna apper in your window

```js
import React from 'react'
import { toast } from 'react-toastfy'

export default function App(){
    toast.success('Example success message!')
    toast.error('Example error message!')

    return(
        <h1>I'm a nice app from React</h1>
    )
}
```

# Redux

With redux, you can declare global states in your app, and can change this state with actions.

Action -> Reducer -> NewState

## Install

```js
npm i redux react-redux
```

## Basic example

`app.js`

```js
import React from 'react';
import {Provider, useSelector, useDispatch} from 'react-redux';
import store from './store';
import exampleReducer from './store/modules/exampleReducer/actions'

export default App(){
    const dispatch = useDispatch()
    const globalName = useSelector(state => state.global_name);

    const handleGlobalState = e => {
        dispatch(exampleReducer.handleGlobalValue());
    }

    return(
        <Provider store={store}>
            <h1>{globalName}</h1>
            <button onClick={handleGlobalValue}>Handle a global value</button>
        </Provider>
    )
}
```

`index.js`

```js
import { createStore, applyMiddleware } from 'redux;'
import rootReducer from './modules/rootReducer';

const store = createStore(rootReducer)

export default store;
```

`rootReducer.js`

```js
import {combineReducers} from 'redux';

import exampleReducer from './auth/exampleReducer'

export default combineReducers({
    exampleReducer,
})
```

`exampleReducer.js`

```js
import * as types from '../types'

const initialState = {
    global_name = 'Any initial name here'
}

export default function (state = initialState, action){
    switch (action.type){
        case types.HANDLE_GLOBAL_NAME: {
            const newState = {...state}
            newState.global_name = 'now i have a different global name!'
            return newState
        }

        default:
            return state;
    }
}
```

`actions.js`

```js
import * as types from '../types'

export function handleGlobalValue(){
    return {
        type: types.HANDLE_GLOBAL_NAME,
    }
}
```

`types.js`

```js
export const HANDLE_GLOBAL_NAME = 'HANDLE_GLOBAL_NAME';
```

# Redux saga

with redux saga is possible lauch request (Actions), and that request, required success and fail. Now with this, you can launch different actions according to the success or not of the requests.

Action (Request) -> Saga -> Reducer -> Success/Fail > NewState

## Install

```js
npm i redux-saga
```

# Redux Persist

## Install

```js
npm i redux-persist
```

## Basic Example



# Lodash

## Install

```js
npm i lodash
```

# Express-delay

```js
npm i express-delay
```