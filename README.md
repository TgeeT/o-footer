# Footer module

Origami module for the FT responsive page footer.

## Module contents

This module contains three assets:

* **footer.mustache** - The template that renders the footer HTML.
* **footer.json** - The footer content to be rendered by the template.
* **main.scss** - The SASS that compiles into the footer CSS.

## Dependencies

This module depends on:

* **origami/grid-module** - for layout CSS
* **Mustache** - for rendering the template
* **SASS** - For compiling the CSS
* **Browser support for HTMl5 semantic elements** - or HTML5 Shiv/Shim

The footer will soon also depend upon **origami/colors-module** for colour variables and **origami/fonts-module** for fonts.

## Template

`footer.mustache` expects a `footer` object, containing three properties:

* `links` - an array of objects, each containing two properties:
    * `text` - The link text to display, e.g. "Privacy policy"
    * `href` - The path for the link to go to, e.g. "http://www.ft.com/privacy/policy"
* `copyrightYear` - The year to display with the copyright, e.g. 2013
* `copyrightText` - The text to display alongside the copyright notice.

## Content

`footer.json` contains the default content to display in the footer. It is recommended that this is used verbatim, but it can be altered after parsing, or even substituted with a custom version (following the same structure), if necessary.

## Stylesheet

The SCSS is defined in `main.scss`. There are no varibles, functions or mixins that are expected to be of use outside this module.


## Responsive behavior

The on small and medium screens, the footer links will render in two vertical columns. On larger screens, the links will render horizontally.

In order to make the copyright text wrap nicely at all screen sizes, the copyright year has a word break element after it, and the `copyrightText` is set to not wrap. This means that if you replace the content of `copyrightText` for something much longer, it is advisable to put further `<wbr/>` elements inline. For example:

`copyrightText: "This is a really really long piece of copyright related text, that may wrap at small screen sizes, so if it does wrap, I want the line break to be here <wbr /> to make things nice and predictable.`