# README

Remove unused CSS is important in production. With the help of `postcss` and `purgecss` we can achieve 80% CSS size reduced at our first loading.

People who buy beautiful theme for their application trade good productivity for 'orphanage code', they are ashamed of a red light house audit by a scary stupid js bundler.

However, every decision on buying theme is smart.

- Good artist copy, great artist steal! (Picasso)

### Result

[bm](keymastervn.github.com/purgecss-practice-tuandao/public/bm.png)

### Test

Take a look at `javascript/stylesheets/application.scss`

```scss
/*! purgecss start ignore */
/*! @import "components/buttons"; or any sass files */

body {
  @apply bg-blue-500 text-white;
}
/*! purgecss end ignore */
```

The purgecss was let ignored by above magic comment. So we can see a blue background in `localhost:3000`.

If you try add some CSS classes to the body element eg. bg-blue-200 / bg-cyan, text-black. The newer class is not changing CSS because the rest are purged!

### Note

(TODO) `purgecss` is naive, it couldn't detect some CSS over transitions, or with compact templates like `.pug` or `.slim` (inprogress)
