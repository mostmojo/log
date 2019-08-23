-----

### Day 1 : Tuesday, 13th August, 2019

**Today's Progress**

• Develop a client's page where a straight line was needed from the design. Utilize `::before` & `::after` pseudo classes on a parent div to accurately portray the line. Lesson: Do not use pseudo classes on a parent `<img>` div as that's self closing and does not have pseudo classes!

• Learn about pulling dates from craft with `{{ entry.postDate | date("M d, Y") }}` and their various formats.

• Debugging broken code, especially with matrix blocks. If block is set to a specific section with a variable, always pull data with `variable_name.title` and not `block.title`.

**Link(s) to work**

1. [Entry post date](https://craftcms.stackexchange.com/questions/9890/display-entry-post-date)

-----

### Day 2: Wednesday, 14th August, 2019

**Today's Progress**

• Key learning: When using includes that have other includes - check to see if the `primaryImage` exists, file relates to the `image macro`, so assign in `entry.primaryImage[0]` - `entry` in this case because it's NOT an index page, so no for loop needed, just an if statement assigned to entry because it'll relate to the entry in this case - `templates > journal  > _entry.twig .`

• Use objects and arrays to set grid classes and transforms to some images from a component, using a dropdown menu in the CMS with narrow, medium, wide parameters that are simple strings, that now coincide with the grids and transforms. Use `{% set sizes = { narrow: ['a6-12', 'halfWidth'] %}` for example, then access it `<div class="grid__item {{ sizes[block.imageWidth.value][0] }}">` like any other array, and ensure to use `.value` to get the string.

• Use twig's `batch` for a gallery-like layout. `{% for row in block.images.all()|batch( 4 ) %}` to segment images in 4s. then set the row lengths to a variable and add the transforms. With some simple maths, apply the grid classes to the according batch like so: `<div class="grid__item a{{ 12 / row|length }}-12">`. Remember, when looping through a block which is agnostic to a template use: `block.images.all()` and NOT `entry`.

**Link(s) to work**

1. [Batch](https://twig.symfony.com/doc/2.x/filters/batch.html)
2. [Levels](https://docs.craftcms.com/v3/dev/element-queries/entry-queries.html#parameters)

-----

### Day 3: Thursday, 15th August, 2019

**Today's Progress**

• Learn and apply ternary operators inside of divs to be able to implement 12-point grids like so: `<div class="grid__item{{ entry.section.handle == 'people' ? ' a12-12' : ' a6-12' }}">`

• Setting `{% set is_people = entry.section.handle == 'people' ? true %}` enables a check, to apply specific styles according to whether the page is on '`people`' or not. That way, in component-drive development, when using `{% include listing_card with { 'class': is_people ? 'card--centred card--flat' : 'card--flat' } %}`, different styles can be applied if the `is_people` is set to `true` and/or false. Explained: This will search for the appropriate image if is_people is set to true. This will also apply the `card—centred card—flat` classes if is_people is true, and just apply `card—flat` if it's `false`/not defined.

• Loop through some related entries field and output the related entry titles like so: `{% for entry in entry.keySkills.all() %} --> keySkills being the related entries field 
		<a class="a key-skills__link" href="{{ entry.url }}">{{ entry.title }}</a>
{% endfor %}`. Learn to distinguish how to access matrix blocks, i.e - `{%  for block in entry.offices.all() %}`, where the block is `offices` inside the `entry`, then accessing each field - `{{  block.city }}` - for example.

**Link(s) to work**

1. [Handle](https://craftcms.stackexchange.com/questions/1682/get-the-current-section-handle)

-----

### Day 4: Friday, 16th August, 2019

**Today's Progress**

• Pair program - take a design from `inVision` - outline `UI/UX` and bring it into `Craft CMS` with entry types, fields, sections & design layout.

• Consider - `sections`, common `fields`, restrict images to `limit(1)`, find reocurring patterns, outline the `redactor config` to `standard/simple`, add groups i.e - `common`. Look at the entry types and utilize components where possible. Lastly, outline the `matrix blocks` eg. `eventContent` (`block types` with their `fields`)

• Spend the day looking into form building with the Craft plugin. Also, learn 'trick' in CSS to overlay an `input type='radio'` button with `::before` & `::after pseudo` classes using `<label>` since inputs are self closing divs and don't have pseudo classes - must be wrapped in labels! :)

**Link(s) to work**

1. [Form](https://github.com/craftcms/contact-form)

-----

### Day 5 & 6: Monday & Tuesday, 20th August, 2019

**Today's Progress**

• Twig includes, content blocks, matrix blocks and conditional logic to render generic components.

• `@extend %typeset;` for cleaner SCSS. 

• Switch blocks for `block.text`, `block.images`, `block.imageOrVideo` and the use of `smartdate` with a Craft plugin to generate events.

-----

### Day 7: Wednesday, 21st August, 2019

**Today's Progress**

• Focus on responsive design. Use `@include media( f ) { @include font-size( delta ); margin-bottom: 0.6rem; }` break points with CSS media queries and `@include` to change from desktop to mobile. 

• Use `object-fit: cover` to place the image and make it sized to maintain its aspect ratio while filling the element’s entire content box. If the object's aspect ratio does not match the aspect ratio of its box, then the object will be clipped to fit. E.g. `.event-card__image { height: 100%; img { height: 100%; object-fit: cover; } }`. With `:hover` states ensure to use `transition: color 0.2s;` for slick UX.

• Use `<div class="a6-12 d5-12 f6-6">` within divs to place the grids in the right col width to move from desktop to mobile. 

• Ensure that when using composer having `ignore` in `composer install --ignore-platform-reqs` to forget the errors. Remember with `includes` use `{% include listing_card with { 'image': is_people ? entry.personThumbnail[0] ?? null : entry.primaryImage[0] ?? null } %}`.

1. [Object fit](https://developer.mozilla.org/en-US/docs/Web/CSS/object-fit)

-----

### Day 8: Thursday, 22nd August, 2019

**Today's Progress**

• Remember when inside an entry template, and looping through a matrix block, use: `{% for block in entry.imageOrVideo.all() %}` and utilize `{% switch block.type %}` to check for `image` and/or `video` fields which can be grabbed with a macro like so: `{{ image( block.image[0], 'homePageListing', '', 'intro__media' ) }}`.

• When not using grid system, remember absolutely positioned images/divs can have `box-sizing: border-box;` to calc. any padding within their 'walls'. 

• To rid any side padding, can use: `right: $container-side-padding-wide * -1;` inside a class that is `position: absolute`.

1. [box-sizing](https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing)

-----

### Day 9: Friday, 23rd August, 2019

**Today's Progress**

• Ensure to add checks to see if images exist prior to styling to prevent errors if they don't exist. E.g. `{% if image is defined and image|length %}`. When fetching related entries for CTAs, ensure to have `.url` at the end of the query to get the URL and not the title like so: `<a href="{{ entry.introCallToActionLink[0].url }}" class="intro__info">`

• Use `float: right` and `float: none` to position elements correctly when moving from desktop to mobile. Use smaller sized grids for mobile layout like so: `<div class="a7-12 e12-12 g6-6">`. Use `display: flex; flex-direction: column;` to change the layout direction too. Handy to use `background-repeat` property to set how background images are repeated. A background image can be repeated along the horizontal and vertical axes. `repeat-x` will repeat an image on the x-axis. 

• When cloning projects using `npm`, errors regarding `sudo` and `permissions` can occur.

1. [Resolve Permission](https://docs.npmjs.com/resolving-eacces-permissions-errors-when-installing-packages-globally%5D(https://docs.npmjs.com/resolving-eacces-permissions-errors-when-installing-packages-globally)
2. [Fictional Project Scripts](https://github.com/mostmojo/fictional-studio)
3. [background-repeat: repeat-x](https://developer.mozilla.org/en-US/docs/Web/CSS/background-repeat)
