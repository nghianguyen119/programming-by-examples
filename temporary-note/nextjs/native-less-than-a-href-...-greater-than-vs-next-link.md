# Native \<a href="…"> vs next/link

The whole page will be fetched when the link is clicked

```
<Link href="/about">
    <a>Go to about</a>
</Link>

is better than for SEO purpose, a link should be in <a> tag
<Link href="/about">
    Go to about
</Link>
```

useRouter() hook to go to a link in function

prefetch, if true, fetch the Link in viewport (actual dislay that user sees), only in production, is disable in slow network or save-data mode

