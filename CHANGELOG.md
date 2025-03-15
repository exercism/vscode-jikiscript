# Change Log

All notable changes to the "jikiscript" extension will be documented in this file.

Check [Keep a Changelog](http://keepachangelog.com/) for recommendations on how to structure this file.

## [0.3.0]

- Fixed `set` and `change` syntax to accept complex expressions in accessor syntax `e.g. variable[some expression]`
- Added a meta token to the `x` in `set x to` and `change x to` as `meta.variable.assignment.subject.jikiscript`.
- Changed the token of `x` from `variable.jikiscript` to `variable.name.jikiscript`
- Changed `variable[some expression]` to only have the part `variable` tagged as `variable.name.jikiscript`
- Added `some expression` in `variable[some expression]` to have the token `meta.variable.accessor.javascript`
- Added _illegal usage_ detection of the keywords: `break`, `next`, and `continue`, which can only be used inside enumeration / loops
- Added _illegal usage_ detection of the keyword: `return`, which can only be used inside a function definition
- Fixed missing token on `do` for `function` definition
- Changed `meta.function.identifier.jikiscript` to `meta.function.name.jikiscript`
- Remove incorrectly scoped `meta.function.name` (without `.jikiscript`)
- Added `meta.function.arguments.jikiscript` for the entire function argument list
- Added `meta.function.argument.jikiscript` for each individual argument without the `,` / whitespace
- Added `meta.function.identifier.jikiscript` for the _entire_ `namespace#name` in a function definition
- Removed duplicated `string` literal definition
- Added support for the keyword `is` (comparison `==`)

## [0.2.1]

- Fixed `do` detection for `if` and nested `if`
- Fixed `meta.conditional.if.expression.jikiscript` token on conditional expressions
- Fixed missing `constant.numeric.jikiscript` for number literals

## [0.2.0]

- Added support for `my#function_name` in `function` definitions and function calls
  - `meta.function.namespace.jikiscript` (matching `my#`)
  - `support.constant.my.jikiscript` (matching `my`)
  - `punctuation.separator.namespace.jikiscript` (matching `#`)
- Changed `for each do` support:
  - Changed `for`, `each`, `in`, `indexed by` when used together from `keyword.control.jikiscript` to `keyword.control.enumerable.jikiscript`
  - Changed the `enumerator` from `variable.other.enumerator.jikiscript` to `variable.other.enumerable.current.jikiscript`
  - Changed the `enumerable` from `variable.other.enumerable.jikiscript` to `meta.enumerable.subject.jikiscript` (as this can be a function call, accessed list index or object)
  - Changed the `index` from `variable.other.index.jikiscript` to `variable.other.enumerable.index.jikiscript`
- Added support for correct token detection for `enumerable` in `for each` (which can be an expression)
- Added support for `function` body detection (matching `end` with `do`)
- Added support for `for each` body detection (matching `end` with `do`)
- Added support for `if` / `else if` / `else` body detection (matching `end` with `do`)
- Added support for `repeat n times do`
- Added support for `repeat_xxx` body detection (matching `end` with `do`)
- Added support to detect illegal usage of keywords used outside of correct syntax or context
- Removed `meta.function.method.*` in favour of a single `meta.function.jikiscript`
- Changed `meta.function-call.jikiscript` to `meta.method-call.jikiscript`
- Added `meta.function-call.jikiscript` with support for `my#` namespace
- Added support for built in functions (e.g. `concatenate`, `push`). These are tagged with `support.function.jikiscript`.
- Changed minimum VS Code version (lowered)

## [0.1.0]

- Initial release
