👨🏻‍💻 [Previous 100DaysOfCode log](https://twitter.com/most_mojo/status/1085674532982214662)

<p align="center">
  <img width="120" height="120" src="https://res.cloudinary.com/mostmojo/image/upload/v1560979571/psy.gif">
</p>

-----

### Day 1: Sat, 4th May, 2019

**Today's Progress**

• Key CSS grid terms: `container, row, column, area, items, cells, display: grid`.

• Downloaded new Mozilla Firefox and checked out grids in dev tools w/ line numbers.

• Practiced moving grids around on codepen with `grid-row` & `grid-column` syntax.

**Link(s) to work**

1. [Codepen grids](https://codepen.io/most_mojo/pen/RmwKWd)

-----

### Day 2: Sunday, 5th May, 2019

**Today's Progress**

• Continued learning CSS grid - infinite `col` span using -1.

• Name grid lines: ex. `grid-template-rows: [ header-start ] 100px [ header-end box-start ] 200px [ box-end main-start ] 400px [ main-end footer-start ] 100px [ footer-end ];`.

• Functionality of cols using `grid-template-columns: repeat(3, [ col-start ] 1fr [ col-end ]) 200px [ grid-end ]; &rarr; col-start-1 col-end-1, col-start-2 col-end-2`, etc.

**Link(s) to work**

1. [Codepen grids](https://codepen.io/most_mojo/pen/RmwKWd)

-----

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

-----

### Day 4: Tues, 7th May, 2019

**Today's Progress**

• Dissected Craft CMS / PHP Twig site. Familiarized myself with Twig syntax, ternary operators and framework. Content blocks within matrix fields can be selected. For loops with array indices can display images; with transform props! Remember: `{% set variable = entry.title %}` for logic vs `<p>{{ entry.title }}</p>` for display. 

• Looked into yarn builds, compilers, SASS variables, the asset pipeline and began to break down Twig logic. 

• Worked on layout of Nexter. Used `line names` within `grid-column` property in practice to align sections. Ex. `grid-column: col-start 7 / full-end;`

**Link(s) to work**

1. [Nexter project](https://github.com/mostmojo/nexter)
2. [NH - private but it's there!](https://github.com/ten4design/nicholas-hare)

-----

### Day 5: Wednesday, 8th May, 2019

**Today's Progress**

• Twig - base inheritance w/ `{% extends '_base' %}` `{% block content %} {% endblock %}`. Used global handles: `@assetUrl, {{ entry.url }}, {{ url( '/.../ ~ entry.slug' ) }}, {{ siteUrl }}` to display different url scenarios. 

• JS `cloak` library, `% placeholder selectors` in SASS - `@extends` , `itemscope` using schema.org, `vendor` files and Craft CMS globals: `getPrev, orderBy, postDate, {% include x %}`, `paginated` entries and `craft.app.request`. `Invisible` classes  to keep semantic structure: h1 > h2 > h3, etc. Also - `loop.last` & `|raw` filter for escaping in Twig.

• Continued on nexter project - **features** layout with CSS grids within `grid items`. Added svg files with `use xlink:href` and `sprite` files.

**Link(s) to work**

1. [SASS @extends docs](https://sass-lang.com/documentation/at-rules/extend)
2. [Schema](https://schema.org/)

-----

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

-----

### Day 7: Friday, 10th May, 2019

**Today's Progress**

• Looked into JavaScript `(function() document.body.className += ' js')` to grab contents of the body in a document that contain JS and render them into `script` tags.

• Twig logic with additional conditions for displaying contents within a footer of a Craft CMS-based site. Remember: `{% set casting_case = '' %}` syntax for loops - `objects` and `arrays` came handy with navbar segments.

• Created `/casting` section, fields, design layout, entries in Craft for new Studio Ramsay page. Made button component in asset pipepline and ensured responsiveness. First deployment w/ `jupiter` - AWS & docker!

**Link(s) to work**

1. [document.body.className](https://stackoverflow.com/questions/2125993/setting-document-body-classname-as-a-variable)
2. [Studio Ramsay](https://www.studioramsay.com/casting)
3. [Casting commits](https://github.com/ten4design/studio-ramsay/commits?author=mostmojo)

-----

### Day 8: Saturday, 11th May, 2019

**Today's Progress**

• Continued Nexter project. Used auto-fit property on parent grid element with minmax to fit contents of the col-grid according to minimum width and 1fr. Anything < 250px would decreased the cols from 3 to 2 to 1, etc. using auto-fit. `grid-template-columns: repeat(auto-fit, minmax(25rem, 1fr));`

• Used `grid-template-columns: min-content 1fr;` on child grid to create cols based on content and adapt. Remember: `fill` property is used to define colors on `svg` icons.

• Made `%heading` placeholder selector for typography and `@extend` into relevant headings throughout project. 

**Link(s) to work**

1. [Nexter](https://github.com/mostmojo/nexter)

-----

### Day 9: Sunday, 12th May, 2019

**Today's Progress**

• Built a `story` section with `display: grid` and `display: flex` solutions to align content with images.

• Made reusable helper classes similar to `atomic css` for margins.

• Worked with linear gradients to overlay images and further studied `BEM` syntax.

**Link(s) to work**

1. [Nexter](https://github.com/mostmojo/nexter)
2. [Atomic CSS](https://acss.io/)
3. [BEM syntax](https://twitter.com/most_mojo/status/1127570130517544962)

-----

### Day 10: Monday, 13th May, 2019

**Today's Progress**

• Looked into Eric Meyer's Reset CSS stylesheet to reduce browser inconsistencies. Read Twig docs to see how `|length` filter operates.

• Further dive into more complex conditionals in twig to display images with image transforms (Craft CMS), reverse--rows, helper tags for margins, typeset classes to style dynamic content and research `display: inline, block, inline-block`.

• Started the house section of Nexter w/ `<use xlink:href="img/sprite.svg#icon-heart-full"></use>` SVGs, multi-nested classes and grid-items.

**Link(s) to work**

1. [Reset CSS](https://meyerweb.com/eric/tools/css/reset/)
2. [Twig](https://twig.symfony.com/doc/2.x/templates.html#filters)
3. [Nexter](https://github.com/mostmojo/nexter)

-----

### Day 11: Tuesday, 14th May, 2019

**Today's Progress**

• Looked into NkdTV layout, craft setup to identify sections, fields, handles, entry types. Looked into image magick error with yarn dependencies, docker config files and node modules. *Tip:* don't `yarn install`, but `yarn build:js` otherwise it overwrites everything you've pasted from older files! 

• Analysed a nav item variable declaration, for loop with 2 parameters and more complex logic to display relevant nav items with highlighting styles upon selection using ternary operators. *Tip:* remember the mighty `.env` file when configuring the DB!

• Finished home card section on Nexter project using CSS grids and flexbox. Used `transform: translateY(50%);` for positioning and `z-index` with `align-self: end` to place an svg file with grid system.

**Link(s) to work**

1. [NkdTV](https://www.nkdtv.com/)
2. [Nexter](https://github.com/mostmojo/nexter)

-----

### Day 12: Wednesday, 15th May, 2019

**Today's Progress**

• Studied Craft's `category groups`, `field layouts` and relationships using `source` to identify a for loop that renders content to the browser using a 'work role' category, filtered by 'departments'.  

• Learned about the kanban process, component delegation when working in groups, and maintainable code structure.

• Started a gallery section in Nexter with another grid featuring gallery items, `object-fit: cover` property and `display: block` to prevent whitespace created by inline elements that behave like text. 

**Link(s) to work**

1. [Craft categories](https://docs.craftcms.com/v3/categories.html#category-groups)
2. [Nexter](https://github.com/mostmojo/nexter)

-----

### Day 13: Thursday, 16th May, 2019

**Today's Progress**

• Create a new section for client to showcase new `shows`. Ensure all fields and design layout in the CMS was sufficient and had good instructions for client. 

• Relate content by `category groups` to display project status using Craft CMS. Indentation, variable naming and continuity is key. Brief look at `JS polyfills` for IE8 browser knowledge.

• Imitate design & structure from related section and InVision mockup. Got a small taste of `kanban` agile methodology. Made relevant index and entry files in asset pipeline. 

**Link(s) to work**

1. [Nkdtv](https://www.nkdtv.com/)
2. [Kanban](https://www.atlassian.com/agile/kanban)

-----

### Day 14: Friday, 17th May, 2019

**Today's Progress**

• Alter existing homepage to make transparent nav bar.

• Begin for loop for featured shows `.slideshow` using BEM and ensuring the related `Show` section contained `showImage` class to successfully complete query and display related content from entry if asset exists. 

• Use `position: absolute`to place headers and links on slideshow responsively. Get my first short code review - helpful to instill way of thought and good practice 🙂.

**Link(s) to work**

1. [Nkdtv](https://www.nkdtv.com/)
2. [Kanban](https://www.atlassian.com/agile/kanban)

-----

### Day 15: Saturday, 18th May, 2019

**Today's Progress**

• Create gallery section for nexter project with `display: grid`and `template rows/cols` using span.

• Read about `display: inline, display: block, display: inline-block;` properties to use for footer styling. Inline: `<a>, <img>, <strong>` inlines can behave like `blocks`e.g. `<p>, <h1>`with `display: block` property.

• Hamburger menu for navbar using pseudo elements `::before, ::after` and assigning `content: ""` with `transform: translateY(-2rem);`

**Link(s) to work**

1. [Nexter](https://github.com/mostmojo/nexter)
2. [Inline & block](https://medium.com/swlh/understanding-css-display-none-block-inline-and-inline-block-63f6510df93)

-----

### Day 16: Sunday, 19th May, 2019

**Today's Progress**

• Finish nexter project on desktop.

• Add @media queries, change grid layouts to adapt to responsive layout and display on mobile devices with ``$bp-large, $bp-medium` breakpoints. 

• Add @media queries to personal site to test using `@media only screen and (max-width: 900px)`. Look at `max-height, max-width and minmax(min-content, max-content)` properties for adjusting responsive layouts.

**Link(s) to work**

1. [Nexter github](https://github.com/mostmojo/nexter)
2. [Nexter desktop](https://mostmojo.github.io/nexter/)

-----

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

-----

### Day 18: Tuesday, 21st May, 2019

**Today's Progress**

• Ternary operators in twig to select specific classes for a `header--transparent` vs `header--primary` class. E.g. `{{ site_area == '' ? ' header--transparent' : ' header--primary' }}`. Also, intermediate responsive queries for mobile layout including font & image sizing as per different setting. 

• `style="background-image: url( 'image.getUrl( 'imageTransformName' )' )";` for more stretchable images with transforms for better performance, with hidden `img src` & `position: absolute; top: -999;` values present to contain ARIA & accessibility labels. 

• Basic run-through of `bash` scripts that configure and prompt `nginx, docker, CraftCMS, Jupiter & Saturn` deployment / setup. Study `main & final.js` files with relevant scripts for pips & slideshows.

**Link(s) to work**


-----

### Day 19: Wednesday, 22nd May, 2019

**Today's Progress**

• Make dynamic privacy, cookies and terms section with CraftCMS and twig syntax. Use `typeset` to style for loop item in `legal section` with appropriate classes.

• Study `continue` statement in JavaScript - terminating execution vs ongoing execution for `addEventListener` and `classList` additions for selected classes for a pip `slideshow`.

• Start Jonas Schmedtman's JS course w/ refresher on `type coercion`, var declaration, data types and operators.

**Link(s) to work**

1. [NakedTV](https://www.nkdtv.com/)
2. [Continue statement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/continue)
3. [JS type coercion](https://www.udemy.com/the-complete-javascript-course/learn/lecture/5869094#questions/7082126)

-----

### Day 20: Thursday, 23rd May, 2019

**Today's Progress**

• Analyse small JS slideshow library containing: `querySelectorAll`, `getElementById`, `addEventListener`, `continue` statement, `clearInterval`, `setInterval()`. These functions and tools were used to ex. restart timing and change slides. Study twig's null coalescing operator `??` and whitespace trimming `{{- value -}}`. 

• Look into nesting, linting and framework using Block Element Modifier (BEM). Ex. nest modifiers but not elements, spell out their full classes instead of the `&` symbol. Check out `role` attribute for `accessibility` paired with `ARIA` labels. Analyse `@extends %class` for typesets. 

• Review operator precedence, boolean logic (`ternary, if/else, switch` w/ `case`), data types, ES5 vs ES6 syntax and carried on with Jonas' JS course; completed mini challenge.

**Link(s) to work**

1. [Slideshow JS - private](https://github.com/ten4design/ten4-framework/blob/master/addons/slideshow/final.js)
2. [JS code challenge](https://www.instagram.com/p/Bx0ljjJn8Co/)
3. [Continue](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/continue)

-----

### Day 21: Friday, 24th May, 2019

**Today's Progress**

• Look into form creation with JavaScript `createElement('script')`, `innerHTML` & `appendChild`via `HubSpot`.

• Multiple `users` in CraftCMS PRO for website contact requests, permissions and ternary operators in twig using `craft.app.request.getQueryParam( 'contact' )`.

• Make first small form component from `inVision` to codepen to website. Experience `Jupiter` and Saturn (dB) hosting, GitHub staging and temporary "deployment" via pointing to staging environment. 

**Link(s) to work**

1. [Codepen](https://codepen.io/most_mojo/pen/gJeKLK)

-----

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

-----

### Day 23: Sunday, 26th May, 2019

**Today's Progress**

• Fork Jonas-based portfolio page and recap `SVG` icons via icomoon. Use `sprite.svg` file with semantic HTML class `<svg class="x"><use xlink:href="img/sprite.svg#icon-github></use></svg>` and the `fill` property. 

•  Recap `animation` property in CSS for title and subtitle entries. Fix error with `npm install -g node-sass` and use `npm-run-all compile:sass prefix:css compress:css` to rebuild asset pipeline for production. 

• Continue JS course - recap ES5 `function calculateAge( birthYear ) {}`, arguments, parameters and functions within functions to calculate retirement; exercise. 

**Link(s) to work**

1. [Site](https://mostmojo.github.io)
2. [Codepen - JS function](https://codepen.io/most_mojo/pen/YbLBMe)

-----

### Day 24: Monday, 27th May, 2019

**Today's Progress**

• Add content to my site, tweak widths, box-shadow, transitions and create link `utility` class.

• Redo tip calculator challenge to instil `data structures` - accessing arrays, objects, functions within functions.

• Continue Jonas' course. `Object literals` vs `new Object()` syntax, CRUD, `this` keyword within methods - i.e. `function() { this.age = 2019 - this.birthYear; }` to extract data from `key:value` pair object. Complete BMI challenge.

**Link(s) to work**

1. [Site](https://mostmojo.github.io/)
2. [Tip Calc](https://twitter.com/most_mojo/status/1132925274520207360)
3. [Gist BMI](https://gist.github.com/mostmojo/6bdd5805d7780f153fb6d3f425bd4b96)

-----

### Day 25: Tuesday, 28th May, 2019

**Today's Progress**

• Style form using reusable components made from scratch. Use CSS class `specificity` when styling form element to target label and border. Ex. `.property input[type = text] { ... }`.

• Use `importdb` when cloning CraftCMS site plus SequelPro, and ensure `yarn watch, build:js` is run. Understand category relationships, their URIs and entry filters. Read on `bash aliases`, and `null coalescing operator` => `??`.  

• JS Course: Loops & iterators - `for` and `while`, `continue` / `break` statements and backwards loops using for `(i = john.length -1 ; i >= 0; i--);`

**Link(s) to work**

1. [Bash alias](https://mijingo.com/blog/creating-bash-aliases)
2. [?? operator](https://twig.symfony.com/doc/2.x/templates.html)

-----

### Day 26: Wednesday, 29th May, 2019

**Today's Progress**

• Feedback on `position: absolute` vs `display: flex` - research on flexbox, default characteristics i.e. `align-items: stretch;` & `flex-direction: row;` and codepen implementation of twitter card.

• Inline (`<a>, <img> <span>`) vs block (`<p>, <div>, <ul>, <li>`) level elements and how they affect layout from the start in HTML. General rule: when using margins - go for top, right and bottom as we read like that in English.

• Study email forms with `getQuerySelector`, `getElementById('x').value`, `addEventListener('click', () => {});`. 

**Link(s) to work**

1. [Flexbox](https://daveceddia.com/implement-a-design-with-css/)
2. [Codepen Twitter](https://codepen.io/most_mojo/pen/rgZKpQ)

-----

### Day 27: Thursday, 30th May, 2019

**Today's Progress**

• Read hubspot docs to integrate form with JavaScript `createElement`, `innerHTML`, `getElementById` and `appendChild` selectors. Use HS-based classes to style sheet accordingly. 

• Study `matrices` in craft and render them in `Twig`. Use `{% include x %}` to define `hashes` with `key:value` pairs using the `with` param for `_partials.twig`. Look into inline styling `background-image: url("{{ image[0].getUrl(passImageTransformHere )}}")` for this occassion only as it applies the image transforms with `getUrl()`. Tip: `.url` would render the image *without* the transforms!  

• Finish first iteration of for-fun personal site using latest Adv. CSS course projects and styling.

**Link(s) to work**

1. [JS: Hubspot form](https://designers.hubspot.com/docs/cos/hubspot-form-markup)
2. [Twig include](https://craftquest.io/articles/passing-data-with-a-twig-include-statement)
3. [Site](https://mostmojo.github.io)

-----

### Day 28: Friday, 31st May, 2019

**Today's Progress**

• `#content` attribute for location anchoring on site. Use for onScroll effects with JS functions and CSS animations too. 

• Build `macros` in `Twig` and their functionality for images, social links and slider transforms. E.g.  `{% macro macroName(parameter1, parameter2) %}` - similar to JS functions, with `for loops` and `hashes`.

• Jonas course final restaurant challenge w/ data structures, objects, logical operators, loops and literals without solution. Tip: in JS we can utilize the `[i]` variable declared in the loop as a placeholder for iteration. Use `this.bill = something` or `this.bill[i]` to refer to variable/value. 

**Link(s) to work**

1. [Content attribute](https://developer.mozilla.org/en-US/docs/Web/CSS/content)
2. [Git shortcuts](https://ohshitgit.com/)
3. [Macros](https://www.google.com/amp/s/mijingo.com/blog/using-macros-in-twig-and-craft/amp)

-----

### Day 29: Saturday, 1st June, 2019

**Today's Progress**

• Look into operator precedence on MDN docs to understand order that JS reads specific expressions and logical operators. Comes handy when using ex. `this.someArray.length;`.

• Review tip calculator challenge (pt.1) in Jonas' course. Understand use of `this` in JavaScript, the `i` counter variable and its usability.

• Start pt.2 - Apply similar functionality of `obj1` to `obj2` and think of average calculator `function` to apply to both objects.

**Link(s) to work**

1. [Operator precedence](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence)
2. [Tip Calculator pt. 1](https://gist.github.com/mostmojo/b31f62ee92e709cb6a9787698ef21206)

-----

### Day 30: Sunday, 2nd June, 2019

**Today's Progress**

• Complete JS tip calculator challenge. Add reusable `function calcAverage(tips) { ... }` that takes ex. `john.tips` & `mark.tips` argument and can be used multiple times while staying DRY. Declare `var sum = 0` outside the loop so value doesn't reset once function is complete. Then `+=` tip values into the variable `sum` and `/ tips.length` to get average.

• Brief intro to `ES5` vs `ES6` syntax, purpose of comp/transpilers ex. `babel` and pros & cons of knowing both syntaxes. 

• Theory - code execution: `parser` &rarr; abstract `syntax tree` &rarr; conversion to machine code &rarr; code runs. Learn theory on `hoisting` - identify between `function declarations` (don't need to be declared before use) and `variable declarations` (Need to be declared before use). Also, learn about `global execution context` vs `functional execution context`. Ex. if `var age = 23;` is declared in global context, then also identical variable within a function, it'll render as their execution context differs 🤓. 

**Link(s) to work**

1. [Tip Calculator pt. 2](https://gist.github.com/mostmojo/b31f62ee92e709cb6a9787698ef21206)
2. [Hoisting](https://github.com/mostmojo/prod/blob/master/javascript-course/script.js)

-----

### Day 31: Monday, 3rd June, 2019

**Today's Progress**

• Reuseable `typeset` extensions w/ `.h-1, %heading-style-4 { ...; }` later `@extend` elsewhere. Study `getPrev()` & `getNext()` Craft methods, and the `{%- whitespace controller -%}`. Plus, `|trim('https://', 'left')` twig filter for trimming content.

• Use `<figure>` & `<figcaption>` semantic HTML tags for img + video content and look at video tag with `muted loop autoplay` attributes. Also, the `<blockquote>` accompanied by `<cite>` to be used with `<figure>` for quotes.

• `flex-wrap: wrap` vs `nowrap;` in flexbox, `word-break: break;` properties; the `rel="noopener"` attribute in `<a>` tags to prevent JS in site via global `.window` opening it for *a)* general performance benefits *b)* security benefits - malicious redirect prevention.

• Playground with `display: flex` in codepen to practice `flex items`, `columns`, `directions` and `wrap`. Finish JS Theory on local and global `scope`, `scoping chain` and `context`.

**Link(s) to work**

1. [figure | MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/figure)
2. [blockquote | MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/blockquote)
3. [noopener](https://developers.google.com/web/tools/lighthouse/audits/noopener)
4. [|trim](https://twig.symfony.com/doc/2.x/filters/trim.html)
5. [codepen](https://codepen.io/most_mojo/pen/mYoPvv)
6. [scope](https://github.com/mostmojo/prod/blob/master/javascript-course/script.js)

-----

### Day 32: Tuesday, 4th June, 2019

**Today's Progress**

• Trace back an error with `twitterUrl()` not recognized. Suggested: `importdb` in terminal or backup db from craft. Then drag/drop into `SequelPro` and distinguish between local testing and staging environments. 

• Study relational `field types` in Twig which work the same as `sections` & `channels` when queried.  ex. `{% for project in craft.entries('projects') %}` vs reverse relations using `.relatedTo()` - this avoids data duplication. ex. `{% set relatedProjects = craft.entries.section('projects').relatedTo(entry) %}` where `entry` is the *service* entry (the one we want to relate to). 

• Create a landing page for practice from `sketch`, using `flexbox`. Tip: use `flex: 1;` for spacing, and keep elements in divs that need to be flexed. Can also change `flex-direction: column;` for mobile responsiveness. `@media screen and (max-width: 1024px) {...}`. Finish by looking into twitter card meta data with image dimensions and relevant `og:titles`.

• **Tip:** Add linear gradient to background, then `clip` the text and make the `fill` transparent to get a nice `bg gradient` inside the font - pure gold. `.class { background: linear-gradient(to right, #494964, #6f6f89); -webkit-background-clip: text; -webkit-text-fill-color: transparent;
-webkit-background-clip: text;`

**Link(s) to work**

1. [Relations](https://straightupcraft.com/articles/introduction-to-relations-and-reverse-relations-in-craft-cms-with-examples)
2. [laptop-ui site](https://mostmojo.github.io/laptop-ui/)
3. [Twitter cards](https://twitter.com/most_mojo/status/1136019113942376448)

-----

### Day 33: Wednesday, 5th June, 2019

**Today's Progress**

• Create a url path using function `url('contact', { contact: entry.project[0].firstName })` to return `site.com/contact?contact=bob` - domain, path, query string hash

• Study `{% include x %}` components and what `key: value` pairs are passed and how they are used in `Twig`. Research `flex-shrink: 0;` for when flex items exceed container limit. 

• Make small tip calculator with `gradient`, `clip`, `webkit-fill`, the `transform: translateY` property and `calcTip()` JS function paired with `calcAverage()` (CRUD) for two fictional objects. 

**Link(s) to work**

1. [URL | MDN](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_URL)
2. [flex-shrink](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-shrink)
3. [calculator](https://codepen.io/most_mojo/pen/QRRdvw)

-----

### Day 34: Thursday, 6th June, 2019

**Today's Progress**

• Built tip calculator with HTML, CSS & JS that rendered `calcTip()` and `calcAverage()` functions to the console in the DOM. Ensured syntactically to complete the challenge in both `ES5` and `ES6` declaring `key:values` with `this` keyword where appropriate.

• Study `functional` scope vs `class/variable` scope and how functions are read and hoisted depending on where they are invoked.

• Use `animate.css` library to create `zoomIn` & `zoomOut`-type effects in CSS for specific elements. Ensure semantic HTML tags such as `<section>` and `<figure>` were integrated. Once complete, rendered final restaurant bills in the `DOM`. 

**Link(s) to work**

1. [Calculator](https://github.com/mostmojo/tip-calculator)
2. [Variable scope](https://www.digitalocean.com/community/tutorials/understanding-variables-scope-hoisting-in-javascript)
3. [Animate.css](https://daneden.github.io/animate.css/)

-----

### Day 35: Friday, 7th June, 2019

**Today's Progress**

• Refactored folder architecture of calculator project with `@import url(folder/file`) in `style.css` and added comments.

• Built bear cartoon from scratch using pure HTML `divs` and `css`. Utilize the power of subtleties like `position: absolute` and `border-radius: 100%;`. The use of `border-bottom: 2px solid #000;` property combined with `border-radius: 0% 0% 100% 100%;` to create half-moon shaped elements for a `mouth` was fun to figure out. Use `z-index` to bring elements on top of others. 

• Read blog on `accessibility` and learn not to use `a:focus { outline: none; }` as users that navigate using keyboard-only wouldn't able to get there. Best practice: `a:focus { background-color: #000000; color: #FFFFFF; }` - alternate 'hidden' styles.

**Link(s) to work**

1. [Calculator](https://github.com/mostmojo/tip-calculator)
2. [Bear](https://mostmojo.github.io/bear-ui/)
3. [Accessibility outline](https://medium.com/@matuzo/writing-css-with-accessibility-in-mind-8514a0007939)

-----

### Day 36: Saturday, 8th June, 2019

**Today's Progress**

• Read a detailed explanation of how to creating pure `CSS` images. Distinguishing components, divs, shapes and how the overall layout of each element looks like. 

• Start build for DOM pig game. Implement `Math.floor(Math.random() * 6) + 1` global function to generate random decimal, round it down to nearest whole and ensure it fulfils 6-number dice roll. 

• Study `getters` vs `setters` with `document.querySelector("#current-" + activePlayer).textContent = dice;` example. Use `concatenation` with JS `type coercion` to set the value of a dice roll to a specific `id` in HTML. If applying HTML tags, use `.innerHTML` and tags in brackets. Ex. `document.querySelector("#current-" + activePlayer).innerHTML = "<em>" + dice + "</em>"`. To hide a CSS class w/ JS: `document.querySelector(".dice").style.display = "none";` (Method, property, value).

**Tip**: 1) Shortcut to open console: `cmd + alt + i` 2) this variable is only assigned a value when object calls a method.

**Link(s) to work**

1. [Pure CSS images](https://medium.com/coding-artist/a-beginners-guide-to-pure-css-images-ef9a5d069dd2)
2. [Pig game](https://github.com/mostmojo/prod/blob/master/javascript-course/DOM-pig-game/app.js)

-----

### Day 37: Sunday, 9th June, 2019

**Today's Progress**

• Revise `querySelectors` by creating fun example with `getter` vs `setter`. Use setter with declared variable to change content in HTML with `textContent`. Set italics `<em>` with `.innnerHTML`.

• Set `.addEventListener` with two params: `(click, function() { // do something });` to change img `src` of dice roll to `diceDOM.src = "dice-" + dice + ".png";` and concatenate the class with variable value and suffix.

• Use `.getElementById` to grab scores and change `textContent` to 0. Ex. `document.getElementById("scores").textContent = "0";`. **Remember:** `callback functions` only work when the function/method is called. In `e`.handlers they can also be `anonymous` and belong to the `addEventListener` function as the 2nd parameter - only in that scope.

**Link(s) to work**

1. [querySelector](https://www.instagram.com/p/ByffDbhn3dW/)
2. [byId | img src](https://github.com/mostmojo/prod/blob/master/javascript-course/DOM-pig-game/app.js)

-----

### Day 38: Monday, 10th June, 2019

**Today's Progress**

• Create koala component with several divs from scratch. Use `:root` to declare variables and use them with `background: var(--green);`

• Use `linear-gradient` with `bg-clip` and `text-fill-color: transparent` for modern text styling. Make triangle for koala hair with `clip-path: polygon(50% 0%, 0% 100%, 100% 100%);`. Build `@keyframes drop` element with states `0-50-100%` and use the `animation: text 1.625s ease 1.5s;` property to render the animation. 

• JS course: Add dice roll to `roundScore`, add ternary: `activePlayer === 0 ? activePlayer = 1 : activePlayer = 0;` to switch players and reset `roundScore = 0` both in DOM and HTML. Use `.classList.toggle("active")` to toggle the `classList` between the class `player-0-panel` and `player-1-panel` and hide dice img with .`style.display = "none".` **Note:** it's important to remember the DOM and HTML. Get JS code to do things in both, as the user will see the interface, not the console. 

**Link(s) to work**

1. [koala](https://mostmojo.github.io/koala-ui)
2. [clippy](https://bennettfeely.com/clippy/)
3. [DOM game](https://github.com/mostmojo/prod/blob/master/javascript-course/DOM-pig-game/app.js)

-----

### Day 39: Tuesday, 11th June, 2019

**Today's Progress**

• Make elephant ui component from scratch using CSS. Use `animation-timing-function: cubic-bezier(0.02, 0.01, 0.21, 1);` to create spiralling animation effect. Use `transform: translate(34px, 0)` to move animation blocks on X & Y axis. 

• Read on delayed effects of `cubic bezier` and how to make `infinite` loops using `animation` property. Deep analysis of dice game to understand building blocks of `('.btn-click').addEventListener('click', function() {...})` and relationship between HTML and JS classes. Also, when to reset scores of game both in `DOM` and user interface with use of `classList.toggle('class)`.

• Continue DOM game and add current score to global score w/ `scores[activePlayer] += roundScore`, update UI w/ `textContent` and check if player won the game then add "Winner!", remove dice with `.style.display = "none"` and add winner class with `.classList.add/remove`. Also, create reusable `function nextPlayer()` to stay DRY. 

**Link(s) to work**

1. [Elephant](https://mostmojo.github.io/elephant-ui)
2. [Cubic bezier](https://github.com/mostmojo/elephant-ui/blob/master/components/keyframes.css)
3. [Cubic bez keyframes](https://tobiasahlin.com/blog/curved-path-animations-in-css/)
4. [Dice analysis](https://gist.github.com/mostmojo/fa3e05fa9cde3532ce74f80aebe6cefa)
5. [DOM game](https://github.com/mostmojo/prod/blob/master/javascript-course/DOM-pig-game/app.js)

-----

### Day 40: Wednesday, 12th June, 2019

**Today's Progress**

• Read on svg use, ex. `<button class="btn-new"><svg class="x"><use xlink:href="sprite.svg#icon-circle-with-plus"></use></svg>New game</button>` and how to use icomoon icons with a `sprite.svg file` including `fill: red` props for styling.

• Finish iteration of dice game. Refactor to stay `"DRY"` and create resuable functions `init()` & `nextPlayer()`. Add `state` variable `gamePlayer = true/false` to reset when winner is declared or game hasn't started. Use `document.querySelector(".player-0-panel").classList.remove/add("active");` in reset to ensure red dot is in the right player panel. Also, add idle function `.addEventListener("click", init);` initialized only on dice roll.

• Declare global `var lastDice` to save instance of `var dice`, containing `Math.floor(Math.random() * 6) + 1);` and create condition `if (dice === 6 && lastDice === 6)` then set memory & DOM `scores` to 0 and call `nextPlayer()` 🎲. Ensure `lastDice` is global or else data will be lost if declared in functional scope, once function ends.  

**Link(s) to work**

1. [svg|use](https://css-tricks.com/svg-use-with-external-reference-take-2/)
2. [Dice game code](https://github.com/mostmojo/prod/blob/master/javascript-course/DOM-pig-game/app.js)
3. [DOM game live](https://mostmojo.github.io/dice-roll/)

-----

### Day 41: Thursday, 13th June, 2019

**Today's Progress**

• JavaScript, dice rolling & accessing input data! 🙌🏼 Create `input fields` and grab data using `querySelector(".class").value` prop to populate different scores for the game chosen by user.

• Implement two dice imgs and create slightly more complex conditions for fun. Ensure to hide/show both img vars and include both in conditions like ` if (dice1 !== 1 && dice2 !== 1);` & `document.getElementById("dice-1").style.display = "block/none";`

• Start `treehouse` Fullstack JS route, take skills test and start challenges. Review - script tags, `document.write`, mongoDB terms, 1-to-many relations and peek through phaser.js gaming library. **Tip:** `git reset HEAD / git reset --hard` to undo in git! 

**Link(s) to work**

1. [Dice game code](https://github.com/mostmojo/prod/blob/master/javascript-course/DOM-pig-game/app.js)
2. [DOM game live](https://mostmojo.github.io/dice-roll/)
3. [phaser.js](https://github.com/photonstorm/phaser)
4. [To read: git rebase](https://www.atlassian.com/git/tutorials/rewriting-history/git-rebase)

-----

### Day 42: Friday, 14th June, 2019

**Today's Progress**

• Primitives (`null, undefined, boolean, number, string`) vs `Constructors`, their `instances` and the `prototype` chain. The way that `OOP` works, JS interactions and objects. 

• Create constructor objects `Person` and `Pokemon` with related `instances`: John, Mark || Pikachu, Slowbro to experiment with shared `prototype` function `calculateAge()` and `calculateDamage()`. This helped instil understanding of `inheritance`, the parent `object Object` properties ex. `toString()`, `hasOwnProperty()`, etc and **Prototype chain**.

• Use chrome dev tools to log instances and explore showcasing `Person prototype properties` (`__proto__:`) vs `object Object properties`

**Link(s) to work**

1. [Prototypes](https://github.com/mostmojo/prod/blob/master/javascript-course/advanced-js/script.js)
2. [Prototype Chain](https://github.com/mostmojo/prod/blob/master/javascript-course/advanced-js/notes.md)

-----

### Day 43: Saturday, 15th June, 2019

**Today's Progress**

• Explore order of var declarations, `mutations`, passing `primitives` into functions to create a copy. Passing references of objects and mutating their values.

• Make example of `callback function` with for loop, using `.push` to put values of a function within a function into an array var. Ex. `arrResult.push(fn(arr[i]));`

• Build callback function to calculate max heart rate using 1) a generic function w/ a loop over an input array function `arrayCalc(arr, fn) { ... }`, give it a `fn` as input to calculate something based on each element of the array. `Ex. var rates = arrayCalc(ages, maxHeartRate)`, where `maxHeartRate` returns `Math.round(206.9 - (0.67 * element));` only if `ages are >= 18` and is also only called within the loop. Hence, callback successful 🤓. 

**Link(s) to work**

1. [Primitives & Objects](https://github.com/mostmojo/prod/blob/master/javascript-course/advanced-js/script.js)

-----

### Day 44: Sunday, 16th June, 2019

**Today's Progress**

• Simple refresher on debugging via Treehouse course. Debug a few errors using the console. 

• Study functions that return functions, w/ shorthand syntax, ex. `interviewQuestion('teacher')('Mark');` Immediately invoked function expressions (`IIFE`) - w/ `(function () {...})()` to trick parser that it's an expression and not a declaration. In this case, we create a `private` scope. 

• Make `closure` function to understand the scope and memory storage. Inner `fn` always has access to vars & params of its outer function, even after outer `fn` has returned, so we can invoke a `fn` with all params.

**Link(s) to work**

1. [IIFE](https://github.com/mostmojo/prod/blob/master/javascript-course/advanced-js/script.js)

-----

### Day 45: Monday, 17th June, 2019

**Today's Progress**

• Make question-based closure functions by wrapping the whole function in an `IIFE (function() {...})();`, thus make its scope private. That way if someone else were to use it, and he/she had a var called Question or n, it would not interfere.

• Use `Question.prototype.displayQuestion = function() { .. }` to set object's `this props` to `new` instance of `Question`.  Use `parseInt` to convert ex. `"2"` to integer, not string &rarr; `2`. Finally, use `callbacks` within functions to call other functions to `keepScores`.

• Start plan for budgety app. Make notes on `modules` regarding: `UI`, `Data` and `Controller`.

**Link(s) to work**

1. [Closures](https://github.com/mostmojo/prod/blob/master/javascript-course/advanced-js/script.js)
2. [Modules](https://github.com/mostmojo/budgety/blob/master/notes.md)
-----

### Day 46: Tuesday, 18th June, 2019

**Today's Progress**

• Read on `private` vs `publicly` accessible closures and how the `return` values to a `k:v` become a simple object, and thus can be accessed outside of the function scope, stil within the `(var someName = function()...)();` wrapper as it's immediately invoked at the end, hence the function is not assigned to the variable, but its returning value is. Magic! 🧙‍♂️

• Create global `appController` module w/ params `(function(budgetCtrl, UICtrl) {})(budgetController, UIController)` to obtain access to `budgetController` and `UIController` modules. Use `document.addEventListener('keypress', function(event) {..}` to call `ctrlAddItem()` once 'Enter' key is hit. Also, create more scalable code in the `UIController` to add vars (`DOMStrings`) to classes and `return` them so they're accessible in `appController.` - Closures are the fundamentals of React/Vue and modular code 🤯🚀

• Make `appController.init()` function to start app outside modular scope. Brief look at `every` and `Promise` in JS to lead way into more `async`-based ES6 syntax, `.fetch`, `JSON.stringify`, `state` manipulation and `AJAX`. Finish off with read on web assembly - `binary format`, `compilation speeds` and high level prog. language benefits. 

**Link(s) to work**

1. [Closures](https://lazamar.github.io/closures-private-variables-and-methods-in-javascript/)
2. [Budgety modules](https://github.com/mostmojo/budgety/blob/master/app.js)
3. [Promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/all)
4. [Every](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/all)
5. [Web assembly](https://webassembly.org/)

-----

### Day 47: Wednesday, 19th June, 2019

**Today's Progress**

• Make `data` object of objects to hold expenses and incomes of app. Use `ID = data.allItems[type][data.allItems[type].length - 1].id + 1;` to add incoming data to the end of the array and assign it an id. 

• Create an `addItems()` public function to push new items into the UIController using `data.allItems[type].push(newItem);`. Use `querySelector` to grab elements, and set template html to them using `''` then `.replace` dummy values with dynamic values and `insertAdjacentHTML` and keyword `beforeend` to the UI.

• Use the `Array.prototype.slice.call(fields);` which is the global constructor `Object` to array-ify the user input values, and then set their current.value to `""` to reset the field. By setting `fieldsArr[0].focus()` we return back to the wanted element.

**Link(s) to work**

1. [call](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/call)
2. [focus](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/focus)
3. [preview site](https://mostmojo.github.io/budgety/)

-----

### Day 48: Thursday, 20th June, 2019

**Today's Progress**

• Extract values from data object w/ `data.budget = data.totals.inc - data.totals.exp;` object syntax to create `calculateBudget` function for `budgetController` module. Also, micro-modularized function ex. `getBudget()` that only retrieved specific data. Simple, reusable functions. 

• Create `displayBudget()` function to display `calculateBudget` from `budgetController` module to the `UIController` module. Ex. `document.querySelector(DOMStrings.budgetLabel).textContent = obj.budget;` and due to `obj param` being linked via `UICtrl.displayBudget(budget)` and power of closures, all 3 modules are linked with the global `appController`.

• Use event delegation for event bubbling, the big `itemID = (event.target.parentNode.parentNode.parentNode.parentNode.id);` to access elements within the DOM tree **(DOM Traversing)**. Use global `event.target` to get the target. Then isolate values into separate variables using `.split()` method and prepare for deletion with `.map()` and `splice()` at `indexOf()` a specific array 👽. 

**Link(s) to work**

1. [preview site](https://mostmojo.github.io/budgety/)
2. [budget](https://github.com/mostmojo/budgety/blob/master/app.js)
3. [split](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/split)
4. [target](https://developer.mozilla.org/en-US/docs/Web/API/Event/target)
5. [parentNode](https://developer.mozilla.org/en-US/docs/Web/API/Node/parentNode)
6. [splice](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice)
7. [map](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)

-----

### Day 49: Friday, 21st June, 2019

**Today's Progress**

• Major app functionality works! 🚀 - Learn how to connect field inputs to numbers using `parseInt(splitID[1]);` wrapper. Also, accessing `parentNodes` and `childNodes` to manipulate & `remove` data in the DOM. Ex. `document.getElementById('income').parentNode
    .removeChild(document.getElementById('income'));`. 

• Build `Expense.prototype.calcPercentage = function(totalIncome) { ... }` & `Expense.prototype.getPercentage = function() { ... }` in the `parent Constructor` so enable functions to be accessed by `expense instances`. In budgetController: `data.allItems.exp.forEach(function(x) { x.calculatePercentage(); }`.

• Use `forEach()` function for `nodeLists` instead of arrays. (Where all HTML elements are stored in the DOM as `nodes`). This way, a set up for the percentages is set in the `UIController` and displayed to the browser. 

**Link(s) to work**

1. [preview site](https://mostmojo.github.io/budgety/)
2. [DOM Manipulation](https://blog.garstasio.com/you-dont-need-jquery/dom-manipulation/)
3. [NodeLists](https://developer.mozilla.org/en-US/docs/Web/API/NodeList)
4. [YDKJS &orarr; ](https://github.com/getify/You-Dont-Know-JS)

-----

### Day 50: Saturday, 22nd June, 2019

**Today's Progress**

• Focus on the tiny details 🤗 - **App done!** - The decimal display of the budget app elements. Use `Math.abs()` to get the absolute value of a number. Set the decimal values of the number to two with the **Number prototype** `toFixed(2)` ex. `1,200.00`.

• Divide numbers into substrings using `substr()`, use array data structures to capture integers and decimals with `.length` and set right commas ex. `int = int.substr(0, int.length - 3) + ',' + int.substr(int.length - 3, 3);` to output `23,500.00`.

• Use `new Date()` object constructor with `var month = getMonth // 5` (also zero- based) & `getFullYear` to display it on app header. As these functions are zero-based, create a `months` array `= ['Jan', 'Feb', 'Mar'...]` and set the value as `months[month]` to get **June**. Use `document.querySelector(DOMStrings.inputBtn).classList.toggle('red');` for better UX to enable all the fields to change color on toggle, so users can know that red = expense and green = income.


**Link(s) to work**

1. [preview site](https://mostmojo.github.io/budgety/)
2. [Math.abs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/abs)
3. [toFixed](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toFixed)
4. [Substring](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/substring)

-----

### Day 51: Sunday, 23rd June, 2019

**Today's Progress**

• Continue with Jonas course into ES6! Refresher on variable declarations in ES6 (`var`) vs ES6 (`let & const`). 

• Revise `var` variable's functional scope vs `let/const` block scope by running tests into the console. Also look at possibilities of reassignment, overriding and immutability (const). `Global` assignement vs `functional scope` using `var` and `let` would render different results when using a for loop.

• Look at `Blocks` and `IIFEs`. To create private scope variables in ES5 ex. `(function() { var c = 3; })();` the `()` wrapper can simply be transcribed into curly braces - `{ const c = 3; }`. 


**Link(s) to work**

1. [ES6 notes](https://github.com/mostmojo/prod/blob/master/javascript-course/ES6/script.js)

-----

### Day 52: Monday, 24th June, 2019

**Today's Progress**

• Refresher on `template literal` syntax with `${age}`. Run tests in the console to check values in an array with `startsWith`, `endsWith`, `includes` & `.repeat`.

• Arrow function syntax - single vs multiple lines w/ shortcuts excluding `{}`, `returns` and `()` on one liners. Ex. `let age = years.map(year => 2019 - year);`. Also look through functions with eventListeners in ES5 vs ES6 and determine lexical and non-lexical scope. Ex. determine `var self = this` or `.bind(this)` to declare the instance of that variable. ES6, `lexical scope` refers this to the code containing the arrow function. 👽

• `Destructuring` in ES6. Ex. `const [name, age] = ['Joe', 26];` and reassigning destructured objects `const {fName: a, lName: b}` which would still render same results. Learn about `Array.from(boxes).forEach(box => box.style.backgroundColor = 'dodgerblue');` to (**from**) transform `nodeList` into array w/o using `Array.prototype.slice.call(boxes);`.

**Link(s) to work**

1. [ES6 notes](https://github.com/mostmojo/prod/blob/master/javascript-course/ES6/script.js)
2. [Notes](https://github.com/mostmojo/prod/blob/master/javascript-course/ES6/notes.md)

-----

### Day 53: Tuesday, 25th June, 2019

**Today's Progress**

• Test different ES5 vs ES6 methods of using `continue` & `break` with `for...of` and `includes('blue')` to change content of element if condition is true. Use `find()` & `findIndex()` to display value in an array or index.

• Look into similar method as `call()` &rarr; `apply()` that contains array as arguments. Ex. `addFourAgesTogether.apply(null, ages);` Assigning `this` to `null` as not needed. Look into `spread` operators to combine arrays with dot notation. Ex. `addFourAgesTogether(...ages);` or fuse two arrays together ex. `const famFuse = [famOne, ...famTwo];`

• NodeList to array  conversion using ES6's `Array.from(xs).forEach(x => x.style.color = 'red');`vs ES5's longer `Array.prototype.slice.call(args);`. Use `REST params` to collect all remaining elements into an array vs `Spread` - which allows iterables to be expanded into single elements or args vs `Default params` which can have default values set ex. `function newGuy(fName, lName = 'Jackson', age) {...}`. 

• `Hash maps` - (ES6) - use instead of objects to `x.set(key, value);` that can later be retrieved using `x.get(key)`, use `.size` to get length and check logic using `.has()`, `.delete()`, `.clear()`. Ability to loop over w/ `[key, value] of x.entries()`. 

**Link(s) to work**

1. [ES6 notes](https://github.com/mostmojo/prod/blob/master/javascript-course/ES6/script.js)
2. [for...of](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of)
3. [find](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find)
4. [findIndex](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/findIndex)
5. [apply](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/apply)
6. [spread](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax)
7. [Map()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map#Syntax)

-----

### Day 54: Wednesday, 26th June, 2019

**Today's Progress**

• Build super `class Person` with sub `class Athlete` in ES6, ft. `constructor` and understand concept of `Object.create()` &rarr; `Athlete.prototype = Object.create(Person.prototype);` to make the link between the prototype chain in ES5 behind the scenes. Concept of `call(this, x, y, z)` to point to `new` instance.

• Analyze the `super` method in ES6, which fetches all assigned params from parent class, into the sub class, allowing instance ex. `const jimAthleteES6 = new AthleteES6('Jim', 1993, 'swimmer', 3, 10 );` to all functions and props from the prototype chain.

• Do JS challenge w/ Parks and Trees. Use super and sub classes with `hash map` function, `default params` and implement `reduce()` function to calculate the sum of an array argument. Ex. `const sum = array.reduce((prev, current, index) => prev + current, 0);`. 

• Re-read `destructuring` to understand breakdown of arguments. Ex. `const { first, last } = person;` - to pick out props from a `person` object and make a variable out of it 'automatically' rather than have to: `const first = person.first;`. Comes handy with deeply nested properties/values in larger JSON objects derived from APIs.


**Link(s) to work**

1. [Classes](https://github.com/mostmojo/prod/blob/master/javascript-course/ES6/script.js)
2. [Challenge](https://github.com/mostmojo/prod/blob/master/javascript-course/ES6/script.js#L535)
3. [Reduce](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce)
4. [Destructuring](https://wesbos.com/destructuring-objects/)

-----

### Day 55: Thursday, 27th June, 2019

**Today's Progress**

• `Synchronous` vs `Asynchronous` JavaScript with `setTimeout( () => { ... }, 1000, xParam)` examples to determine the difference between functional `callbacks`, the `callback hell` and reason for `promises`. Study the `global execution context` to understand `event loops` that act as middle man between `Web APIs`, `Message Queue`, `Execution Stack` and `Console`. 

• Deep dive into `promises` to understand `state`: **PENDING &rarr; (EVENT HAPPENS) &rarr; SETTLED/RESOLVED - FULFILLED || REJECTED**. Promises are *produced* and then callbacks can *fulfill* or *reject* data. Promises have `resolve` and `reject` **callback executors**  where `resolve` holds the values of everything that is retrieved from an API for example. `[1, 2, 3]`.

• **Consuming** promises. Any values from the above resolve method are stored in the parameter after `.then` and can be logged, returned, etc. Look into `async & await` to aid in promise consumption. Also, look into `.catch()` method for error handling.

**Link(s) to work**

1. [promise](https://javebratt.com/wtf-promise/)
2. [notes](https://github.com/mostmojo/prod/blob/master/javascript-course/asynchronous-js/asynchronous.html)

-----

### Day 56: Friday, 28th June, 2019

**Today's Progress**

• Make asynchronous network requests using `.fetch()` method on MetaWeather API. To bypass proxy, found cors-anywhere prefix, so didn't have to disable any security feaures in google chrome. 

• On `body: Readable Stream` noticed `.then` needed to consume the data but first `return result.json()` - to convert JSON to JavaScript, readable by browser. `.then(data => {... manipulate data here ...}` and finally `.catch` any errors.

• Repeat the same with `async/await`. Since, `async func` always returns a `promise`, the data returned is the `resolved` value of the promise, accessible using the `then` method.

**Link(s) to work**

1. [notes](https://github.com/mostmojo/prod/blob/master/javascript-course/asynchronous-js/asynchronous.html)
2. [metaweather](https://www.metaweather.com/api/)
3. [CORS-anywhere](https://cors-anywhere.herokuapp.com)

-----

### Day 57: Saturday, 29th June, 2019

**Today's Progress**

• Refresher on CLI terminal commands. `Install npm`, nodeJS, `webpacker` and `live-dev server`. `Npm init package.json files` with dev dependencies, and node modules for `bundler.js` file.

• Set up webpack `config file` after npm install webpack with `path = require('path'); module.exports` to point exports to `dir__name` for `entry` and `output`. 

•  `npm install webpack-cli --save-dev` for command line interface for webpack as dev dependency, along with `live dev server` config to reload in real time for quicker work flow. 

**Link(s) to work**

1. [Setup notes](https://github.com/mostmojo/forkify/blob/master/src/notes.md)

-----

### Day 58: Sunday, 30th June, 2019

**Today's Progress**

• Install webpack, dev-server, html-webpack-plugins.

• `npm install babel-core babel-preset-env babel-loader --save dev`

• `npm install babel-polyfill --save` and run into an error which took all day (still not solved!). When I run `npm run dev`, error: `ERROR in multi @babel-polyfill ./src/js/index.js. Module not found: Error: Can't resolve '@babel-polyfill' in '/Users/jacobpapageorgiou/Desktop/Projects/forkify' @ multi @babel-polyfill ./src/js/index.js main[0]
Child html-webpack-plugin for "index.html":`.

**Link(s) to work**

1. [Setup notes](https://github.com/mostmojo/forkify/blob/master/src/notes.md)

-----

### Day 59: Monday, 1st July, 2019

**Today's Progress**

• Fix nasty `babel polyfill` bug by reinstalling all npm packages from scratch, checking typos and adding most recent updates to `node modules`. Ensure that `modules`, `package.json` files, `compilers` and `webpack CLIs` were installed and targeted properly in `bash` & `nodeJS` syntax.

• Create files to compliment `MVC` model architecture for forkify project. Have `base.js` contain object with `querySelectors`, use `food2fork API` to grab search queries with `axios` for better error handling rather than `.fetch()` as the `model`. Catch `async promise` using `await axios` query string, `catch()` & `alert` any errors.

• Build search model constructor with query params to fetch `this.results`. Create control Search function to be called on `submit event` that - gets a query from view, makes new search object and adds it to state, fetches results from API request and renders results to console. Getting used to the file `import/exports` will take some time! 

**Link(s) to work**

1. [Notes](https://github.com/mostmojo/forkify/blob/master/src/notes.md)
2. [State](http://jsclass.jcoglan.com/state.html)

-----

### Day 60: Tuesday, 2nd July, 2019

**Today's Progress**

• Create function to renderResults containing renderRecipe &rarr; `recipes.forEach(renderRecipe);` where function contains markup inserted with `insertAdjacentHTML`.

• `limitRecipeTitle()` function using modern `split`, `default params`, `reduce`, `join` and `push` methods to iterate through a string, split it if it's over 17 characters and push it into a `newTitle` array and then render to UI, to have better UI/UX when fetching recipe titles. Lastly, look into loader for when waiting for the fetch. `<svg><use></use></svg>` method with markup and `insertAdjacentHTML` in `base.js`

• Create for-fun spinner to generate a random winner. Pull `jquery` from codepen first try and set it to render results & use `confetti` effect for winner 🎉 `[Math.floor(Math.random()]` - magic.

**Link(s) to work**

1. [Notes](https://github.com/mostmojo/forkify/blob/master/src/notes.md)
2. [InsertAdjacentHTML](https://developer.mozilla.org/en-US/docs/Web/API/Element/insertAdjacentHTML)
3. [Spinner](https://mostmojo.github.io/spinner/)

-----

### Day 61: Wednesday, 3rd July, 2019

**Today's Progress**

• Grab svg of loader image, add `animation: rotate 1.5s infinite linear;` which responds to 2 states of `@keyframes rotate { 0% { transform: rotate (0); } 100% { transform: rotate (360deg)l }`. Create ` export const renderLoader` function with appropriate styling `<svg><use href="..."></use></svg>` and `insertAdjacentHTML('afterbegin', loader)` and import into controller with `querySelected` class as argument. Make another clearLoader function to removeChild/loader class after the API data is fetched.

• **Pagination**: Create `renderResults()` with `start` and `end` consts, new array using `slice` method to get recipes, `renderButtons` to have pages, `next/prev` buttons with logical operators to render according to condition. `createButton` - to render html with button / ternary operators to determine the type and page number. 

• Explore `e.target.closest` method to target closest element to click event. Use `Math.ceil()` method to round up numbers when using pagination. 

• Make simple card in codepen to practice display flex, layout, positioning and linear gradients.

• Make reusable card component with basic `ReactJS` 'architecture' containing a `function Person(props)`, its dynamically inserted `props.name`, etc inside a `return( ... )`; a `var app` containing the instances of the new card components wrapped in `JSX syntax` and all sent to `ReactDOM.render(app, document.querySelector('#app'));` to ship all components to the div with the id `app` in the HTML. Ex. `<div id="app"></div>`

**Link(s) to work**

1. [Notes](https://github.com/mostmojo/forkify/blob/master/src/notes.md)
2. [Slice](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice)
3. [Transform origin](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-origin)
4. [Codepen card](https://codepen.io/most_mojo/pen/LKrPNQ)
5. [React card](https://codepen.io/most_mojo/pen/xozajV)

-----

### Day 62: Thursday, 4th July, 2019

**Today's Progress**

• Create new Recipe class with constructor parameter `id` - that way we can have lots of id instances. In same scope of Recipe class, make asynchronous getRecipe function, using axios to fetch recipe with `https://www.food2fork.com/api/get?key=${key}&rId=${this.id}` - ` key & rId` from documentation.

• Set an `.addEventListener` to the global `window` object, and set it to detect a `hashchange`. Use `const id = window.location.hash;` to use global window object, grab the location (in the search bar) of the hash, anything after the `#` ex. `#334554`; - look at ways to have two event listeners in one line of code: `['hashchange', 'load'].forEach(event => window.addEventListener(event, controlRecipe));`

• Create `parseIngredients` function in recipe model to grab uneccessary brackets, long units and convert them to abbreviations ex. tablespoons = tbsp. Use regex `ingredient.replace(/ *\([^)]*\) */g, ' ');` to remove braces and replace with empty string. **Consider fixing `slice` error/bug**.

• Play with `@keyframes` to instil spinning effect using CSS `animation: rotate 1.5s infinite linear;` prop. 

**Link(s) to work**

1. [Notes](https://github.com/mostmojo/forkify/blob/master/src/notes.md)
2. [Window.location](https://developer.mozilla.org/en-US/docs/Web/API/Window/location)
3. [codepen - spinner](https://codepen.io/most_mojo/pen/vqaGQQ)

-----

### Day 63: Friday, 5th July, 2019

**Today's Progress**

• Parse ingredients into count, unit and ingredient places. Use `.findIndex(el2 => unitShort.includes(el2));` &rarr; a new ES7 method to find the index of any element, which `includes()` that element. Ex. Does the array include an element called 'ounces', what's its index?

• Use `eval()` to evaluate numbers and add them up if they are obscure. `4 + 1/2 = 4.5`, use `slice()` to slice methods up at a given index, and later `join()` them with `(' ')` empty space.

• Make a recipeViews to renderRecipe with `.map()` and `${recipe.ingredients.map(el => createIngredient(el)).join('')}` and call `elements.recipe.insertAdjacentHTML('afterbegin', markup);` to render it. Link the recipe controller to the view. 

• Clone existing craft site via github, and import the database into `mySequelPro`, add `env` files and integrate `docker` links. Add new nav bar element to existing site with key:value pair to determine `slug` vs `title content`. Look at git and terminal command shortcuts to quicken work flow. Install `code .` to open files in VS Code via terminal 😊

**Link(s) to work**

1. [Notes](https://github.com/mostmojo/forkify/blob/master/src/notes.md)
2. [Unix cheatsheet](http://cheatsheetworld.com/programming/unix-linux-cheat-sheet/)
3. [Nav element](https://www.casarotto.co.uk/)

-----

### Day 64: Saturday, 6th July, 2019

**Today's Progress**

• Integrate `fractionJS`, small library for doing simple arithmetic in Forkify project. Use destructuring to separate integer and decimal using `const [int, dec] = count.toString().split('.').map(el => parseInt(el, 10));` for ex. `count = 2.5 => [2, 5]` and use `return ${int} ${fr.numerator}/${fr.denominator} // 2 1/2` numerator/denom from library to render necessary ouput.

• Teach at `CoderBrixton` 🙂. Used `HTML, CSS, JS` to create an interface for a math game. Install `jQuery CDN` to use shorthand query selectors. Build markup for title, score, maths sections and status bar with up/down buttons and enter key and style. (Math calculating game with status bars).

• Use JS to select all status bar elements by id, and set `classList.add(visibility, hidden);` Make modular functions, imported with script tags to select id and concatenate `variableName + 1` expression result, on event click. Using `callback functions` to trigger the `moveUp` and `moveDown` button events. Ex. `document.querySelector('moveUpButton').addEventListener('click', moveButtonUpFunc);`

**Link(s) to work**

1. [formatCount()](https://github.com/mostmojo/forkify/blob/master/src/js/views/recipeView.js#L8)
2. [coderbrixton](http://coderbrixton.com)
3. [JS Math game](http://www.garethshapiro.com/item/teaching-beginner-programmers-how-to-code)
4. [Destructuring](https://wesbos.com/destructuring-objects/)
6. [fractionJS](https://github.com/ekg/fraction.js/)

-----

### Day 65: Sunday, 7th July, 2019

**Today's Progress**

• Make `updateServings(type)` function with types `'dec'` and `'inc'`, with ternary operator assigning a `+/- 1`. Loop through ingredients with `forEach` and update count with `ing.count *= (newServings / this.servings);` before setting `newServings` to `this.servings;`. - All in recipe.js model

• `AddEventListener` on click to check if `e.target.matches('.btn-decreases, .btn-decreases *')` class and update the `state.recipe` object with `updateServings()` function results. Do the same for `'increases'` class in `if/else statement.` - All in index.js controller

• Create `updateServingsIngredients` variable in UI which holds a `recipe` parameter. Use `querySelector` to replace `textContent` with `recipe.servings`. Use `Array.from` to select `recipe__count class`, loop through all the elements and set the textContent to `recipe.ingredients[i].count` which basically sets the counter number to the relevant ingredient, as wrapped with `formatCount` function from previous `fractional.js library`. - All in recipeView.js - this completes the recipe section.

**Link(s) to work**

1. [formatCount()](https://github.com/mostmojo/forkify/blob/master/src/js/views/recipeView.js#L8)
2. [matches](https://developer.mozilla.org/en-US/docs/Web/API/Element/matches)

-----

### Day 66: Monday, 8th July, 2019

**Today's Progress**

• Look into various VS Code & git shortcuts to quicken workflow. 

• Create new list model and build a list class with a constructor pointing to an empty array. Create `addItem` function with params `count, unit, ingredient` and set an item object to `count: count, unit: unit and ingredient: ingredient`. Install `uniqid` library and import it to list model. Add CRUD functionality to model and controller to delete & update items. 

• Make a `listView` view to render markup of selected shopping item dynamically w/ `elements.shopping.insertAdjacentHTML('beforeend', markup);`- also delete item functionality with `item.parentElement.removeChild(item);` since the elements are not present on page load and are nodes in the DOM. 

• Participate to open source HTML Handbook by editing some code/explanations.

**Link(s) to work**

1. [Notes](https://github.com/mostmojo/forkify/blob/master/src/notes.md)
2. [git amend](https://www.atlassian.com/git/tutorials/rewriting-history)
3. [github fork](https://dev.to/ceri_anneblog/how-to-fork-and-contribute-to-a-github-repo-5bfp)
4. [VS shortcuts](https://code.visualstudio.com/shortcuts/keyboard-shortcuts-macos.pdf)  🙏🏼 @michailb
5. [uniqid](https://github.com/adamhalasz/uniqid)
6. [HTML Handbook - Flavio](https://github.com/flaviocopes/html-handbook)

-----

### Day 67: Tuesday, 9th July, 2019

**Today's Progress**

• Merged HTML handbook open source participation 🎉. Learned a lot in doing so about `input types`, `iframes`, `video`, `src`, `meta` data tags, `block` vs `inline` style, `get/post` requests, `tables` and `accessibility`. 

• Contine with forkify project, create `likesView` and `listView` views with specific `markup` renders to the browser and also integrated with the `likes` controller. Kept everything outside of functional scope to ensure data was 'saved' in memory. Ex. `likesView.toggleLikeMenu(state.likes.getNumLikes());`.

• Start first group project with `kanban` for architect client. This involved planning using invision mockup designs, segmenting `sections`, `fields`, `channels`, etc in `Craft CMS` and `Kanban Flow` chart, `startsite` in terminal/docker scripts, downloadable databases in `mySequelPro` and start planning structure of components, fonts, styling, colors. 

• **Tips:** 1. `cmd + ->` , to hop from beginning to end of code line, `cmd + shift + -> ` , to hop and highlight. <br/>
2.`.some__class[href*="#${id}"]` &rarr; select an element with an attribute `href` whose value contains at             least one occurrence of `${id}` (it will be replaced with a specific number) within the string.

**Link(s) to work**

1. [Notes](https://github.com/mostmojo/forkify/blob/master/src/notes.md)
2. [HTML Handbook - Flavio](https://github.com/flaviocopes/html-handbook)
3. [Attribute selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors)

-----

### Day 68: Wednesday, 10th July, 2019

**Today's Progress**

• Learn about `Kanban flow` and `Agile/Waterfall` methodologies. Install `composer`, `craft CMS` and start first team project.

• Segment design into resusable components and follow through craft entries, fields, sections. Once implemented, create first component using `for loops`, set variables, and use ex. `entry.title` to query DB, and get some data from Craft's backend &rarr; some query examples: `{% for item in entry.listingImageOrVideo.all() %}`, `{{ image( item.image[0], 'listingImage', null, 'card__image' ) }}`, render it to the browser using `index.twig` file and `include` method : `{% include 'template.html' with {'entry': 'something'} %}`

• Finish `forkify` app and use `localStorage` to ensure data is encapsulated on reload, within memory. Explore `JSON.parse` and `stringify` methods to convert data to and from strings to `JavaScript objects`. Run into small build error with `bundle.js` not rendering to github but will figure out the build script in `package.json`.

**Link(s) to work**

1. [Forkify repo](https://github.com/mostmojo/forkify)
2. [include](https://twig.symfony.com/doc/2.x/tags/include.html)

-----

### Day 69: Thursday, 11th July, 2019

**Today's Progress**

• Start building components with twig syntax, html & SASS. Ensure to use `{% extends base %}` to bring content into another file from base, and use `{% include.x_file with 'entry': 'x' %}` 

• Learn about targeting `input[type='text']` elements in forms, `::after` pseudo classes for adding arrows after designated class, transform props, and modifiers vs element nesting.  

• Class naming for reusability, `placeholder` text in forms, `hover & focus` classes and using `Tower` for git commit management. 

**Link(s) to work**

1. [class names](http://chir.ag/projects/name-that-color/#6195ED)

-----

### Day 70: Friday, 12th July, 2019

**Today's Progress**

• Continue with team project. Create individual components such as `channel-card` with `macro` imports for `images`, `loops` with `switch` statements to check whether image or video is present and reusable CSS classes to style similar components. 

• Learn about `accessibile` & `semantic`, `invisible` headers. Use `::before` pseudo class to insert icons, `@include` and `@extend` CSS magic. 

• Use twig's `include` `with:` within a `grid` system to render components in other templates. Use `pagination macro` to set pages up with limits (ex. 9 images) depending on their required listings. Use `( loop.index % 4 == 3 or loop.index % 4 == 0 )` to render images in a specific `grid layout` depending on their loop index positions.

• Intro to Node.js with `file system`, `http` and `url` packages, `JSON.parse` some data into a JS object, create a local server with `http req` and `res` and implement responses with `writeHead` and `end` with `200 / 404` network requests. Ensure to understand `routing`, `pathnames` and `query strings`. Ex. `github.com/products?id=4&name=bob`. Write callbacks to listen at port `server.listen(1337, '127.0.0.1')`. Install `nodemon` utility, that monitors for any changes in your source and automatically restart your server.

**Link(s) to work**

1. [KA - private](https://github.com/ten4design/knight-architects)
2. [laptop-store](https://github.com/mostmojo/laptop-store-nodejs/blob/master/index.js)
3. [nodemon](https://nodemon.io/)

-----

### Day 71: Saturday, 13th July, 2019

**Today's Progress**

• Continue with nodeJS laptop store app. Create reuseable function to `replaceOriginalHtml` with `let output = originalHtml.replace(/{%PRODUCTNAME%}/g, laptop.productName);` 

• Use regex to determine image file types and serve them with `res.writeHead` method and `((/\.(jpg|jpeg|png|gif)$/i).test(pathName))` test. 

• Create callback within callback function to `fs.readFile(${__dirname}/templates..` extract the data and create new array with `laptopData.map(el => replaceTemplate(data, el)).join(''); console.log(cardsOutput);` and use the newly made html from card component and push it into each iteration of the JSON object with `replace` method.

**Link(s) to work**

1. [Laptop-nodejs ](https://github.com/mostmojo/laptop-store-nodejs/blob/master/index.js)

-----

### Day 72: Sunday, 14th July, 2019

**Today's Progress**

• Look into node modules permissions error and change the owner from root to myself to allow access to `create-react-app` module to configure. Use `whoami` to find out details and `sudo chown -R ownerName: /usr/local/lib/node_modules` to ammend. Look into bash script `alias` for shortcuts. Update `lodash` vulnerability. 

• Install `create-react-app` and `npm` modules and start new **youtube-react** project. Import `React`, `ReactDOM` and `App` into `index.js` file and set `ReactDOM` to render on `#root id` with `document.querySelector`. Get `semantic ui` `cdn` for quicker CSS styling. 

• Create `app class` component and inject `SearchBar` component with basic container styling. Create SearchBar class component that `render() { return ( ... ) }` a form with label and input field. Set the value of the input to `this.state.searchTerm` and make a `this.onInputChange` event handler function that'll change the text from the input field. *Revisiting is so much better after intense JavaScript course! :)*

**Link(s) to work**

1. [Node module error](https://stackoverflow.com/questions/48910876/error-eacces-permission-denied-access-usr-local-lib-node-modules-react)
2. [Youtube-react](https://github.com/mostmojo/youtube-react)

-----

### Day 73: Monday, 15th July, 2019

**Today's Progress**

• More component driven development in `Craft CMS`. Look at `relatedEntry` fields to pull data through other entries such as related blogs or news from channel section. Always check to see if it's present: `{% if entry.relatedArticle|length > 0`. %

• Look at the `loop.index` of a project entry and use the `modulo operator` to check for the remainder of the `index` position and give the relevant grid class to position a series of images in a specific order. Use `switch/case` to alternate between image and video content blocks and check if they are there, then apply relevant styling. 

• Finish off with 2 React functions - o`nInputChange` and `onFormSubmit`, to set `this.setState` to `event.target.value` from the UI. Then, use `onFormSubmit` `event.preventDefault` to ensure the page doesn't reload entirely when enter key is pressed.

**Link(s) to work**

1. [null coalescing](https://twig.symfony.com/doc/2.x/templates.html)
2. [loop index](https://github.com/ten4design/knight-architects/blob/master/templates/projects/index.twig#L25)
3. [Youtube-react](https://github.com/mostmojo/youtube-react)

-----

### Day 74: Tuesday, 16th July, 2019

**Today's Progress**

• Querying an object with `{% set studio_approach = craft.entries.section( 'studioApproach' ).all() %}`. Set `projectInformation` field to a `table`, in `CraftCMS` that has a `label` & `value` column headings as `handles`. Set default values as `x & y` (ex. clients, programs), loop through them with a for loop  and display. Can also nest an `a4 / a8` grid within an `a5` grid 🤯

• Use twig macro to access images with `{{ image( entry.approachHeaderImage[0], 'imageGridFullWidth', '', 'approach__header-image' ) }}` - remember to use `entry.x[0]` to access the image within an entry. Querying a content block to extract `{{ item.itemContent }}` - create a for loop with `{% for item in entry.approachItems.all() %}` - name `item` as it is declared in the `block type` in the `matrix` block.

• Use `::after` pseudo class to create media-scrim with SASS' `$colour-media-scrim: transparentize( $colour-black, 0.7 );` method. Use `.class { top: 50%; transform: translateY( -50% ); }` to offset an element to center.

• Look into hiding API keys in react app with .env and `const API_KEY =${process.env.REACT_APP_API_KEY};`. Make an `onTermSubmit` function with preconfigured `youtube.get` method where inside, passed is the `/search` query string and `q: term` params. Assign `this.onTermSubmit` to `<SearchBar property />` in `App` component. Pass it into `SearchBar onFormSubmit` function with `this.props` - it's now linked!

**Link(s) to work**

1. [KA - priv](https://github.com/ten4design/knight-architects)
2. [Matrix blocks](https://docs.craftcms.com/v3/matrix-fields.html#templating)
3. [Tables - Craft](https://docs.craftcms.com/v3/table-fields.html#settings)
4. [TranslateY offset](https://stackoverflow.com/questions/40530101/why-is-translatey-50-needed-to-center-an-element-which-is-at-top-50)
5. [Hide API Key React](https://stackoverflow.com/questions/48699820/how-do-i-hide-api-key-in-create-react-app)

-----

### Day 75: Wednesday, 17th July, 2019

**Today's Progress**

• Look at basic query objects with `{% set query = craft.app.request.getQueryParam( 'q' ) %}` to target search bar and extract the query `https://www.somewebsite.com/search` &rarr; `?q=hello`. Use `search_results|group( 'section' )` and `|lower` to group via related entries and display with JavaScript toggle library, which toggles the `.active` class.

• Pair programming for home page of client's project. Learn about the power of `emmet` and extent of 'nesting' ex. `.section.section--top>.header.header__info>p.name & tab`. Talk about redactor fields and design vs developing points, and focus on `{% include '_partials/_more-news' with { 'relatedNews': recent_news, 'headingOverride': 'News' } %}` for including components from other files and assigning the fields to variables.

• Continue YouTube React app. Assign `this.setState({ videos: response.data.items });` and make `App` functional component into `async/await` function with a `response` variable. 

**Link(s) to work**

1. [KA - priv](https://github.com/ten4design/knight-architects)
2. [YT - React](https://github.com/mostmojo/youtube-react/blob/master/src/components/App.js)

-----

### Day 76: Thursday, 18th July, 2019

**Today's Progress**

• Partials and includes in templates (Twig / Craft). When a partial is created and injection into another template will happen, we can set a `headingOverride` an `h2` will appear or not, like so: `<h2 class="page__sub">{{ headingOverride ?? 'Featured Projects' }}</h2>`. Include in the relevant template with - `{% include '_partials/_project-image-grid.twig' with { entry: projects, 'headingOverride': 'Featured Projects' } %}` - Remember to set variable up top to `craft.entries.section...`

• Learn about setting `craft.entries` `with` for `eager loading` - hence, reducing the amount of queries to the server and maintaining performance. 

• Look into using `pagination macro` for `{% paginate projects.limit( 8 ) as projects %}` that contains a **query object** with an as &rarr; `variable` name.

**Link(s) to work**

1. [KA - priv](https://github.com/ten4design/knight-architects)
2. [Eager loading](https://docs.craftcms.com/v3/dev/eager-loading-elements.html#eager-loading-image-transform-indexes)
3. [Pagination](https://docs.craftcms.com/v3/dev/tags/paginate.html#parameters)

-----

### Day 77: Friday, 19th July, 2019

**Today's Progress**

• Implement a `slideshow` in JavaScript with pips. Ensure folder architecture is correct with vendor files all linked and `.pips` classes for active and non active images or videos in the slideshow. Set `data-slide-interval="4000" data-pips-container-id="slideshow-pips`

• Check to see if `slideshowImageOrVideo|length` exists in the CMS field. Implement conditionals to check `{% if entry.headerImageOrVideo[0].type == 'video' and entry.headerImageOrVideo[0].vimeoId %}` & `{% elseif entry.headerImageOrVideo[0].type == 'image' and entry.headerImageOrVideo[0].image|length %}` and set media variables for both image and video like so: `{% set header_media = entry.headerImageOrVideo[0].vimeoId %}` & `{% set header_media = entry.headerImageOrVideo[0].image[0] %}`.

• Apply relevant styling depending on if the media variable is defined and exists. Remember that video positioning requires `absolute` properties and backdrop lineargradient filter. Use `<iframe>` tags for video. Use `image` macro for images. Finish the day with little tweaks on company website - spacing, font sizes and styling form inputs and discover: `label { &:last-child { xxx } }` 👶🏼

**Link(s) to work**

1. [KA - priv](https://github.com/ten4design/knight-architects)
2. [:last-child](https://css-tricks.com/almanac/selectors/l/last-child/)

-----

### Day 78: Saturday, 20th July, 2019

**Today's Progress**

• Finish off the development of React application. Create `onVideoSelect` with `this.setState({ selectedVideo: video });` and understand concept of passing `props` from parent `App` down to its children. Also, understand deeply nested `callback functions` to send items back up to the parent. 

• Use `semantic ui` grids in order to style the relevant `rows`, `columns` and `grids` to display the `videoList` and the `videoItem` components like Youtube.

• Understand concept of destructuring to avoid props.paramName and simply use curly braces. Use YT's embed feature within an `iframe` tag to insert the `src` from the object. 

**Link(s) to work**

1. [YT - React](https://github.com/mostmojo/youtube-react)
2. [Semantic UI grids](https://semantic-ui.com/collections/grid.html)

-----

### Day 79: Sunday, 21st July, 2019

**Today's Progress**

• Finish React YT clone and use `npm run build` from `create-react-app` preferences to create a `bundle` folder ready for production. Use `netlify` to host the project.

• Theory on `Redux` - state management for React app. Learn about Insurance company form flow - form, receiver, departments, and central company repository vs how it relates to `Redux` with `Action creator`, `action`, `dispatch`, `reducers` and `state`.

• Create `Action Creators` and `Action` for `createPolicy`, `deletePolicy` and `createClaim`, with `types` and `payloads`, following caps convention and returning plain JS object with `k:v` pairs and params. 

**Link(s) to work**

1. [YT - React](https://github.com/mostmojo/youtube-react)
2. [YT - site](https://dreamy-nobel-9542ac.netlify.com/)
3. [Codepen](https://codepen.io/most_mojo/pen/qedQXZ?editors=0010)

-----

### Day 80: Monday, 22nd July, 2019

**Today's Progress**

• Install existing craft project and manage errors with `ImageMagick`, `.env` files and `docker`. Add `file` to `Standard.json` to enable `PDF` file uploads in redactor `matrix blocks`.

• Fix `slideshow` implementation with small slideshow library. Ensure classes matched with relevant `add/removeClassLists`. Create linear-gradient using `::before` pseudo class on a `slideshow__slide` class. Ensure to use `content: '';` otherwise the `before` pseudoclass doesn't work!

• Create 3 `reducers` in `Redux` for mock up departments that take existing data & actions, modify and return that data based on the contents of the action. Learn about spread syntax `[...oldListOfClaims]` to return _new_ array with additional `action.payload` values. Use `return listOfPolicies.filter(name => name !== action.payload.name);` to return mock 'deleted' _new_ array of policies should the name param _not_ equal one in `payload` array. Hence, if it does equal, then assume policy to be deleted.

**Link(s) to work**

1. [PDF - redactor](https://craftcms.stackexchange.com/questions/13410/how-can-i-link-to-an-asset-from-the-rich-text-editor)
2. [::before - gradient](https://stackoverflow.com/questions/23375638/gradient-on-pseudo-elements)
3. [Spread syntax](https://codeburst.io/javascript-es6-the-spread-syntax-f5c35525f754)
4. [Redux - insurance](https://codepen.io/most_mojo/pen/qedQXZ?editors=0010)

-----

### Day 81: Tuesday, 23rd July, 2019

**Today's Progress**

• Integrate `loadomatic` JS library to `lazy load` more entries on click with an `Ajax` request. Also, consider `pagination` as fallback in case user doesn't use JS. 

• Look into CSS loading spinners with `::before` & `::after` pseudo-classes, `@keyframes` with `transform: rotate(0deg)`

• Build fictional interior design page with `@keyframes`, `display: flex` properties and practice div nesting, `flex: 1`, and `-webkit-background-clip: text;`, amongst `position: absolute` and deeply flexed elements.

•  _Redux_: First glance at `const { createStore, combineReducers } = Redux;` destructured functions with `store.dispatch(createPolicy('Alex', 20);` for example, and a final `console.log(store.getState());` - all alterations that are dispatched are shown in the the console.

**Link(s) to work**

1. [Loadomatic - priv](https://github.com/ten4design/ten4-framework/tree/master/addons/loadomatic)
2. [Loadomatic - int - priv](https://github.com/ten4design/ten4-2019/commit/c04f0105ab3245b6a56c745111a74fe506c7c88a)
3. [CSS loading spinner](https://projects.lukehaas.me/css-loaders/)
4. [Interior site](https://mostmojo.github.io/fictional-studio/)
5. [Redux - dispatch](https://codepen.io/most_mojo/pen/qedQXZ?editors=0010)

-----

### Day 82: Wednesday, 24th July, 2019

**Today's Progress**

• Solve the `loadomatic` JS library bug by tracing back behaviour of AJAX call, which needed a `preventDefault()` on click event, inside the loadomatic constructor class.  `this.trigger.addEventListener( 'click', ( event ) => { this.loadMore();
event.preventDefault(); } );` - otherwise page would reload entirely when `load-more` spinner was pressed, instead of render more content just beneath!

• Look at implementation of play / pause button with timer on slideshow. Utilize `svg unicode` from icomoon, and the JS `performance.now()` method with `Timer JS` library - with `pause`, `play`, `ended` and `reset` callback function params. 

• Read up on `lazy loaded` images with `data-src` attributes, using vanilla JS to `add/remove eventListners`.

• Model `create-react-app songs` boiler plate with `ReactDOM`, `React App` component and render it on `#root` inside `index.js` - plan Redux to manage state


**Link(s) to work**

1. [Loadomatic - tweak](https://github.com/ten4design/ten4-framework/tree/master/addons/loadomatic)
2. [Lazy loading](https://css-tricks.com/the-complete-guide-to-lazy-loading-images/)
3. [songs](https://github.com/mostmojo/songs)

-----

### Day 83: Thursday, 25th July, 2019

**Today's Progress**

• Implement own small `lazy loading` JS library to add/remove `classList( .lazy )` on `scroll`, `orientationChange` and `resize`.

• Add `.lazy-fade` class upon removal of `lazy loading` with `@keyframes`, using `animation: drop 1.825s cubic-bezier(0.86, 0, 0.07, 1);`. Had to explore `cubic bezier` animation speed to get a feel for what was possible. Resulted in picking an animation with a slow start and gradual acceleration.

**Link(s) to work**

1. [Lazyload - priv](https://github.com/ten4design/knight-architects/commit/71f0ff4b66dd9ba8d9c558b04bb20fa14389cd89)
2. [cubic bez - easein](https://easings.net/en#easeInOutQuint)
3. [lazyload.js](https://github.com/mostmojo/lazyload)

-----

### Day 84: Friday, 26th July, 2019

**Today's Progress**

• Look at mixin creation for responsive layout: `@mixin media( $max-width-or-breakpoint ) { @media only screen and ( max-width: get-breakpoint( $max-width-or-breakpoint ) ) { @content; } }` which later used as: `@include media( 1066px ) { } `.

• Ensure the `outline:none` of a specific animated loader disappears on click, for better UX. Further, look into company `grid system` with responsive `breakpoints`, minimizing a `12-12` to `6-6` grid, to adjust to screen size, specifically for mobile. (`a12-12 -> f6-6`).

• Make `action creators` for songs app to `selectSong` with `type: 'SONG_SELECTED'` which will be read in with `selectedSongsReducer` and return `action.payload;` should the song be selected. Also, make a `songsReducer` with a hardcoded array of objects with song `titles` and `durations` for the sake of understandig `Redux`! Ensure both `/reducers` and `/actions` directories have an `index.js` (where the above code is written into) as React automatically reads index files so thus, no need to write more code when importing/exporting! 

**Link(s) to work**

1. [mixin](https://sass-lang.com/documentation/at-rules/mixin)
2. [songs](https://github.com/mostmojo/songs)

-----

### Day 85: Saturday, 27th July, 2019

**Today's Progress**

•  Recap on `::before` & `::after` pseudo elements, with must have `content: '';` attribute and `background-image: linear-gradient` to display bg.

•  Responsive media queries using `mixins` and includes to make mobile-designs. Examine grid system with `flexbox` wrappers, `flex: wrap` and `flex: 1`.

•  React-redux recap- action creators & reducers and component driven development to manage state. 

**Link(s) to work**

1. [songs](https://github.com/mostmojo/songs)

-----

### Day 86: Sunday, 28th July, 2019

**Today's Progress**

•  Continue songs app. Tie in `semantic-ui` for quick CSS in app.js, with grids, to display `SongList class` elements nicely.

•  Import/export default `connect` from `react-redux` library with `mapStateToProps` and `selectSong` object as params.

• Import/export `combineReducers` method from `redux` library with songs & selectedSongReducer as k:v pairs in an object. Wrap the ReactDOM render method's `<App />` in `<Provider store={createStore(reducers}>` which talks to the `app's` state.

**Link(s) to work**

1. [songs](https://github.com/mostmojo/songs)


-----

### Day 87: Monday, 29th July, 2019

**Today's Progress**

•  Work to improve dev-weakness - CSS layouting. Imitate a design from scratch, and understand fundamentals of structure and layout. Brush up on semantics such as `blockquote`, `cite`, `nav`, `section`, `header` - the little things! Keep CSS3 - `display: flex`, `justify-content: space-between` and `margins` always from parent elements downwards.

• Utilize `background-size: contain` to scale the image as large as possible without cropping or stretching the image as part of a header logo element.

• Pair programming to re-implement `lazy loading JS` function with the more modern `intersection observer API`, which asynchronously observes changes in the intersection of a target element with an ancestor element or with a top-level document's viewport - by targeting `[data-lazy-iframe], [data-lazy-src]` and `element.appendChild( image );` into the parent `div`.


**Link(s) to work**

1. [codepen](https://codepen.io/most_mojo/pen/NQdyZE)
2. [blockquote](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/blockquote)
3. [Intersection Observer API](https://developer.mozilla.org/en-US/docs/Web/API/Intersection_Observer_API)
4. [Lazy loading](https://github.com/ten4design/knight-architects/blob/master/raw/js/main.js#L28)

-----

### Day 88: Tuesday, 30th July, 2019

**Today's Progress**

• `Lazyload` meets `loadmore` JS lib - with `window.IntersectionObserver`, with `.hasAttribute`, `appendChild`, `removeAttribute`, `continue`, `typeof` `observe` & `unobserve`.

• More layout practice! Imitate architect site with 3 image components. Use `height: calc(100vh - 90px)` to keep page in same view port when applying margins outside of the `section` that impact the layout.

• Look into toggle handling for a desktop to mobile navigation bar. Basic functionality such as adding/removing a class like so:  `togglees[i].classList.remove( 'toggled' );` and inserting an `x` SVG or hamburger menu on click event.

• Revist `matrix blocks` in twig, with switch statements to check whether the `block type` is either `text` or a `quote` and inject the content accordingly like so: `{{ contentBlock.text }}`.

**Link(s) to work**

1. [codepen](https://codepen.io/most_mojo/pen/jgBKNL)
2. [Toggler func](https://github.com/ten4design/ten4-framework/blob/master/addons/toggler/libs/toggler.js)

-----

### Day 89: Wednesday, 31st July, 2019

**Today's Progress**

• Look into QA testing, `accessibility` and `page speed` along with `Aria-labels` to prepare for page production. Ensure, to keep a look out for `Nginx CGI cache` for lightning speed sites, of course, without enabling it where there is user sensitive data - i.e log in details, passwords. 

• Research touch devices to consider hover states vs no hover states. i.e - `@media ( hover: none ) { opacity: 1; }` where applicable, due to the evergrowing trend of both small and most recently, large screen, touch devices. Distinguish between `fine` (mouse) & `coarse` (finger). For pointers - i.e - `@media (pointer: coarse) { ... }`

• Study use of `relatedTo` parameter in `Craft CMS`, to return elements related to given elements, also, with an additional object with a sourceElement and field tag if needed. i.e. - `{% set relatedDrinks = craft.entries.section('drinks').relatedTo(drink).all() %}` & `{% set ingredients = craft.entries.section('ingredients').relatedTo({ sourceElement: drink, field: 'ingredients'}) %}`.

• Create a card element. Place a `.card__overlay` wrapper around an `<img src="image.png">` - set a `position: relative` to the `.card__overlay` as it's the parent, and create a pseudo class `::before` to absolutely position a background property linear gradient and make it invisible with `opacity: 0;`. Outside the `before block`, inside the `.card__overlay` block, target the `:hover` state's `::before` pseudo class and set it to `opacity: 1;`. Additionally, add `.card__title` inside the `.card__overlay`'s `hover` state, that way making the title text visible when a user hovers anywhere on the card, and not only where the title is placed! 👾

**Link(s) to work**

1. [Accessibility](http://wave.webaim.org/report#/https://www.knight-architects.ten4dev.com/)
2. [PageSpeed](https://developers.google.com/speed/pagespeed/insights/)
3. [Touch devices](https://css-tricks.com/touch-devices-not-judged-size/#article-header-id-2)
4. [relatedTo](https://docs.craftcms.com/v3/relations.html#templating)
5. [Codepen - card](https://codepen.io/most_mojo/pen/rXmgZq)

-----

### Day 90: Thursday, 1st August, 2019 🎉

**Today's Progress**

• Make `mixin` to manage breakpoints, with modern `@if` logical operator in `SASS`. Like so: `@mixin respond($breakpoint) { @if $breakpoint == phone { @media only screen and (max-width: 37.5em) { // 600px / 16 @content; } }` and when necessary, instead of rewriting the whole thing, use `@include respond(phone) { };`

• Build hamburger menu navigation with a couple of `<li>` items. Use `position:fixed` to keep circular `bg` elements in place and unaffected by scrolling, `background-position` to move a background image (or gradient) around within its container. Use `&, &::before` & `&::after` pseudo elements to absolutely position the three lines and `transform: rotate(135deg);` them when checkbox is `:checked`. Utilize `~` selector to more generally target elements that follow a specific tag, i.e - `h4 ~ p { do something.. };`

• Use `Browser Stack` to run browser tests and see how things as viewed on IE11, FireFox, Safari, Chrome, etc. 

**Link(s) to work**

1. [Codepen - menu](https://codepen.io/most_mojo/pen/dxRKBy)
2. [Mixin - breakpoints](https://css-tricks.com/snippets/sass/mixin-manage-breakpoints/)
3. [position: fixed](https://css-tricks.com/almanac/properties/p/position/)
4. [background-position](https://css-tricks.com/almanac/properties/b/background-position/)
5. [ ~ tilde selector ](https://www.cssportal.com/blog/what-does-and-do-in-css/)
6. [Browser Stack](https://live.browserstack.com)

-----

### Day 91: Friday, 2nd August, 2019

**Today's Progress**

• Look into blog related performance, image handling and critical css. Also, deep dive into HTML form styling, and understand `get/post`, `type=""`, `labels` & form `ids`.

• Go over `inline` and `block` elements to understand when to utilize the `display: block` property. Also, refresh on SASS folder architecture with the correct imports and create a script with `npm`, in a `package.json` file to enable everything to serve locally and also build for 'production' with `prefixer` & `compressors`.

• Learn about targeting `input[type="text"], input[type="password"]` fields, how to change the `hover` state of buttons for better UX and all about correct layouts, frames and margins. 


**Link(s) to work**

1. [Performance](https://www.smashingmagazine.com/2019/07/web-on-50mb-budget/)
2. [Critical CSS](https://github.com/pocketjoso/penthouse)
3. [Styling HTML forms](https://developer.mozilla.org/en-US/docs/Learn/HTML/Forms/Styling_HTML_forms)
4. [Log in form](https://mostmojo.github.io/login-form/)

-----

### Day 92: Sunday, 4th August, 2019

**Today's Progress**

•  Read about basics of setting up `Jest` for testing JS, with `sum.js` file, importing it into `sum.test.js`, applying script to `package.json` and running test in CLI with `yarn/npm`.

•  Look into another test example with `test('Fake test', () => { expect(true).toBeTruthy });` to familiarise myself with syntax. Using `expect`, aka an `assertion` with a result.

**Link(s) to work**

1. [Jest](https://github.com/facebook/jest)
2. [LevelUpTuts](https://youtu.be/b3VJVwQzw_Q)

-----

### Day 93: Monday, 5th August, 2019

**Today's Progress**

• Look into `categories`, `matrix blocks `and relational DBs in CraftCMS and understand `source` vs `target` relationships with `entry types`. 

•  Fix `docker` update issue in `CLI` by declaring the port where the local server should be served. 

• Create component with `ternary operators`, `logic` to check if certain conditions are met in `twig`, to then pull out `entry.title || entry.subtitle`, etc. Use `Invision's` inspect to gauge designs and commence build implementation for a project. 

**Link(s) to work**

1. [Relations](https://docs.craftcms.com/v3/relations.html)

-----

### Day 94: Tuesday, 6th August, 2019

**Today's Progress**

• Create footer with tailwind-like reusable classes for `flex`. Use: `<div class="grid flex flex--align-center">` as shorthand props to the well known `display: flex`, `align-items: center;` & utilize flexbox's `row/col` relationship with `grid` & `grid__item a6-12`, for example. Understand that a 12-column grid that doesn't necessarily have 12 columns will also wrap everything accordingly. Use `.container` with `max-width` properties to determine layout initially. 

•  Understand purpose of `{% cache globally using key 'legal-entries' %}` to prevent requests being made continuously for legal items - i.e. - privacy, cookies, etc. Use classes like so to apply correct styling: `<li class="footer__item"><a class="footer__link" href="{{ item.url }}">{{ item.title }}</a></li>` and Twig's shorthand syntax to query the entries for the appropriate url & titles. 

• Use `aria-label="CompanyX on Instagram" rel="noopener"` for accessibility and `noopener` to prevent malicious redirects when clicking a link to new page.

• With SASS, ensure to think simplistically, apply general styling (color, padding, etc), a container, then go deeper into elements whether left or right, item, link, `:hover & focus` states.

• When building components, understand that there are various checks in a CMS setting that should be applied. i.e. - `{% set image = entry.listingImage|length ? entry.listingImage[0] : entry.primaryImage|length ? entry.primaryImage[0] ?? null %}`, giving the client more space to do as they wish. The styling in the component will _not_ include layout. The grid & general appearance should be integrated inside the `listing page` where the element/card, etc will be rendered into. 

**Link(s) to work**

1. [Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)

-----

### Day 95: Wednesday, 7th August, 2019

**Today's Progress**

• Use `includes` in Twig for component driven development. Create an agnostic component with a declared variable like: `cta` that queries `cta.name`, etc. In the desired template, use `include ... with { cta: entry.callToAction[0] }` being the name of the field and array position.

• Reuse general SASS components and nest with BEM modifiers, apply `@extends %class-name` for styling. 

• Start React-based form with `Material-UI` dependency for quick CSS. Use `state` and pass down props to child components. 

**Link(s) to work**

1. [React form](https://github.com/mostmojo/react-form)

-----

### Day 96: Thursday, 8th August, 2019

**Today's Progress**

• Continue with `includes`. Fuse two components into one by interpreting design and logical operators. Ensure to keep variable naming general for reusability.

• Use flexbox with grid system to apply a design layout for 3 images and use `flex reverse` on `light switch` click from CMS. Continue with SASS nesting and modifier reusability, and look into the purpose of the `parent selector`.

• Look into new chrome `loading attribute`, used in an image like so: `<img src="image.png" loading="lazy" alt="…" width="200" height="200">`, which will prevent the use of JavaScript for lazy loading images (performance measure). 

• Use Craft's in-built `focal point` feature but also aware of cache busting bug.

**Link(s) to work**

1. [& - parent selector](https://sass-lang.com/documentation/style-rules/parent-selector)
2. [Loading attribute](https://web.dev/native-lazy-loading)
3. [Cache busting bug](https://github.com/craftcms/cms/issues/3685)

-----

### Day 97: Friday, 9th August, 2019

**Today's Progress**

• Piece together several components in Twig, using `{% include '_component/_generic-intro' with { 'headline: entry.pageHeadline, 'media: entry.pageImageOrVideo[0] ?? null', 'stacked': true } %}`. Ensure to `{% set jobs = craft.entries.section( 'careers' ).all() %}` prior to conducting a loop so Craft can relate to the section where it will be queried. 

• Run through `container--bleed` classes to understand layouting and how they work with `flex` helper classes, alongside `flex-direction: column;`, `align-items: center;`

• Create a `{% if stacked is defined and stacked == 'true' %}` *stacked* variable inside the `general-component` to provide a different layout with these logical checks. Another example of a ternary operator check: `{{ stacked is defined and stacked == 'true' ? ' mb-1' }}` within a div, to apply a `margin-bottom` helper class.

• Work on reusable `SASS` classes such as `card_title`, to nest `card_title--alt` modifiers within, that will take presidence due to specificity.

**Link(s) to work**

1. [includes](https://twig.symfony.com/doc/2.x/tags/include.html)

-----

### Day 98 & 99: Saturday & Sunday, 10th & 11th August, 2019

**Today's Progress**

• Research UI/UX and best way to create a user form. Chose `MaterialUI`, installed via `$ npm install @material-ui/core` as a project dependency in `package.json` file. 

• Created a react app using `create-react-app` that resembled a 4-part user journey with `UserForm` being the parent component that holds the state. Used `destructuring` to extract steps to go to `nextStep` and `prevStep`. Render it all in a switch statement for various page cases like so: `<Privacy nextStep={this.nextStep} prevStep={this.prevStep} handleChange={this.handleChange} />`, with `handleChange` containing all the `event.target.value`s.

• Explore material UI styles for labels, and controls with `control={ <Checkbox /> } label="Receive communication by email for other products created by the team" style={styles.mb}`, `onClick={this.continue}` in React and creating objects to style elements in CSS like so: `const styles = { button: { margin: 15 }`.

**Link(s) to work**

1. [React form](https://vigilant-kirch-c0de1d.netlify.com/)
2. [Form source code](https://github.com/mostmojo/react-form)
3. [Material UI](https://material-ui.com/)

-----

### Day 100 🎉: Monday, 12th August, 2019

**Today's Progress**

• Create an `Awards page` for client using individual components in Twig. Ensure to `{% set awards = craft.entries.section( 'awards' ).all() %}` to later be able to query the objects in a loop.

• Look into the `dump` PHP variable to check whether looping through an array, object, etc - handy!

• Loop through a matrix block using `{% for block in entry.awards.all() %}` and use `loop.index` to apply `flex-direction: row-reverse` to all entries that are odd like so: `<div class="block{{ loop.index % 2 == 0 ? ' block--reverse' }} grid">`. Use ternary operators to also check whether the `block.image|length ? ' a6-12' : 'a12-12'` and apply relevant rows/cols. Learn how to get a related entry's url with: `href="{{ block.relatedProject[0].url }}`.

**Link(s) to work**

1. [Matrix fields](https://docs.craftcms.com/v3/matrix-fields.html)
2. [Dump](https://twig.symfony.com/doc/2.x/functions/dump.html)

