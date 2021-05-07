from take home "News"

```js
      <Router>
        <form>       </form>
        <hr />
        <Switch>
          <Route exact path="/">
            <NewsList news={news} />
          </Route>
          <Route path="/article/:id"></Route>
        </Switch>
      </Router>

```

from take home "Librian"
```js
     <Router>
        <div>
        <h1> Librian</h1>
        <p> type "isbn/9780140328721" after current url in address bar </p>
        <Link to="isbn/9780140328721"> 9780140328721 </Link>
        <Link to="isbn/1573226122"> 1573226122 </Link>
        </div>
        <Switch>
          <Route path="/isbn/:isbn">
            <Book />
          </Route>
          <Route path="/">
          </Route>
        </Switch>
      </Router>
```
