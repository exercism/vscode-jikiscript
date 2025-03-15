# VSCode JikiScript

Add language support for [Exercism's Bootcamp](https://bootcamp.exercism.org/) language: JikiScript

![Example highlighted code](./media/highlight.png)

## Features

- Syntax highlighting as of Level 9 (updated: **2025-03-14**)
- Snippets for common actions
- Language support (`.jiki`, `.jikiscript`, .`js` and embedded markdown)

## Known Issues

Not all highlighting is consistent, for example enumerators and enumerables in `for each` may be highlighted partially.
If operators such as `>=` or `and` are not highlighted, support for `keyword.operator.*` is missing in your theme.

The following code will not highlight properly:

```jikiscript
change list[complex + expression] to some + other + complex + expression
```

But the following does work:

```jikiscript
change list[variable] to some + other + complex + expression
```

## Custom theming

The following can be added to your `editor.tokenColorCustomizations`, either directly inside `textMateRules`, or nested underneath your theme(s):

```json
{
  "scope": "support.function.jikiscript",
  "settings": {
    "fontStyle": "underline"
  }
},
{
  "scope": "support.constant.my.jikiscript",
  "settings": {
    "fontStyle": "bold"
  }
},
{
  "scope": "punctuation.separator.namespace.jikiscript",
  "settings": {
    "fontStyle": "bold"
  }
}
```

## Release Notes

See [CHANGELOG.md](./CHANGELOG.md)
