# Native \<img /> vs next/image

Developer has to:

* Ensuring your image is responsive on different screen sizes
* Optimizing your images with a third-party tool or library
* Only loading images when they enter the viewport

#### next/image

[`next/image`](https://nextjs.org/docs/api-reference/next/image) is an extension of the HTML `<img>` element, evolved for the modern web

Next.js also has support for Image Optimization by default. This allows for resizing, optimizing, and serving images in modern formats like [WebP](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image\_types#webp) when the browser supports it

It allows Next.js to automatically adopt future image formats and serve them to browsers that support those formats.

Automatic Image Optimization works with any image source. Even if the image is hosted by an external data source, like a CMS, it can still be optimized.

#### Using the Image Component

Instead of optimizing images at build time, Next.js optimizes images on-demand, as users request them. (not static generator)

Images are lazy loaded by default. That means your page speed isn't penalized for images outside the viewport. Images load as they are scrolled into viewport.

Images are always rendered in such a way as to avoid [Cumulative Layout Shift](https://web.dev/cls/), a [Core Web Vital](https://web.dev/vitals/#core-web-vitals) that Google is going to [use in search ranking](https://webmasters.googleblog.com/2020/05/evaluating-page-experience.html).



