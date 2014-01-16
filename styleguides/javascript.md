# Javascript Coding Style

## Line Length

Keep lines shorter than 80 characters.  It's better for lines to be
too short than to be too long.  Break up long lists, objects, and other
statements onto multiple lines.

## Indentation

Use two-spaces (not tabs).

## Case & Naming

All identifiers (variables, functions, objects, arrays, etc.) are to use
`lowerCamelCase` style.

Class names use `UpperCaseCamelStyle`.

Filenames use `lower-case-hyphen-css-case`.

Constants use `ALL_CAPS_UNDERSCORE_CASE`.

All names should specify what they signify. Short, one-letter variables or
nonsense named functions are a no no.

## Curly Braces

Place them on the same line as the thing that necessitates them.

An `else`, `elseif`, `catch` statement belongs on the same line as
the preceeding `}`.

Bad:

    function()
    {

Good:

    function () {

Always wrap blocks to the next line and always use curly braces.

Bad:

    if (foo) bar()
    if (foo) { bar() }

Good:

    if (foo) {
      bar()
    }

## Semicolons

Don't use them except for:

* Where they are required like `for (;;)`
* In front of a line beginning with a `(` or `[`

Bad:

    Foo.doSomething();
    (function(){
      myLoop:for (var i = 0, len = list.length; i < len; ++i) {
        Bar.compile(list[i]);
        if (i === 3) {
          break myLoop;
        }
      }
    })();

Good:

    Foo.doSomething()
    ;(function(){
      myLoop:for (var i = 0, len = list.length; i < len; ++i) {
        Bar.compile(list[i]);
        if (i === 3) {
          break myLoop;
        }
      }
    })()

Generally if you are in a position to need a semicolon prepending a line of code
in any other situation (starting with a `+`, `-`, `/`, etc.) then you probably need
to rework your code!

## Comma First

In lists separated by commas that wrap to new lines place the commas
at the beginning of the line (NPM style).

    var someVar = require('someModule')
      , another = require('another')
      , oneMore = require('yetAnotherThing')
      , arrays = [ "one"
                 , "two"
                 , "three"
                 ]
      , objects = { "one" : 1
                  , "two": 2
                  , "three": 3
                  }

## Whitespace

Place a single space before `(` and after `)` other than function calls.
Use a single space when needed to make things more readable.

Never leave trailing whitespace or whitespace on empty lines.

## Var Statements

Use one `var` per context block at the top.

Separate out declarations, one per line.

Every variable must be declared in a `var` statement.

Bad:

    var someVar = require('./something')
      , another, andAnother, oneMore = []

Good:

    var someVar = require('./something')
      , another
      , andAnother
      , oneMore = []

## Strings

Always prefer single-quotes over double-quotes unless you need to escape
a single quote in the string.

Do not escape newlines with `\` when setting long strings. Use concatenation
instead.

Good:

    var longString = 'Lorem ipsum Consectetur dolor culpa cupidatat in '
                   + 'dolor labore eu nisi qui consectetur Ut veniam '
                   + 'tempor sint dolor eu esse cillum fugiat officia '
                   + 'reprehenderit ex enim cupidatat nostrud in aliqua.'

## Functions

Prefer named functions over anonymous. (This is better for stack tracing.)

Within proceedural blocks assign anonymous functions to variables instead
of declaring functions by name.

Good:

    function aFunctionName (arg1, arg2, arg3) {
      var someOtherVar = arg1 + arg2
        , toUseLater

      function adHocFunc (piece) {
        return '' + piece
      }

      if (arg1 === 'hello') {
        toUseLater = function () {
          return 'hello'
        }
      }

      return arg1 + adHocFunc(piece) + arg3
    }

## Returned Values

Truthy values should always be specified as either `true` or `false`.

Use `null` for values that are removed.

Never set something to `undefined`, only test for it as something not yet set.

## Operators

Always use `===` and `!==`.

Place a single-space before and after assignment, logical, mathematical, and
bitwise operators.

Do not leave operators hanging on the end of lines. If an expression spans
multiple lines wrap the operator to the beginning of the next line. (This
especially includes the object `.` operator.)

Bad:

    var a = b+2*3
      , c = dog|cat

    if (a||c) {
      doSomething()
    }

Good:

    var a = b + 2 * 3
      , c = dog | cat

    if (a || c) {
      doSomething()
    }

## Comments & Documentation

Comment only with `//`.

Comment often for inline documentation. Place a Header 1 at the top of every
file with the module/class name and a Header 3 with a brief description of what
it does.

## Linting (Hinting)

Always JSHint your code. We use a Grunt task to do this for us but it's a good
idea to have some sort of Linter enabled on your editory of choice.

## Danger Zones

Don't use `with` or `eval`, ever.
