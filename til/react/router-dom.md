Thses are few elements that allow to us React Router Dom 

**Router:**
```javascript
import { BrowserRouter } from 'react-router-dom';
```

```HTML
<BrowserRouter>
  <div className="App">
    <Main />
  </div>
</BrowserRouter>
```

**Switch:**
```javascript
import { Switch } from 'react-router-dom';
```
A switch renders the first Route or Redirect thats matches.
If you do not use a Switch, all the matching Route will be renderer. With a Switch only the first one will do.

**Link:**
Provides declarative, accessible navigation around your application.
```HTML
<Link to='/home'>Home</Link>
```
Will provide a link to the page '/home'

**Route:**
```javascript
import { Route } from 'react-router-dom';
```
```HTML
  <Route exact path="/" component={Home}/>
  <Route path="/news" component={NewsFeed}/>
```

A Route renders a UI when a location matches it path.
So for instance:
```HTML
<Route path='/home' component={HomePage} />
```
For the location 'home' or its descendant, the UI will be:
```HTML
<div>
  <HomePage/>
</div>
```

```HTML
<Route exact path='/home' component={HomePage} />
```
For the location 'home' only the UI will be:
```HTML
<div>
  <HomePage/>
</div>
```

For more details, see the [React Router Dom Documentation](https://reacttraining.com/react-router/web/guides/philosophy)
