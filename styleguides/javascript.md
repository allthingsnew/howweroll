# Javascript

Use [Standard JS](http://standardjs.com/) style. You can use the rules for this style
[here](http://standardjs.com/rules.html). We decided to back this project because it is
widely accepted within the Javascript community (adopted by NPM), it saves from
*bikeshedding* about style since it's all-or-nothing/non-configurable, and we want to
support a movement to universalize JS code style across projects, companies, development
houses, open source projects, and more. The less time engineers have to spend time on
styling their code the more time they have for what really matters.

To follow this style please do at least one of the following:

* Install standard globally (`npm install -g standard`) and test your code.
* Install the standard linter in your favorite IDE like
  [SublimeLinter-contrib-standard](https://github.com/Flet/SublimeLinter-contrib-standard)
  for Sublime Text or [Linter-js-standard](https://atom.io/packages/linter-js-standard)
  for Atom or others.
* Use the linter gulp task: `gulp lint`.

### Basic Standard rules
- **2 spaces** – for indentation
- **Single quotes for strings** – except to avoid escaping
- **No unused variables** – this one catches *tons* of bugs!
- **No semicolons** – [It's][1] [fine.][2] [Really!][3]
- **Never start a line with `(` or `[`**
  - This is the **only** gotcha with omitting semicolons – *automatically checked for you!*
- **Space after keywords** `if (condition) { ... }`
- **Space after function name** `function name (arg) { ... }`
- Always use `===` instead of `==` – but `obj == null` is allowed to check `null || undefined`.
- Always handle the node.js `err` function parameter
- Always prefix browser globals with `window` – except `document` and `navigator` are okay
  - Prevents accidental use of poorly-named browser globals like `open`, `length`,
    `event`, and `name`.

[1]: http://blog.izs.me/post/2353458699/an-open-letter-to-javascript-leaders-regarding
[2]: http://inimino.org/~inimino/blog/javascript_semicolons
[3]: https://www.youtube.com/watch?v=gsfbh17Ax9I

[Standard Github Repo](https://github.com/feross/standard)
