⚡️[Previous #100DaysOfCode log](https://twitter.com/most_mojo/status/1085674532982214662)

---

### Day 1: Saturday, 4th May, 2019

**Today's Progress**

• Key CSS grid terms: `container, row, column, area, items, cells, display: grid`.

• Downloaded new Mozilla Firefox and checked out grids in dev tools w/ line numbers.

• Practiced moving grids around on codepen with `grid-row` & `grid-column` syntax.

**Link(s) to work**

1. [Codepen grids](https://codepen.io/most_mojo/pen/RmwKWd)

---

### Day 2: Sunday, 5th May, 2019

**Today's Progress**

• Continued learning CSS grid - infinite `col` span using -1.

• Name grid lines: ex. `grid-template-rows: [ header-start ] 100px [ header-end box-start ] 200px [ box-end main-start ] 400px [ main-end footer-start ] 100px [ footer-end ];`.

• Functionality of cols using `grid-template-columns: repeat(3, [ col-start ] 1fr [ col-end ]) 200px [ grid-end ]; &rarr; col-start-1 col-end-1, col-start-2 col-end-2`, etc.

**Link(s) to work**

1. [Codepen grids](https://codepen.io/most_mojo/pen/RmwKWd)

---

### Day 3: Monday, 6th May, 2019

**Today's Progress**

• More on CSS grids. New elements: `grid-auto-rows` for `implicit` grids w/ keyword `dense` to avoid 'holes'.

• Elements similar to flexbox: `justify-items` and `align-items` (and self) for X & Y axis alignment. Also, `max-content` and `min-content` for responsive layouts w/ `auto-fit`/ `auto-fill`.

• Started NEXTER project by Jonas Schmedtmann to put all grid-work into practice. To remember: `grid-template-columns:
    [sidebar-start] 8rem [sidebar-end full-start] 1fr [center-start] repeat(8, [col-start] minmax(min-content, 14rem) [col-end]
    )[center-end] 1fr [full-end];` &rarr; All naming, numeric and minmax functions utilized in one place 🤓.

**Link(s) to work**

1. [Codepen grids](https://codepen.io/most_mojo/pen/EzagWr)
2. [Nexter project](https://github.com/mostmojo/nexter)

---

### Day 4: Tuesday, 7th May, 2019

**Today's Progress**

• Dissected Craft CMS / PHP Twig site. Familiarized myself with Twig syntax, ternary operators and framework. Content blocks within matrix fields can be selected. For loops with array indices can display images; with transform props! Remember: `{% set variable = entry.title %}` for logic vs `<p>{{ entry.title }}</p>` for display. 

• Looked into yarn builds, compilers, SASS variables, the asset pipeline and began to break down Twig logic. 

• Worked on layout of Nexter project. Used `line names` within `grid-column` property in practice to align sections. Ex. `grid-column: col-start 7 / full-end;`

**Link(s) to work**

1. [Nexter project](https://github.com/mostmojo/nexter)
2. [NH - private but it's there!](https://github.com/ten4design/nicholas-hare)

---

### Day 5: Wednesday, 8th May, 2019

**Today's Progress**

• Twig - base inheritance w/ `{% extends '_base' %}` `{% block content %} {% endblock %}`. Used global handles: `@assetUrl, {{ entry.url }}, {{ url( '/.../ ~ entry.slug' ) }}, {{ siteUrl }}` to display different url scenarios. 

• JS `cloak` library, `% placeholder selectors` in SASS - `@extends` , `itemscope` using schema.org, `vendor` files and Craft CMS globals: `getPrev, orderBy, postDate, {% include x %}`, `paginated` entries and `craft.app.request`. `Invisible` classes  to keep semantic structure: h1 > h2 > h3, etc. Also - `loop.last` & `|raw` filter for escaping in Twig.

• Continued on nexter project - **features** layout with CSS grids within `grid items`. Added svg files with `use xlink:href` and `sprite` files.

**Link(s) to work**

1. [SASS @extends docs](https://sass-lang.com/documentation/at-rules/extend)
2. [Schema](https://schema.org/)

---
### Day 6: Thursday, 9th May, 2019

**Today's Progress**

• Researched `breadcrumbs` for general UI/UX design - extra navigation. Studied *graceful degredation* vs *progressive enhancement* for JS & non JS browsers.  

• Continued exploring SASS `$variables`, reusable components and utilities; `@extend` with `%` selectors. Looked into the power of `display: inline-block` vs `block`

• Deciphered variables in `twig` syntax with k:v pairs with arrays which hold social icon data (handles, urls, icon font, aria labels) to render them in HTML. Ex.`{% for class, content in footer_social if content[1] %}
<li><a href="{{ content[1] }}" class="a icon icon--{{ class }}" aria-label="{{ content[0] }}"></a></li>
{% endfor %}`

**Link(s) to work**

1. [Breadcrumbs](https://www.nngroup.com/articles/breadcrumbs/)
2. [NH - private](https://github.com/ten4design/nicholas-hare)
3. [MDN graceful degredation](https://developer.mozilla.org/en-US/docs/Glossary/Graceful_degradation)
4. [CSS display](https://css-tricks.com/almanac/properties/d/display/)

---
