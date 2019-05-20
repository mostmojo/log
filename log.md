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
<a href="{{ content[1] }}" class="a icon icon--{{ class }}" aria-label="{{ content[0] }}"></a>
{% endfor %}`

**Link(s) to work**

1. [Breadcrumbs](https://www.nngroup.com/articles/breadcrumbs/)
2. [CSS display](https://css-tricks.com/almanac/properties/d/display/)

---

### Day 7: Friday, 10th May, 2019

**Today's Progress**

• Looked into JavaScript `(function() document.body.className += ' js')` to grab contents of the body in a document that contain JS and render them into `script` tags.

• Twig logic with additional conditions for displaying contents within a footer of a Craft CMS-based site. Remember: `{% set casting_case = '' %}` syntax for loops - `objects` and `arrays` came handy with navbar segments.

• Created `/casting` section, fields, design layout, entries in Craft for new Studio Ramsay page. Made button component in asset pipepline and ensured responsiveness. First deployment w/ `jupiter` - AWS & docker!

**Link(s) to work**

1. [document.body.className](https://stackoverflow.com/questions/2125993/setting-document-body-classname-as-a-variable)
2. [Studio Ramsay](https://www.studioramsay.com/casting)
3. [Casting commits](https://github.com/ten4design/studio-ramsay/commits?author=mostmojo)

---

### Day 8: Saturday, 11th May, 2019

**Today's Progress**

• Continued Nexter project. Used auto-fit property on parent grid element with minmax to fit contents of the col-grid according to minimum width and 1fr. Anything < 250px would decreased the cols from 3 to 2 to 1, etc. using auto-fit. `grid-template-columns: repeat(auto-fit, minmax(25rem, 1fr));`

• Used `grid-template-columns: min-content 1fr;` on child grid to create cols based on content and adapt. Remember: `fill` property is used to define colors on `svg` icons.

• Made `%heading` placeholder selector for typography and `@extend` into relevant headings throughout project. 

**Link(s) to work**

1. [Nexter](https://github.com/mostmojo/nexter)

---

### Day 9: Sunday, 12th May, 2019

**Today's Progress**

• Built a `story` section with `display: grid` and `display: flex` solutions to align content with images.

• Made reusable helper classes similar to `atomic css` for margins.

• Worked with linear gradients to overlay images and further studied `BEM` syntax.

**Link(s) to work**

1. [Nexter](https://github.com/mostmojo/nexter)
2. [Atomic CSS](https://acss.io/)
3. [BEM syntax](https://twitter.com/most_mojo/status/1127570130517544962)

---

### Day 10: Monday, 13th May, 2019

**Today's Progress**

• Looked into Eric Meyer's Reset CSS stylesheet to reduce browser inconsistencies. Read Twig docs to see how `|length` filter operates.

• Further dive into more complex conditionals in twig to display images with image transforms (Craft CMS), reverse--rows, helper tags for margins, typeset classes to style dynamic content and research `display: inline, block, inline-block`.

• Started the house section of Nexter w/ `<use xlink:href="img/sprite.svg#icon-heart-full"></use>` SVGs, multi-nested classes and grid-items.

**Link(s) to work**

1. [Reset CSS](https://meyerweb.com/eric/tools/css/reset/)
2. [Twig](https://twig.symfony.com/doc/2.x/templates.html#filters)
3. [Nexter](https://github.com/mostmojo/nexter)

---

### Day 11: Tuesday, 14th May, 2019

**Today's Progress**

• Looked into NkdTV layout, craft setup to identify sections, fields, handles, entry types. Looked into image magick error with yarn dependencies, docker config files and node modules. *Tip:* don't `yarn install`, but `yarn build:js` otherwise it overwrites everything you've pasted from older files! 

• Analysed a nav item variable declaration, for loop with 2 parameters and more complex logic to display relevant nav items with highlighting styles upon selection using ternary operators. *Tip:* remember the mighty `.env` file when configuring the DB!

• Finished home card section on Nexter project using CSS grids and flexbox. Used `transform: translateY(50%);` for positioning and `z-index` with `align-self: end` to place an svg file with grid system.

**Link(s) to work**

1. [NkdTV](https://www.nkdtv.com/)
2. [Nexter](https://github.com/mostmojo/nexter)

---

### Day 12: Wednesday, 15th May, 2019

**Today's Progress**

• Studied Craft's `category groups`, `field layouts` and relationships using `source` to identify a for loop that renders content to the browser using a 'work role' category, filtered by 'departments'.  

• Learned about the kanban process, component delegation when working in groups, and maintainable code structure.

• Started a gallery section in Nexter with another grid featuring gallery items, `object-fit: cover` property and `display: block` to prevent whitespace created by inline elements that behave like text. 

**Link(s) to work**

1. [Craft categories](https://docs.craftcms.com/v3/categories.html#category-groups)
2. [Nexter](https://github.com/mostmojo/nexter)

---

### Day 13: Thursday, 16th May, 2019

**Today's Progress**

• Create a new section for client to showcase new `shows`. Ensure all fields and design layout in the CMS was sufficient and had good instructions for client. 

• Relate content by `category groups` to display project status using Craft CMS. Indentation, variable naming and continuity is key. Brief look at `JS polyfills` for IE8 browser knowledge.

• Imitate design & structure from related section and InVision mockup. Got a small taste of `kanban` agile methodology. Made relevant index and entry files in asset pipeline. 

**Link(s) to work**

1. [Nkdtv](https://www.nkdtv.com/)
2. [Kanban](https://www.atlassian.com/agile/kanban)

---

### Day 14: Friday, 17th May, 2019

**Today's Progress**

• Alter existing homepage to make transparent nav bar.

• Begin for loop for featured shows `.slideshow` using BEM and ensuring the related `Show` section contained `showImage` class to successfully complete query and display related content from entry if asset exists. 

• Use `position: absolute`to place headers and links on slideshow responsively. Get my first short code review - helpful to instill way of thought and good practice 🙂.

**Link(s) to work**

1. [Nkdtv](https://www.nkdtv.com/)
2. [Kanban](https://www.atlassian.com/agile/kanban)

---

### Day 15: Saturday, 18th May, 2019

**Today's Progress**

• Create gallery section for nexter project with `display: grid`and `template rows/cols` using span.

• Read about `display: inline, display: block, display: inline-block;` properties to use for footer styling. Inline: `<a>, <img>, <strong>` inlines can behave like `blocks`e.g. `<p>, <h1>`with `display: block` property.

• Hamburger menu for navbar using pseudo elements `::before, ::after` and assigning `content: ""` with `transform: translateY(-2rem);`

**Link(s) to work**

1. [Nexter](https://github.com/mostmojo/nexter)
2. [Inline & block](https://medium.com/swlh/understanding-css-display-none-block-inline-and-inline-block-63f6510df93)

---

### Day 16: Sunday, 19th May, 2019

**Today's Progress**

• Finish nexter project on desktop.

• Add @media queries, change grid layouts to adapt to responsive layout and display on mobile devices with ``$bp-large, $bp-medium` breakpoints. 

