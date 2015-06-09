# Javascript

In this style guide JS is primary represented with es6 features. These features are supported mainly on the server, but not in all browsers and so should be used sparingly or not at all. *If they are used in the browser, a transpiler should be used
to downgrade the syntax to es5 until all browsers catch up.*

## Quick Points

* Do not use [semicolons](#semicolons).
* Thou shall not write lines longer than 90 characters long.
* Indent with two-spaces (not tabs).
* Prefer to use es6 features where applicable.
* Prefer `let` over `var`.
* Default to `lowerCamelCase` style for naming.
* **Lint your code before pushing up commits!**

## Case & Naming

Most things use `lowerCamelCase` style.

Class names use `UpperCaseCamelStyle`.

Filenames use `lower-case-hyphen-css-case.js`.

Constants you create use `ALL_CAPS_UNDERSCORE_CASE`. (If you require a 
module assigned with `const` there's no need to use all caps.)

Variables storing a promise should be appended with a `P` or `Prom`.

All names should specify what they signify. Avoid single-letter variable names
unless they are being used in a small, single-purpose context.

## Curly Braces

Place them on the same line as the thing that necessitates them.

An `else`, `elseif`, `catch` statement belongs on the same line as
the preceeding `}`.

Bad:

```js
function()
{
```

Good:

```js
function () {
```

Wrap blocks to the next line if they are complex (more than 1 line). And always use curly braces only if wrapping to a new line.

Bad:

```js
if (foo) { bar() }
if (foo)
  bar()
```

Good:

```js
if (foo) bar()
if (foo) {
  bar()
}
```

## Semicolons

Don't use them except for:

* Where they are required like `for (;;)`
* In front of a line beginning with a `(` or `[`

Generally if you are in a position to need a semicolon prepending a line of code
in any other situation (starting with a `+`, `-`, `/`, etc.) then you probably need
to rework your code!

## Comma First

In comma-separated lists that wrap to new lines place the commas
at the beginning of the line (like NPM). Align commas and the closing `]` or `}`
with the parent name. The listed set is indented once.

```js
let myArray = [
  'one'
, 'two
, ['short', 'array', 'can', 'be', 'inline']
, {an: 'object', not: 'too long', 'can-be': 'too'}
]

let objects = {
  foo: true
, bar: {
    embed: 'object'
  , that: 'should'
  , be: 'broken up'
  }
}
```

## Whitespace

Place a single space after function names, `*`, and `)` in function calls.

```js
function myFunc () {}

let fn = function() {}

let generator = function* () {}
```

Segment your code into logical groups with single-empty lines. Be generous with
breaking up code but no need to separate out each line on its own.

Don't add extra lines after or before brackets.

## Strings

Always prefer `'` over `"`.

Do not escape long lines with `\`. Use string templates or concatenation.

```js
let longString = `Lorem ipsum Consectetur dolor culpa cupidatat in
dolor labore eu nisi qui consectetur Ut veniam
tempor sint dolor eu esse cillum fugiat officia
reprehenderit ex enim cupidatat nostrud in aliqua.`
```

## Functions

Prefer named functions over anonymous. (Better stack tracing.)

Within proceedural blocks assign anonymous functions to variables instead
of declaring functions by name.

Truthy values should always be specified as either `true` or `false`.

## If, Else If, Else, Switch

Use ternary conditions when possible.

Prefer `switch` over the use of `else if`.

Rework your code to not use `else` if possible. It's usually easier to read an `if` 
condition that exits the current block instead of the use of an either-or:

```js
// prefer:
function fooOrNot (foo) {
  if (foo) return doSomethingFooish(foo)
  return doUnfooishStuff()
}

// instead of...
function thisOrThat (foo) {
  if (foo) {
    return doSomethingFooish(foo)
  } else {
    return doUnfooishStruff(foo)
  }
}
```

## Operators

Always use `===` and `!==`.

Place a single-space before and after assignment, logical, mathematical, and
bitwise operators (except `!`).

Do not leave operators hanging on the end of lines. If an expression spans
multiple lines wrap the operator to the beginning of the next line. (This
especially includes the object `.` operator.)

## Flow Control

Be sure to not write blocking, synchronous code!

When writing asynchronously prefer to use Promises. Promisify all methods (like
node api methods) that use nodebacks.

Do not use deferred Promises. Use Promise construction instead.

If generators are supported, prefer to use wrapped generators 
([coroutines](https://goo.gl/IZeWPG)) with 
promised flows to minimize on block indenting and explicit uses of `.then()`.

Events should be used for broadcasting data from one component to (potentially)
many. They shouldn't be over-used for abstracting method calls.

Streams should be used for keeping buffered data in memory to a minimum.

## Comments & Documentation

Comment often for inline documentation. Place a Header 1 (in Markup) at the top of every
file with the module/class name and a Header 3 with a brief description of what
it does.

## CommonJS

Use `require` statements at the top of the file or any block that necessitates
them.

Group `require`, `module.exports`, and `exports` statements together. This makes
it easy to see at first glance what a file is requiring and exporting.

## Danger Zones

Don't use `with` or `eval`, ever.
