👨🏻‍💻 [Previous #100DaysOfCode log](https://twitter.com/most_mojo/status/1085674532982214662)

<p align="center">
  <img width="120" height="120" src="https://res.cloudinary.com/mostmojo/image/upload/v1560979571/psy.gif">
</p>

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

### Day 28: Friday, 31st May, 2019

**Today's Progress**

• `#content` attribute for location anchoring on site. Use for onScroll effects with JS functions and CSS animations too. 

• Build `macros` in `Twig` and their functionality for images, social links and slider transforms. E.g.  `{% macro macroName(parameter1, parameter2) %}` - similar to JS functions, with `for loops` and `hashes`.

• Jonas course final restaurant challenge w/ data structures, objects, logical operators, loops and literals without solution. Tip: in JS we can utilize the `[i]` variable declared in the loop as a placeholder for iteration. Use `this.bill = something` or `this.bill[i]` to refer to variable/value. 

**Link(s) to work**

1. [Content attribute](https://developer.mozilla.org/en-US/docs/Web/CSS/content)
2. [Git shortcuts](https://ohshitgit.com/)
3. [Macros](https://www.google.com/amp/s/mijingo.com/blog/using-macros-in-twig-and-craft/amp)

---

### Day 29: Saturday, 1st June, 2019

**Today's Progress**

• Look into operator precedence on MDN docs to understand order that JS reads specific expressions and logical operators. Comes handy when using ex. `this.someArray.length;`.

• Review tip calculator challenge (pt.1) in Jonas' course. Understand use of `this` in JavaScript, the `i` counter variable and its usability.

• Start pt.2 - Apply similar functionality of `obj1` to `obj2` and think of average calculator `function` to apply to both objects.

**Link(s) to work**

1. [Operator precedence](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence)
2. [Tip Calculator pt. 1](https://gist.github.com/mostmojo/b31f62ee92e709cb6a9787698ef21206)

---

### Day 30: Sunday, 2nd June, 2019

**Today's Progress**

• Complete JS tip calculator challenge. Add reusable `function calcAverage(tips) { ... }` that takes ex. `john.tips` & `mark.tips` argument and can be used multiple times while staying DRY. Declare `var sum = 0` outside the loop so value doesn't reset once function is complete. Then `+=` tip values into the variable `sum` and `/ tips.length` to get average.

• Brief intro to `ES5` vs `ES6` syntax, purpose of comp/transpilers ex. `babel` and pros & cons of knowing both syntaxes. 

• Theory - code execution: `parser` &rarr; abstract `syntax tree` &rarr; conversion to machine code &rarr; code runs. Learn theory on `hoisting` - identify between `function declarations` (don't need to be declared before use) and `variable declarations` (Need to be declared before use). Also, learn about `global execution context` vs `functional execution context`. Ex. if `var age = 23;` is declared in global context, then also identical variable within a function, it'll render as their execution context differs 🤓. 

**Link(s) to work**

1. [Tip Calculator pt. 2](https://gist.github.com/mostmojo/b31f62ee92e709cb6a9787698ef21206)
2. [Hoisting](https://github.com/mostmojo/prod/blob/master/javascript-course/script.js)

---

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

---

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

---

### Day 33: Wednesday, 5th June, 2019

**Today's Progress**

• Create a url path using function `url('contact', { contact: entry.project[0].firstName })` to return `site.com/contact?contact=bob` - domain, path, query string hash

• Study `{% include x %}` components and what `key: value` pairs are passed and how they are used in `Twig`. Research `flex-shrink: 0;` for when flex items exceed container limit. 

• Make small tip calculator with `gradient`, `clip`, `webkit-fill`, the `transform: translateY` property and `calcTip()` JS function paired with `calcAverage()` (CRUD) for two fictional objects. 

**Link(s) to work**

1. [URL | MDN](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_URL)
2. [flex-shrink](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-shrink)
3. [calculator](https://codepen.io/most_mojo/pen/QRRdvw)

---

### Day 34: Thursday, 6th June, 2019

**Today's Progress**

• Built tip calculator with HTML, CSS & JS that rendered `calcTip()` and `calcAverage()` functions to the console in the DOM. Ensured syntactically to complete the challenge in both `ES5` and `ES6` declaring `key:values` with `this` keyword where appropriate.

• Study `functional` scope vs `class/variable` scope and how functions are read and hoisted depending on where they are invoked.

• Use `animate.css` library to create `zoomIn` & `zoomOut`-type effects in CSS for specific elements. Ensure semantic HTML tags such as `<section>` and `<figure>` were integrated. Once complete, rendered final restaurant bills in the `DOM`. 

**Link(s) to work**

1. [Calculator](https://github.com/mostmojo/tip-calculator)
2. [Variable scope](https://www.digitalocean.com/community/tutorials/understanding-variables-scope-hoisting-in-javascript)
3. [Animate.css](https://daneden.github.io/animate.css/)

---

### Day 35: Friday, 7th June, 2019

**Today's Progress**

• Refactored folder architecture of calculator project with `@import url(folder/file`) in `style.css` and added comments.

• Built bear cartoon from scratch using pure HTML `divs` and `css`. Utilize the power of subtleties like `position: absolute` and `border-radius: 100%;`. The use of `border-bottom: 2px solid #000;` property combined with `border-radius: 0% 0% 100% 100%;` to create half-moon shaped elements for a `mouth` was fun to figure out. Use `z-index` to bring elements on top of others. 

• Read blog on `accessibility` and learn not to use `a:focus { outline: none; }` as users that navigate using keyboard-only wouldn't able to get there. Best practice: `a:focus { background-color: #000000; color: #FFFFFF; }` - alternate 'hidden' styles.

**Link(s) to work**

1. [Calculator](https://github.com/mostmojo/tip-calculator)
2. [Bear](https://mostmojo.github.io/bear-ui/)
3. [Accessibility outline](https://medium.com/@matuzo/writing-css-with-accessibility-in-mind-8514a0007939)

---

### Day 36: Saturday, 8th June, 2019

**Today's Progress**

• Read a detailed explanation of how to creating pure `CSS` images. Distinguishing components, divs, shapes and how the overall layout of each element looks like. 

• Start build for DOM pig game. Implement `Math.floor(Math.random() * 6) + 1` global function to generate random decimal, round it down to nearest whole and ensure it fulfils 6-number dice roll. 

• Study `getters` vs `setters` with `document.querySelector("#current-" + activePlayer).textContent = dice;` example. Use `concatenation` with JS `type coercion` to set the value of a dice roll to a specific `id` in HTML. If applying HTML tags, use `.innerHTML` and tags in brackets. Ex. `document.querySelector("#current-" + activePlayer).innerHTML = "<em>" + dice + "</em>"`. To hide a CSS class w/ JS: `document.querySelector(".dice").style.display = "none";` (Method, property, value).

**Tip**: 1) Shortcut to open console: `cmd + alt + i` 2) this variable is only assigned a value when object calls a method.

**Link(s) to work**

1. [Pure CSS images](https://medium.com/coding-artist/a-beginners-guide-to-pure-css-images-ef9a5d069dd2)
2. [Pig game](https://github.com/mostmojo/prod/blob/master/javascript-course/DOM-pig-game/app.js)

---

### Day 37: Sunday, 9th June, 2019

**Today's Progress**

• Revise `querySelectors` by creating fun example with `getter` vs `setter`. Use setter with declared variable to change content in HTML with `textContent`. Set italics `<em>` with `.innnerHTML`.

• Set `.addEventListener` with two params: `(click, function() { // do something });` to change img `src` of dice roll to `diceDOM.src = "dice-" + dice + ".png";` and concatenate the class with variable value and suffix.

• Use `.getElementById` to grab scores and change `textContent` to 0. Ex. `document.getElementById("scores").textContent = "0";`. **Remember:** `callback functions` only work when the function/method is called. In `e`.handlers they can also be `anonymous` and belong to the `addEventListener` function as the 2nd parameter - only in that scope.

**Link(s) to work**

1. [querySelector](https://www.instagram.com/p/ByffDbhn3dW/)
2. [byId | img src](https://github.com/mostmojo/prod/blob/master/javascript-course/DOM-pig-game/app.js)

---

### Day 38: Monday, 10th June, 2019

**Today's Progress**

• Create koala component with several divs from scratch. Use `:root` to declare variables and use them with `background: var(--green);`

• Use `linear-gradient` with `bg-clip` and `text-fill-color: transparent` for modern text styling. Make triangle for koala hair with `clip-path: polygon(50% 0%, 0% 100%, 100% 100%);`. Build `@keyframes drop` element with states `0-50-100%` and use the `animation: text 1.625s ease 1.5s;` property to render the animation. 

• JS course: Add dice roll to `roundScore`, add ternary: `activePlayer === 0 ? activePlayer = 1 : activePlayer = 0;` to switch players and reset `roundScore = 0` both in DOM and HTML. Use `.classList.toggle("active")` to toggle the `classList` between the class `player-0-panel` and `player-1-panel` and hide dice img with .`style.display = "none".` **Note:** it's important to remember the DOM and HTML. Get JS code to do things in both, as the user will see the interface, not the console. 

**Link(s) to work**

1. [koala](https://mostmojo.github.io/koala-ui)
2. [clippy](https://bennettfeely.com/clippy/)
3. [DOM game](https://github.com/mostmojo/prod/blob/master/javascript-course/DOM-pig-game/app.js)

---

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

---

### Day 40: Wednesday, 12th June, 2019

**Today's Progress**

• Read on svg use, ex. `<button class="btn-new"><svg class="x"><use xlink:href="sprite.svg#icon-circle-with-plus"></use></svg>New game</button>` and how to use icomoon icons with a `sprite.svg file` including `fill: red` props for styling.

• Finish iteration of dice game. Refactor to stay `"DRY"` and create resuable functions `init()` & `nextPlayer()`. Add `state` variable `gamePlayer = true/false` to reset when winner is declared or game hasn't started. Use `document.querySelector(".player-0-panel").classList.remove/add("active");` in reset to ensure red dot is in the right player panel. Also, add idle function `.addEventListener("click", init);` initialized only on dice roll.

• Declare global `var lastDice` to save instance of `var dice`, containing `Math.floor(Math.random() * 6) + 1);` and create condition `if (dice === 6 && lastDice === 6)` then set memory & DOM `scores` to 0 and call `nextPlayer()` 🎲. Ensure `lastDice` is global or else data will be lost if declared in functional scope, once function ends.  

**Link(s) to work**

1. [svg|use](https://css-tricks.com/svg-use-with-external-reference-take-2/)
2. [Dice game code](https://github.com/mostmojo/prod/blob/master/javascript-course/DOM-pig-game/app.js)
3. [DOM game live](https://mostmojo.github.io/dice-roll/)

---

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

---

### Day 42: Friday, 14th June, 2019

**Today's Progress**

• Primitives (`null, undefined, boolean, number, string`) vs `Constructors`, their `instances` and the `prototype` chain. The way that `OOP` works, JS interactions and objects. 

• Create constructor objects `Person` and `Pokemon` with related `instances`: John, Mark || Pikachu, Slowbro to experiment with shared `prototype` function `calculateAge()` and `calculateDamage()`. This helped instil understanding of `inheritance`, the parent `object Object` properties ex. `toString()`, `hasOwnProperty()`, etc and **Prototype chain**.

• Use chrome dev tools to log instances and explore showcasing `Person prototype properties` (`__proto__:`) vs `object Object properties`

**Link(s) to work**

1. [Prototypes](https://github.com/mostmojo/prod/blob/master/javascript-course/advanced-js/script.js)
2. [Prototype Chain](https://github.com/mostmojo/prod/blob/master/javascript-course/advanced-js/notes.md)

---

### Day 43: Saturday, 15th June, 2019

**Today's Progress**

• Explore order of var declarations, `mutations`, passing `primitives` into functions to create a copy. Passing references of objects and mutating their values.

• Make example of `callback function` with for loop, using `.push` to put values of a function within a function into an array var. Ex. `arrResult.push(fn(arr[i]));`

• Build callback function to calculate max heart rate using 1) a generic function w/ a loop over an input array function `arrayCalc(arr, fn) { ... }`, give it a `fn` as input to calculate something based on each element of the array. `Ex. var rates = arrayCalc(ages, maxHeartRate)`, where `maxHeartRate` returns `Math.round(206.9 - (0.67 * element));` only if `ages are >= 18` and is also only called within the loop. Hence, callback successful 🤓. 

**Link(s) to work**

1. [Primitives & Objects](https://github.com/mostmojo/prod/blob/master/javascript-course/advanced-js/script.js)

---

### Day 44: Sunday, 16th June, 2019

**Today's Progress**

• Simple refresher on debugging via Treehouse course. Debug a few errors using the console. 

• Study functions that return functions, w/ shorthand syntax, ex. `interviewQuestion('teacher')('Mark');` Immediately invoked function expressions (`IIFE`) - w/ `(function () {...})()` to trick parser that it's an expression and not a declaration. In this case, we create a `private` scope. 

• Make `closure` function to understand the scope and memory storage. Inner `fn` always has access to vars & params of its outer function, even after outer `fn` has returned, so we can invoke a `fn` with all params.

**Link(s) to work**

1. [IIFE](https://github.com/mostmojo/prod/blob/master/javascript-course/advanced-js/script.js)

---

### Day 45: Monday, 17th June, 2019

**Today's Progress**

• Make question-based closure functions by wrapping the whole function in an `IIFE (function() {...})();`, thus make its scope private. That way if someone else were to use it, and he/she had a var called Question or n, it would not interfere.

• Use `Question.prototype.displayQuestion = function() { .. }` to set object's `this props` to `new` instance of `Question`.  Use `parseInt` to convert ex. `"2"` to integer, not string &rarr; `2`. Finally, use `callbacks` within functions to call other functions to `keepScores`.

• Start plan for budgety app. Make notes on `modules` regarding: `UI`, `Data` and `Controller`.

**Link(s) to work**

1. [Closures](https://github.com/mostmojo/prod/blob/master/javascript-course/advanced-js/script.js)
2. [Modules](https://github.com/mostmojo/budgety/blob/master/notes.md)
---

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

---

### Day 47: Wednesday, 19th June, 2019

**Today's Progress**

• Make `data` object of objects to hold expenses and incomes of app. Use `ID = data.allItems[type][data.allItems[type].length - 1].id + 1;` to add incoming data to the end of the array and assign it an id. 

• Create an `addItems()` public function to push new items into the UIController using `data.allItems[type].push(newItem);`. Use `querySelector` to grab elements, and set template html to them using `''` then `.replace` dummy values with dynamic values and `insertAdjacentHTML` and keyword `beforeend` to the UI.

• Use the `Array.prototype.slice.call(fields);` which is the global constructor `Object` to array-ify the user input values, and then set their current.value to `""` to reset the field. By setting `fieldsArr[0].focus()` we return back to the wanted element.

**Link(s) to work**

1. [call](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/call)
2. [focus](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/focus)
3. [preview site](https://mostmojo.github.io/budgety/)

---

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

---

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

---

### Day 50: Saturday, 22nd June, 2019

**Today's Progress**

• Focus on the tiny details 🤗 - The decimal display of the budget app elements. Use `Math.abs()` to get the absolute value of a number. Set the decimal values of the number to two with the **Number prototype** `toFixed(2)` ex. `1,200.00`.

• Divide numbers into substrings using `substr()`, use array data structures to capture integers and decimals with `.length` and set right commas ex. `int = int.substr(0, int.length - 3) + ',' + int.substr(int.length - 3, 3);` to output `23,500.00`.

• 

**Link(s) to work**

1. [preview site](https://mostmojo.github.io/budgety/)
2. [Math.abs)[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/abs]
3. [toFixed](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toFixed)
4. [Substring](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/substring)
