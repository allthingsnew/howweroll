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

## Curly Braces

Place them on the same line as the thing that necessitates them.

Bad:

    function()
    {

Good:

    function(){

Always wrap blocks to the next line and always use curly braces.

Bad:

    if (foo) bar()
    if (foo) { bar() }

Good:

    if (foo) {
      bar()
    }

## Semicolons

Don't use them except in these situation:

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

Place a single space before `(` other than function calls. Use a single space
when needed to make things more readable.

Never leave trailing whitespace or whitespace on empty lines.

## Functions

Prefer named functions over anonymous. (This is better for stack tracing.)

## Returned Values

Truthy values should always be specified as either `true` or `false`.

Use `null` for values that are removed.

Never set something to `undefined`, only test for it as something not yet set.
