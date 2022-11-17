# Incremental Static Regeneration (ISR)

```javascript
export async function getStaticProps(){
    return {
        props: {},
        revalidate: 10, // re-generate when a request comes in, at most every 10s
    }
}

// it maybe get called again on serverless function if the path has not been generated
export async function getStaticPaths(){
    return {}
}
```
