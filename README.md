# payload-blurhash

Payload CMS plugin for automatic Blurhash encoding of images.

## Getting started

1. Install the package with `npm i payload-blurhash` or `yarn add payload-blurhash`.
2. Add the plugin to your `payload.config.ts`:

```ts
import computeBlurhash from 'payload-blurhash';

export default buildConfig({
  /* ... */
  plugins: [
    computeBlurhash(),
  ],
});
```

## Plugin options

Optionally, you can pass the following options to tweak the behavior of the plugin:

```ts
export interface BlurhashPluginOptions {
  /*
   * Array of collection slugs that the plugin should apply to.
   * By default, the plugin will apply to all collections with `upload` properties.
   */
  collections?: CollectionConfig['slug'][];

  /*
   * Width to resize the image to prior to computing the blurhash.
   * Default: 32
   */
  width?: number;

  /*
   * Height to resize the image to prior to computing the blurhash.
   * Default: 32
   */
  height?: number;

  /*
   * X component count to pass to the Blurhash library.
   * Default: 3
   */
  componentX?: number;

  /*
   * Y component count to pass to the Blurhash library.
   * Default: 3
   */
  componentY?: number;
}
```

The defaults are chosen somewhat arbitrarily, they are just values that I've found to work nicely for me.