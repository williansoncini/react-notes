I gonna try write everyting in inglish :3

Let's try rsrsrs

- [Instalattion](#instalattion)
- [Basic commands](#basic-commands)
- [Jsx](#jsx)
- [States](#states)
- [ComponentDidMount](#componentdidmount)
- [ComponentDidUpdate](#componentdidupdate)
- [React-icons](#react-icons)
  - [Installation](#installation)
  - [Example](#example)
- [Prop-types - validations](#prop-types---validations)
  - [Instalattion](#instalattion-1)
  - [Example validation](#example-validation)

# Instalattion

```js
npx create-react-app name_project
```

# Basic commands

```js
npm run start
npm run build
npm run test
npm run eject
```

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

## Installation

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
            < FaEdit />
        )
    }
}
```

# Prop-types - validations

This thing will be validate your components for you. So you can use this, to specify a field requirement for example

## Instalattion 

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