https://developer.mozilla.org/en-US/docs/Learn/Forms/Your_first_form

https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form

```html
<form action="" method="get" class="form-example">
  <div class="form-example">
    <label for="name">Enter your name: </label>
    <input type="text" name="name" id="name" required>
  </div>
  <div class="form-example">
    <label for="email">Enter your email: </label>
    <input type="email" name="email" id="email" required>
  </div>
  <div class="form-example">
    <input type="submit" value="Subscribe!">
  </div>
</form>
```

```html
<form>
          <label className="mr-10">Transaction Date</label>
          <input
            id="date"
            type="date"
            defaultValue="0000-00-00"
            onChange={changeDate}
          />
          <button
            className="small"
            type="submit"
            onClick={filterItem}
            value={date}
          >
            {console.log(date)}
            Filter
          </button>
</form>
```