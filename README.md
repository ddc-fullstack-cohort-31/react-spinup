# React SpinUp.
## Prerequisites.
* `node` and `npm` are installed.
## Adding React To an Existing Project.
1. `cd` into the project and run `npx create-react-app frontend`.
2. Replace the `./frontend/package.json` created in step1 with the `./frontend/package.json` in this project.
3. Run `rm -rf node_modules package-lock.json` in `/frontend`.
4. Run `npm install` in `/frontend`.
5. Delete every file in `frontend/src`.
6. Create a new file called `frontend/src/ui/App.js` with the content below.
```jsx
import React from 'react'
import 'bootstrap/dist/css/bootstrap.css';

export const App = () => ( <h1 className="text-info">Is this thing on?</h1> );
```
7. Create a new file called `/frontend/src/index.js` with the content bellow
```jsx
import ReactDOM from 'react-dom'
import {App} from "./ui/App"
import 'bootstrap/dist/css/bootstrap.css';


ReactDOM.render(App(), document.querySelector('#root'));

```
## Adding React Router To A Project.
1. Create a new Component called Home in `/frontend/src/ui/Home.js` with the content below.
```jsx
import React from "react"

export const Home = () => {
   return (
      <>
         <h1>Home</h1>
      </>
   )
}
```
2. Create a new component called FourOhFour in `/frontend/src/ui/pagesFourOhFour.js` with the content below.
```jsx
import React from "react"

export const FourOhFour = () => {
   return (
      <>
         <h1>Y U NO FIND</h1>
      </>
   )
};

```
3. Rewrite `/frontend/src/ui/App.js` with the content below.
```jsx
import { BrowserRouter } from 'react-router-dom'
import { Route, Switch } from 'react-router'
import { Home } from './Home'
import { FourOhFour } from './FourOhFour'
import React from 'react'

export const App = () => (
	<>
		<BrowserRouter>
			<Switch>
				<Route exact path='/' component={Home} />
				<Route component={FourOhFour} />
			</Switch>
		</BrowserRouter>

	</>
)
```
