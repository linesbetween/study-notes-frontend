https://codesandbox.io/s/pair-liberian-h0qsy?file=/src/Book.js
```js
    <div className="book-card">
      <div className="info-container">
        <h2>{book ? book.title : ""}</h2>
        <div className="data-container">
          <p>ISBN {book ? book.isbn_13 : ""}</p>
          <p>Publish Date {book ? book.publish_date : ""}</p>
          <p>Pages {book ? book.number_of_pages : ""}</p>
          <p>
            Publishers{" "}
            {!book ? "" : book.publishers.map((p) => <span key={p}>{p} </span>)}
          </p>
        </div>
      </div>
      <img className="book-cover" src={imgSrc} />
    </div>
```

