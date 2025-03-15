# Change Log

All notable changes to the "jikiscript" extension will be documented in this file.

Check [Keep a Changelog](http://keepachangelog.com/) for recommendations on how to structure this file.

## [0.2.1]

- Fix `do` detection for `if` and nested `if`
- Fix `meta.conditional.if.expression.jikiscript` token on conditional expressions
- Fix missing `constant.numeric.jikiscript` for number literals

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
