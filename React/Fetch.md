```js
import { useEffect, useState } from "react";

const useFetch = (url) => {
  const [data, setData] = useState(null);
  const [isPending, setIsPending] = useState(true);
  const [error, setError] = useState(false);

  useEffect(() => {
    const abortCont = new AbortController();

    fetch(url, { signal: abortCont.signal })
      .then((res) => {
        if (!res.ok) {
          throw Error("response from server is not ok");
        }
        return res.json();
      })
      .then((data) => {
        setError(false);
        setData(data);
        setIsPending(false);
      })
      .catch((err) => {
        if (err.name === "AbortError") {
          console.log("aborted fetch");
        } else {
          console.log("message", err.message);
          setIsPending(false);
          setError(true);
        }
      });
    return () => abortCont.abort();
  }, [url]);
  return { data, isPending, error };
};
export default useFetch;
```

https://codesandbox.io/s/pair-liberian-h0qsy?file=/src/Book.js:441-705
```
useEffect(
    (isbn) => {
      console.log("useEffect");
      fetch(url)
        .then((response) => response.json())
        .then((data) => {
          setBook(data);
          setImgSrc(`${IMG_URL}${data.covers[0]}-L.jpg`);
        });
    },
    [isbn]
  )
```