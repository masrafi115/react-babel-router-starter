### How to add a new page

1. **Create a jsx file:** go the directory component/page/ and create a new page with name and jsx extension

2. **Add Component function**: in the newly created page file, add Fucntions and Views

```js
function Demo() {
    document.title = 'Demo Page'
    return (
      <div className="Demo">
        Demo Page
      </div>
    )
  }
```
3. **Add to router:** In the routes file route.jsx , Add the path and component 
> Caution: if you add any route code below the 404 component code, it won't work

```js
const Main = props => (
  <ReactRouterDOM.HashRouter>
    <Navbar />
    <Switch>
      <Route path="/" exact component={home} />
      <Route path="/demo" exact component={demo} />
      {/*<Route path="/route" exact component={component} />*/}
      <Route component={_404} />

      {/* dont add any route here.*/}
    </Switch>
  </ReactRouterDOM.HashRouter>
)
```

here's a simple route structure

In React Router, routes are evaluated in the order they are defined. When you have a catch-all route like <Route component={_404} /> placed before specific routes, it will match any path that hasn't been matched by previous routes, including the /demo route.

4. **Load:** Load the script of your page in index.html with mime type 'text/babel'

```js
<script src="Components/pages/demo.jsx" type="text/babel" charset="utf-8"></script>
```
5. **Navigate URL**: type ``http://127.0.0.1:5500/#/route-name`` to URL bar and it will load your page.