-----

### Day 1 : Tuesday, 14th August, 2019

**Today's Progress**

• Develop a client's page where a straight line was needed from the design. Utilize `::before` & `::after` pseudo classes on a parent div to accurately portray the line. Lesson: Do not use pseudo classes on a parent `<img>` div as that's self closing and does not have pseudo classes!

• Learn about pulling dates from craft with `{{ entry.postDate | date("M d, Y") }}` and their various formats.

• Debugging broken code, especially with matrix blocks. If block is set to a specific section with a variable, always pull data with `variable_name.title` and not `block.title`.

**Link(s) to work**

1. [Entry post date](https://craftcms.stackexchange.com/questions/9890/display-entry-post-date)

-----

### Day 2: Wednesday, 15th August, 2019

**Today's Progress**

• Key learning: When using includes that have other includes - check to see if the `primaryImage` exists, file relates to the `image macro`, so assign in `entry.primaryImage[0]` - `entry` in this case because it's NOT an index page, so no for loop needed, just an if statement assigned to entry because it'll relate to the entry in this case - `templates > journal  > _entry.twig .`

• Use objects and arrays to set grid classes and transforms to some images from a component, using a dropdown menu in the CMS with narrow, medium, wide parameters that are simple strings, that now coincide with the grids and transforms. Use `{% set sizes = { narrow: ['a6-12', 'halfWidth'] %}` for example, then access it `<div class="grid__item {{ sizes[block.imageWidth.value][0] }}">` like any other array, and ensure to use `.value` to get the string.

• Use twig's `batch` for a gallery-like layout. `{% for row in block.images.all()|batch( 4 ) %}` to segment images in 4s. then set the row lengths to a variable and add the transforms. With some simple maths, apply the grid classes to the according batch like so: `<div class="grid__item a{{ 12 / row|length }}-12">`. Remember, when looping through a block which is agnostic to a template use: `block.images.all()` and NOT `entry`.

**Link(s) to work**

1. [Batch](https://twig.symfony.com/doc/2.x/filters/batch.html)
2. [Levels](https://docs.craftcms.com/v3/dev/element-queries/entry-queries.html#parameters)

-----

### Day 3: Thursday, 16th August, 2019

**Today's Progress**

• Learn and apply ternary operators inside of divs to be able to implement 12-point grids like so: `<div class="grid__item{{ entry.section.handle == 'people' ? ' a12-12' : ' a6-12' }}">`

• Setting `{% set is_people = entry.section.handle == 'people' ? true %}` enables a check, to apply specific styles according to whether the page is on '`people`' or not. That way, in component-drive development, when using `{% include listing_card with { 'class': is_people ? 'card--centred card--flat' : 'card--flat' } %}`, different styles can be applied if the `is_people` is set to `true` and/or false. Explained: This will search for the appropriate image if is_people is set to true. This will also apply the `card—centred card—flat` classes if is_people is true, and just apply `card—flat` if it's `false`/not defined. 

**Link(s) to work**

1. [Handle](https://craftcms.stackexchange.com/questions/1682/get-the-current-section-handle)
