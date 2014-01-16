# SCSS Styles

## Indentation

Use four-space indentation.

## Whitespace

Never leave trailing whitespace or whitespace on empty lines.

## Documentation & Commenting

Always use `//` commenting style instead of css comments `/* */`.

Every file must have a header 1 at the top naming the file followed by a header 3
with a brief description of the file's contents.

Comments generate docs so be sure to mark off sections with appropriate headers.

## Blocks

Use a single space before `{` in rule blocks and place it on the same line as
the last selector.

Prefer to keep selectors on the same line.

Use a single space before and after modifiers like `+`, `>`, and `~`.

## Properties & Values

Use a single space after `:` in declarations.

Units should not be used with a `0` (`padding: 0;`).

Lead decimals with a `0` (`opactiy: 0.3;`).

Keep properties and values in lowercase and short if possible. Prefer shorthand
for hex values.

Prefer `em` when font size in relative to a component's context, `rem` when
setting fixed font sizes. Don't use units with `line-height`.

Stack properties like the box model with outer properties nearer the top and inner
or inessential properties nearer the bottom. Place `display` at the top.

Example:

    .styleguide {
      display: none;
      position: absolute;
      top: 0;
      left: 0;
      z-index: 100;
      float: left;
      clear: both;
      margin: 0;
      width: 300rem;
      height: 200rem;
      border: 1px solid #0f0;
      padding: 0;
      font: 1.5em helvetica, sans-serif;
      line-height: 2;
      color: #c00;
      background: rgba(0, 0, 0, 0.5);
    }

## Nesting

Use nesting sparingly! It comes with a cost. A common mistake is to think of Sass
nesting like the DOM. Not everything should be nested. Nesting merely saves you
the hassle of having to retype selectors multiple times for modifying situations.

Don't nest any deeper than 3 levels deep.

Never nest an id `#` selector.

Never specify tags with id selectors (`ul#my-list`).

Place a single empty line between nested declarations.

Order your nesting blocks in the general order of your HTML structure.

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
1. Interative State *(optional)*

Examples:

    module-function-state.png
    accordion-titlearrow-on.png
    nav-bg.png
    icon-facebook.png
    logo-sitename.png
    btn-buynow.png

Use shorthand for things that are easily recognizable like `bg`, `bd`, and `btn`.

Prefer font icons over images and prefer `png` over other types of images.

All images must have a high-def version (2x). The exception is images that are
already scaled down to fit their container.