• Add @media queries to personal site to test using `@media only screen and (max-width: 900px)`. Look at `max-height, max-width and minmax(min-content, max-content)` properties for adjusting responsive layouts.

**Link(s) to work**

1. [Nexter github](https://github.com/mostmojo/nexter)
2. [Nexter desktop](https://mostmojo.github.io/nexter/)

---

### Day 17: Monday, 20th May, 2019

**Today's Progress**

• Finished Nexter project entirely and got my certificate from udemy 🎉! Ran `npm run build:css` to finalize the compilation and build process including minification for production. Researched *caniuse* website to check CSS grid browser compatibility.

• Study JS properties: `window`, `strict mode`, `this`, `.call() & apply()`, `getAttribute(),` `classList` and `pips`.

• Rendered a slideshow for a home page section where `slideshow addon` is placed within vendor file, `@import` into main scss and js asset pipeline files and relevant `<script>` tags inserted to ensure the class ids and JS was related. Ensure to understand `z-index` power, `::before` pseudo class with `content:"∙"` for slideshow pips and layout. 

**Link(s) to work**

1. [Udemy certificate](https://www.udemy.com/certificate/UC-1TBM8CJY/)
2. [Nexter complete](https://mostmojo.github.io/nexter/)
3. [Caniuse](https://caniuse.com/#search=css%20grids)
4. [window.object](https://developer.mozilla.org/en-US/docs/Web/API/Window)

---

