### customHook

Follow the code below and see how it mostly works.

```js
import { useState, useEffect } from "react";

function useFetch(url) {
  const [data, setData] = useState([]);

  useEffect(() => {
    fetch(url)
      .then((res) => res.json())
      .then((d) => setData(d));
  }, [url]);
  return [data];
}

export default useFetch;
```
