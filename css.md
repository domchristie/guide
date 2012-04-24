# CSS

## Syntax and Formatting

* Use hyphen-delimited, lowercase selectors (avoid underscores, CamelCasing, or camelBack)
* Use soft-tabs with a two space indent
* Put spaces after `:` in property declarations
* Put spaces before `{` in rule declarations
* Use multi-line declarations (i.e. one declaration per line): makes diffs easier
* Group similar declarations together e.g. group box-model and typography declarations separately (don't necessarily order alphabetically)
* Use hex colour codes `#000`, unless using `rgba`
* Use [Bourbon](http://thoughtbot.com/bourbon/) (or similar) to generate cross-browser declarations
* Separate closely related rules (e.g. pseudo selectors) with a single carriage-return; roughly related rules with two line-breaks; and significantly different rules with a comment banner
* When rule sets become rather long, consider breaking them out into their own files

A good example:
    
    /* ------------------------------------*\
     $Conversations
    \*------------------------------------ */

    .conversations-list {
      border: 1px solid #000;
      box-shadow: 0 -1px 0 rgba(0,0,0,.5); /* prefixes left out for brevity */
    }
    
    .conversation {
      color: #f00;
    }
    
    /* ------------------------------------*\
     $Messages
    \*------------------------------------ */
    
    .message {
      background: #fff;
    }
    .message:hover {
      background: #ffc;
    }

## Typography and Layout

* Start with a [modular scale](http://modularscale.com/). Choose an appropriate scale according to the content type. 
* Avoid applying `font-size` declarations to large blocks of content
* Try to use `em` for `font-size` declarations as much as possible. Should calculations become tricky, use `rem` with `px` fallbacks
* Use `%` widths for layout style where possible (this will make adapting for various screen sizes easier). Depending on the layout, setting a `max-width` may be necessary.

For example:

    .container {
      width: 95%;
      max-width: 500px;
      margin: 0 auto;
    }


### Defining headings

* `hN` tag rules should only be defined once to ensure a consistent design throughout
* Define corresponding class names to allows the heading styles to be used elsewhere:


    h1, .h1 {
      font-size: 1.618em;
      font-weight: bold;
    }
    h2, .h2 {
      text-transform: uppercase;
      font-weight: bold;
    }


## Organisation

Think in terms of OOCSS and [SMACSS](http://smacss.com/):

* Split styles into:
  * **Reset**
  * **Base**: basic element selectors; no id or class name selectors
  * **Layout**: the major layout components on the page e.g. `.header`, `.footer`
  * **Modules**:
  * **State**: often prefixed with `is-`

### Modules

Todo:

* Discuss OOCSS mindset (`.hd`, `.bd`, `.ft`)

### File organisation

(WIP)

Something along the lines of: [SCSS toolkit](https://github.com/davidrapson/scss-toolkit)

## References:

* CSS Wizardry:
  * [HTML/CSS coding style](http://csswizardry.com/2012/04/my-html-css-coding-style/)
  * [General CSS notes, advice and guidelines](https://github.com/csswizardry/CSS-Guidelines/blob/master/CSS%20Guidelines.md)
* [GitHub CSS styleguide](https://github.com/styleguide/css)
* [SMACSS](http://smacss.com/)
* [OOCSS](https://github.com/stubbornella/oocss/wiki)
* [SCSS toolkit](https://github.com/davidrapson/scss-toolkit)
* [CSS Lint](http://csslint.net/)
* [Modular scale](http://modularscale.com/)
* [Bourbon](http://thoughtbot.com/bourbon/)
