---
id: parseAlgoliaHitSnippet
---

Returns the snippeted parts of an Algolia hit.

<!-- prettier-ignore -->
:::info
This function escapes characters.
:::

# Example

```js
import { parseAlgoliaHitSnippet } from '@algolia/autocomplete-preset-algolia';

// Fetch an Algolia hit
const hit = {
  name: 'Laptop',
  _snippetResult: {
    name: {
      value: '__aa_highlight__Lap__/aa_highlight__top',
    },
  },
};
const snippetParts = parseAlgoliaHitSnippet({
  hit,
  attribute: 'query',
});

// => [{ value: 'Lap', isHighlighted: true }, { value: 'top', isHighlighted: false }]
```

# Reference

## Params

### `hit`

> `AlgoliaHit` | required

The Algolia hit to retrieve the attribute value from.

### `attribute`

> `string` | required

The attribute to retrieve the snippet value from.

### `ignoreEscape`

> `string[]` | defaults to `[]`

The characters to skip from escaping.