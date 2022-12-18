---
description: https://www.youtube.com/watch?v=wgWwJSnhgDU
---

# Coding Complex App Logic?

Key is to visualize, even it's not useful but I can learn st from there docs about organizing complex logics, to be read



```javascript
const [isLoading, setIsLoading] = useState(false);
const [isCanceled, setIsCanceled] = useState(false);
const [error, setError] = useState(null);

<form onSubmit={event => {
    if (isLoading) return;
    
    submitData(event)
        .then(()=>{
            if (isCanceled) return;
            //...logics
            setIsLoading(false);
            })
        .catch(err => {
            if (isCanceled) return;
            setIsLoading(false);
            setError(err);
        })
    setIsLoading(true);
}
/>
```

```javascript
```

Some keywords: state machines, finite states

> [https://xstate.js.org/docs/](https://xstate.js.org/docs/)
