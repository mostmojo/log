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

• Rendered a slideshow for a home page section where `slideshow addon` is placed within vendor file, `@import` into main scss and js files and relevant `<script>` tags inserted to ensure class ids and JS relationship. Understand `z-index` power, `::before` pseudo class with `content:"∙"` for slideshow pips and layout. 

**Link(s) to work**

1. [Udemy certificate](https://www.udemy.com/certificate/UC-1TBM8CJY/)
2. [Nexter complete](https://mostmojo.github.io/nexter/)
3. [Caniuse](https://caniuse.com/#search=css%20grids)
4. [window.object](https://developer.mozilla.org/en-US/docs/Web/API/Window)

---

### Day 18: Tuesday, 21st May, 2019

**Today's Progress**

• Ternary operators in twig to select specific classes for a `header--transparent` vs `header--primary` class. E.g. `{{ site_area == '' ? ' header--transparent' : ' header--primary' }}`. Also, intermediate responsive queries for mobile layout including font & image sizing as per different setting. 

• `style="background-image: url( 'image.getUrl( 'imageTransformName' )' )";` for more stretchable images with transforms for better performance, with hidden `img src` & `position: absolute; top: -999;` values present to contain ARIA & accessibility labels. 

• Basic run-through of `bash` scripts that configure and prompt `nginx, docker, CraftCMS, Jupiter & Saturn` deployment / setup. Study `main & final.js` files with relevant scripts for pips & slideshows.

**Link(s) to work**


---

### Day 19: Wednesday, 22nd May, 2019

**Today's Progress**

• Make dynamic privacy, cookies and terms section with CraftCMS and twig syntax. Use `typeset` to style for loop item in `legal section` with appropriate classes.

• Study `continue` statement in JavaScript - terminating execution vs ongoing execution for `addEventListener` and `classList` additions for selected classes for a pip `slideshow`.

• Start Jonas Schmedtman's JS course w/ refresher on `type coercion`, var declaration, data types and operators.

**Link(s) to work**

1. [NakedTV](https://www.nkdtv.com/)
2. [Continue statement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/continue)
3. [JS type coercion](https://www.udemy.com/the-complete-javascript-course/learn/lecture/5869094#questions/7082126)

---

### Day 20: Thursday, 23rd May, 2019

**Today's Progress**

• Analyse small JS slideshow library containing: `querySelectorAll`, `getElementById`, `addEventListener`, `continue` statement, `clearInterval`, `setInterval()`. These functions and tools were used to ex. restart timing and change slides. Study twig's null coalescing operator `??` and whitespace trimming `{{- value -}}`. 

• Look into nesting, linting and framework using Block Element Modifier (BEM). Ex. nest modifiers but not elements, spell out their full classes instead of the `&` symbol. Check out `role` attribute for `accessibility` paired with `ARIA` labels. Analyse `@extends %class` for typesets. 

• Review operator precedence, boolean logic (`ternary, if/else, switch` w/ `case`), data types, ES5 vs ES6 syntax and carried on with Jonas' JS course; completed mini challenge.

**Link(s) to work**

1. [Slideshow JS - private](https://github.com/ten4design/ten4-framework/blob/master/addons/slideshow/final.js)
2. [JS code challenge](https://www.instagram.com/p/Bx0ljjJn8Co/)
3. [Continue](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/continue)

---

### Day 21: Friday, 24th May, 2019

**Today's Progress**

• Look into form creation with JavaScript `createElement('script')`, `innerHTML` & `appendChild`via `HubSpot`.

• Multiple `users` in CraftCMS PRO for website contact requests, permissions and ternary operators in twig using `craft.app.request.getQueryParam( 'contact' )`.

• Make first small form component from `inVision` to codepen to website. Experience `Jupiter` and Saturn (dB) hosting, GitHub staging and temporary "deployment" via pointing to staging environment. 

**Link(s) to work**

1. [Codepen](https://codepen.io/most_mojo/pen/gJeKLK)

---

### Day 22: Saturday, 25th May, 2019

**Today's Progress**

• Continue JS course (Jonas Schmedtmann) - Falsy values: `null, undefined, 0, "", NaN` vs `truthy` values. Equality operators: strict `===` vs `==`, which do `type coercion`.

• Complete short basketball challenge with ES6 `template literals`, `const` declarations and logical operators. 

• Implement weekly learnings to personal site to test mobile responsiveness & new fonts using `em`s. Create linktree account to better share profile content. 

**Link(s) to work**

1. [Codepen](https://codepen.io/most_mojo/pen/pmVOjW?editors=1111)
2. [Personal site](https://mostmojo.github.io/)
3. [Linktree](https://linktr.ee/mostmojo)
4. [Site inspiration](https://konradcodes.github.io/Konrad-Szerszen-Portfolio/)
5. [*PHP Rest API*](https://www.youtube.com/watch?time_continue=1&v=OEWXbpUMODk) - TraversyMedia must watch

---

### Day 23: Sunday, 26th May, 2019

**Today's Progress**

• Fork Jonas-based portfolio page and recap `SVG` icons via icomoon. Use `sprite.svg` file with semantic HTML class `<svg class="x"><use xlink:href="img/sprite.svg#icon-github></use></svg>` and the `fill` property. 

•  Recap `animation` property in CSS for title and subtitle entries. Fix error with `npm install -g node-sass` and use `npm-run-all compile:sass prefix:css compress:css` to rebuild asset pipeline for production. 

• Continue JS course - recap ES5 `function calculateAge( birthYear ) {}`, arguments, parameters and functions within functions to calculate retirement; exercise. 

**Link(s) to work**

1. [Site](https://mostmojo.github.io)
2. [Codepen - JS function](https://codepen.io/most_mojo/pen/YbLBMe)

---

### Day 24: Monday, 27th May, 2019

**Today's Progress**

• Add content to my site, tweak widths, box-shadow, transitions and create link `utility` class.

• Redo tip calculator challenge to instil `data structures` - accessing arrays, objects, functions within functions.

• Continue Jonas' course. `Object literals` vs `new Object()` syntax, CRUD, `this` keyword within methods - i.e. `function() { this.age = 2019 - this.birthYear; }` to extract data from `key:value` pair object. Complete BMI challenge.

**Link(s) to work**

1. [Site](https://mostmojo.github.io/)
2. [Tip Calc](https://twitter.com/most_mojo/status/1132925274520207360)
3. [Gist BMI](https://gist.github.com/mostmojo/6bdd5805d7780f153fb6d3f425bd4b96)

---

### Day 25: Tuesday, 28th May, 2019

**Today's Progress**

• Style form using reusable components made from scratch. Use CSS class `specificity` when styling form element to target label and border. Ex. `.property input[type = text] { ... }`.

• Use `importdb` when cloning CraftCMS site plus SequelPro, and ensure `yarn watch, build:js` is run. Understand category relationships, their URIs and entry filters. Read on `bash aliases`, and `null coalescing operator` => `??`.  

• JS Course: Loops & iterators - `for` and `while`, `continue` / `break` statements and backwards loops using for `(i = john.length -1 ; i >= 0; i--);`

**Link(s) to work**

1. [Bash alias](https://mijingo.com/blog/creating-bash-aliases)
2. [?? operator](https://twig.symfony.com/doc/2.x/templates.html)

---

### Day 26: Wednesday, 29th May, 2019

**Today's Progress**

• Feedback on `position: absolute` vs `display: flex` - research on flexbox, default characteristics i.e. `align-items: stretch;` & `flex-direction: row;` and codepen implementation of twitter card.

• Inline (`<a>, <img> <span>`) vs block (`<p>, <div>, <ul>, <li>`) level elements and how they affect layout from the start in HTML. General rule: when using margins - go for top, right and bottom as we read like that in English.

• Study email forms with `getQuerySelector`, `getElementById('x').value`, `addEventListener('click', () => {});`. 

**Link(s) to work**

1. [Flexbox](https://daveceddia.com/implement-a-design-with-css/)
2. [Codepen Twitter](https://codepen.io/most_mojo/pen/rgZKpQ)

---

### Day 27: Thursday, 30th May, 2019

**Today's Progress**

• Read hubspot docs to integrate form with JavaScript `createElement`, `innerHTML`, `getElementById` and `appendChild` selectors. Use HS-based classes to style sheet accordingly. 

• Study `matrices` in craft and render them in `Twig`. Use `{% include x %}` to define `hashes` with `key:value` pairs using the `with` param for `_partials.twig`. Look into inline styling `background-image: url("{{ image[0].getUrl(passImageTransformHere )}}")` for this occassion only as it applies the image transforms with `getUrl()`. Tip: `.url` would render the image *without* the transforms!  

• Finish first iteration of for-fun personal site using latest Adv. CSS course projects and styling.

**Link(s) to work**

1. [JS: Hubspot form](https://designers.hubspot.com/docs/cos/hubspot-form-markup)
2. [Twig include](https://craftquest.io/articles/passing-data-with-a-twig-include-statement)
3. [Site](https://mostmojo.github.io)

---

### Day 28: Friday, 21st May, 2019

**Today's Progress**

• Look into `#content` attribute for location anchoring on a site. Also, use for onScroll effects with JS functions and CSS animations. 

• How to build & use `macros` in `Twig` and their functionality for images, social links and slider transforms. E.g.  `{% macro macroName(parameter1, parameter2) %}` - similar to JS functions, with `for loops` and `hashes`.

• Try Jonas course final restaurant challenge w/ data structures, objects, logical operators, loops and literals without solution. Tip: in JS we can utilize the `[i]` variable declared in the loop as placeholder for iteration. Use `this.bill = something` or `this.bill[i]` to refer to specific variable/value in an object. 

**Link(s) to work**

1. [Content attribute](https://developer.mozilla.org/en-US/docs/Web/CSS/content)
2. [Git shortcuts](https://ohshitgit.com/)
3. [Macros](https://www.google.com/amp/s/mijingo.com/blog/using-macros-in-twig-and-craft/amp)

---

