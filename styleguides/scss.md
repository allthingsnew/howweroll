# SCSS Styles

## Indentation

Use four-space indentation.

## Whitespace

Never leave trailing whitespace or whitespace on empty lines.

## Blocks

Use a single space before `{` in rule blocks.

Use a single space before and after modifiers like `+`, `>`, and `~`.

## Properties

Use a single space after `:` in declarations.

Units should not be used with a `0` (`padding: 0;`).

Lead decimals with a `0` (`opactiy: 0.3;`).

## Nesting

Use nesting sparingly! It comes with a cost. A common mistake is to think of Sass
nesting like the DOM. Not everything should be nested. Nesting merely saves you
the hassle of having to retype selectors multiple times for modifying situations.

Don't nest any deeper than 3 levels deep.

Never nest an id `#` selector.

Never specify tags with id selectors (`ul#my-list`).

Place a single empty line between nested declarations.

Order your nesting blocks in the general order of your HTML structure.

## Comments

Always use `//` commenting style instead of css comments `/* */`.

## Nomenclature

Prefer classnames over ids.

Use `lower-case-hyphen-css-case`.

Prefer direct descendant selectors by defualt (`ul > li`).

Use as few selectors as possible.

Describe what a components function is rather than using generic names.

## Images

Image filenames are specially named with each part separated by a hyphen. A name
should contain the following:

1. UI Module
1. Function of Module
1. *(optional)* Interative State

Examples:

    module-function-state.png
    accordion-titlearrow-on.png
    nav-bg.png
    icon-facebook.png
    logo-sitename.png
    btn-buynow.png

Use shorthand for things that are easily recognizable like `bg`, `bd`, and `btn`.

Prefer font icons over images and prefer `png` over other types of images.

All images must have a high-def version (2x).
