# VSCode JikiScript

Add language support for [Exercism's Bootcamp](https://bootcamp.exercism.org/) language: JikiScript

![Example highlighted code](./media/highlight.png)

## Features

- Syntax highlighting as of Level 10 (updated: **2025-03-16**)
- Snippets for common actions
- Language support (`.jiki`, `.jikiscript`, .`jikis` and embedded markdown)

### Strong contextual support

The highlighter can detect illegal use of `break`, `continue`, `next` and `return` in any scope.

```jikiscript
// Illegal
return
break
continue
next
```

```jikiscript
function test do
  // Illegal
  break

  // Fine
  return
end
```

```jikiscript
if true do
  // Illegal
  break
end
```

```jikiscript
repeat_forever do
  // Illegal
  return

  // Fine
  continue
end
```

## Known Issues

### Missing colors

If operators such as `>=` or `and` are not highlighted, support for `keyword.operator.*` is missing in your theme.
You can use [custom theming for syntax highlighting](https://code.visualstudio.com/docs/editor/themes#_editor-syntax-highlighting).
See the section **Custom Theming**.

### Strict whitespace

The following code will not highlight properly:

```jikiscript
if(pos["direction"] == "up") do
```

But the following does work:

```jikiscript
if (pos["direction"] == "up") do
```

The highlighter will enforce good use of whitespace, so please make sure you have word boundaries around _all_ keywords.

### Illegal highlighting

As you write your code, highlighting may indicate something is illegal.
This is often because your code _is_ incomplete.

## Custom theming

The following can be added to your [`editor.tokenColorCustomizations`](https://code.visualstudio.com/docs/editor/themes#_editor-syntax-highlighting), either directly inside `textMateRules`, or nested underneath your theme(s):

```json
{
  "scope": "support.function.jikiscript",
  "settings": {
    "fontStyle": "underline"
  }
},
{
  "scope": [
    "support.constant.my.jikiscript",
    "punctuation.separator.namespace.jikiscript",
  ],
  "settings": {
    "fontStyle": "bold"
  }
},
```

## Release Notes

See [CHANGELOG.md](./CHANGELOG.md)
