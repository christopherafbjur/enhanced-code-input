# sanity-plugin-code-input-enhanced

This is a fork of the [official @sanity/code-input](https://github.com/sanity-io/sanity/tree/next/packages/%40sanity/code-input) plugin which adds various capabilities.

# Temp installation

1. Clone and add folder to plugins/ folder of Sanity project
2. Add `code-input-enhanced` to sanity.json in "plugins"

Currently only a subset of languages and features are exposed, over time we will implement a richer set of options.

## Installation

```
sanity install code-input-enhanced
```

## Usage

Use it in your schema types:

```js
// [...]
{
  fields: [
    // [...]
    {
      name: "exampleUsage",
      title: "Example usage",
      type: "code",
    },
  ];
}
```

Note that the above only works if you import and use the `all:part:@sanity/base/schema-type` part in your schema.

## Options

- `language` - Default language for this code field
- `languageAlternatives` - Array of languages that should be available
- `theme` - Name of the theme to use. Possible values: `['github', 'monokai', 'terminal', 'tomorrow']`
- `withFilename` - Boolean option to display input field for filename

```js
// ...fields...
{
  name: 'exampleUsage',
  title: 'Example usage',
  type: 'code',
  options: {
    language: 'js'
  }
}
```

## Data model

```js
{
  _type: 'code',
  language: 'js',
  highlightedLines: [1, 2],
  code: 'const foo = "bar"\nconsole.log(foo.toUpperCase())\n// BAR'
}
```

## License

MIT-licensed. See LICENSE.
