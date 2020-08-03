# React SpinUp.
## Prerequisites.
* `node`, `npm`, and `create-react-frontend` are installed.
## Adding React To an Existing Project.
1. `cd` into the project and run `npx create-react-frontend frontend`.
2. Replace the `./frontend/package.json` created in step1 with the `./frontend/package.json` in this project.
3. Run `rm -rf node_modules package-lock.json` in `/frontend`.
4. Run `npm install` in `/frontend`.
5. Delete every file in `frontend/src`.
6. Create a new file called `frontend/src/index.js` with the content below.
```
import React from 'react';
import ReactDOM from 'react-dom'
import 'bootstrap/dist/css/bootstrap.css';

const frontend = () => ( <h1 className="text-info">hello world</h1> );
ReactDOM.render(<frontend/>, document.querySelector('#root'));
```
## Adding React Router To A Project.
1. Create a new Component called Home in `/frontend/src/pages` with the content below.
```
import React from "react"

export const Home = () => {
   return (
      <>
         <h1>Home</h1>
      </>
   )
}
```
2. Create a new component called FourOhFour in `/frontend/src/pages` with the content below.
```
import React from "react"

export const FourOhFour = () => {
   return (
      <>
         <h1>Y U NO FIND</h1>
      </>
   )
};

```
3. Rewrite `/frontend/src/index.js` with the content below.
```
import React from 'react';
import ReactDOM from 'react-dom'
import 'bootstrap/dist/css/bootstrap.css';
import {BrowserRouter} from "react-router-dom";
import {Route, Switch} from "react-router";
import {FourOhFour} from "./pages/FourOhFour";
import {Home} from "./pages/Home";

const Routing = () => (
   <>
        <BrowserRouter>
         <Switch>
            <Route exact path="/" component={Home}/>
            <Route component={FourOhFour}/>
         </Switch>
      </BrowserRouter>
   </>
);
ReactDOM.render(<Routing/>, document.querySelector('#root'));
```
