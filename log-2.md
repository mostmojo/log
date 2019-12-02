-----

### Day 1 : Tuesday, 13th August, 2019

**Today's Progress**

• Develop a client page where a straight line was needed from the design. Utilize `::before` & `::after` pseudo classes on a parent `<div>` to accurately portray the line. Lesson: Do not use pseudo classes on a parent `<img>` div as that's self closing and does not have pseudo classes!

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

**Link(s) to work**

1. [Object fit](https://developer.mozilla.org/en-US/docs/Web/CSS/object-fit)

-----

### Day 8: Thursday, 22nd August, 2019

**Today's Progress**

• Remember when inside an entry template, and looping through a matrix block, use: `{% for block in entry.imageOrVideo.all() %}` and utilize `{% switch block.type %}` to check for `image` and/or `video` fields which can be grabbed with a macro like so: `{{ image( block.image[0], 'homePageListing', '', 'intro__media' ) }}`.

• When not using grid system, remember absolutely positioned images/divs can have `box-sizing: border-box;` to calc. any padding within their 'walls'. 

• To rid any side padding, can use: `right: $container-side-padding-wide * -1;` inside a class that is `position: absolute`.

**Link(s) to work**

1. [box-sizing](https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing)

-----

### Day 9: Friday, 23rd August, 2019

**Today's Progress**

• Ensure to add checks to see if images exist prior to styling to prevent errors if they don't exist. Ex. `{% if image is defined and image|length %}`. When fetching related entries for CTAs, ensure to have `.url` at the end of the query to get the URL and not the title like so: `<a href="{{ entry.introCallToActionLink[0].url }}" class="intro__info">`

• Use `float: right` and `float: none` to position elements correctly when moving from desktop to mobile. Use smaller sized grids for mobile layout like so: `<div class="a7-12 e12-12 g6-6">`. Use `display: flex; flex-direction: column;` to change the layout direction too. Handy to use `background-repeat` property to set how background images are repeated. A background image can be repeated along the horizontal and vertical axes. `repeat-x` will repeat an image on the x-axis. 

• When cloning projects using `npm`, errors regarding `sudo` and `permissions` can occur. List of `error` management - [here](https://github.com/mostmojo/fictional-studio)

**Link(s) to work**

1. [Resolve Permission](https://docs.npmjs.com/resolving-eacces-permissions-errors-when-installing-packages-globally%5D)
2. [Fictional Project Scripts](https://github.com/mostmojo/fictional-studio)
3. [background-repeat: repeat-x](https://developer.mozilla.org/en-US/docs/Web/CSS/background-repeat)

-----

### Day 10: Tuesday, 27th August, 2019

**Today's Progress**

• Play with the design of a fictional studio, decrease size of navigation bar and add animation effects. Also try to position paragraph with `display: flex;` & `flex-end` properties.

• Learn about form redirects with: `{% if not order or order.isCompleted == false %}{% redirect 'events' %}{% redirect 'events' %}{% endif #}{% endif %}`.

• Work with helper classes like `mb` or `separated-less` to create space between BEM styled elements by wrapping around them without changing semantics. 

**Link(s) to work**

1. [Fictional studio](https://mostmojo.github.io/fictional-studio/)

-----

### Day 11: Wednesday, 28th August, 2019

**Today's Progress**

• Build a `notice banner` with cookie-like behavior. Ensure to have `display: flex` and `display: none` classes to be toggled with JavaScript. As svg icons act like font, `@extend %icon-pseudo` brings them in and then they can be treated like `text` with `color` and `font-size` property alterations. Semantically, in HTML a `<button></button>` will do the job.

• JS: `addEventListener` on `'click'` to `classList.add` & `classList.remove` the toggled classes. 

• `document.cookie` looks like a variable but it's not. A cookie is created in the browser which persists until it expires or you remove it. `http` requests are stateless, so we need a cookie to 'save' the fact that a user has seen the notice without the cookie, the message would always appear, it's only because you've got it already that commenting the line out doesn't do anything.

**Link(s) to work**

1. [document.cookie](https://developer.mozilla.org/en-US/docs/Web/API/Document/cookie)

-----

### Day 12: Thursday, 29th August, 2019

**Today's Progress**

• Look into importing sprite files with icomoon.

• Using icomoon to use `symbol-defs.svg` to `sprite.svg` and implement all the files within a project architecture. In `HTML` use `<svg class="icon icon--9"><use xlink:href="{{ uncache( 'assets/img/sprite.svg#icon-paint---4' ) }}"></use>
</svg>` and use `fill: $colour-icon-dark-pink;` for colors.

• Due to the nature of the assets, when styling in a `raw` file, all assets are processed in a `public` file so therefore, using `assets/img` will display the files.

**Link(s) to work**

1. [Sprite](https://gist.github.com/mostmojo/8b7de71d82cfe5c85b8470913b411d16)
2. [Icomoon](https://icomoon.io/app/#/select)

-----

### Day 13: Friday, 30th August, 2019

**Today's Progress**

• Work with `svg` motifs to absolutely position them within a multi-page layout. Create multiple layouts that correspond to design. ensure to keep `fill` properties and use `@include media( f ) { }` breakpoints to go from desktop to mobile responsiveness. Experiment with `transform: rotate( 180deg );`.

**Link(s) to work**

1. [Rotate](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/rotate)

-----

### Day 14: Monday, 2nd September, 2019

**Today's Progress**

• Look into `filter: brightness(150%);` property for chrome & mozilla to apply to images and enhance their brightness. Also, read into Imager for Craft CMS using `{% set transformedImage = craft.imager.transformImage(image, { width: 500, effects: { modulate: [100, 20, 100] } }) %}`. 

• Tweak a few client sites to add `{% if entry.phoneNumber %}<p>{{ entry.phoneNumber }}</p>{% endif %}`, fix positioning of `quote` in `imageBlock`. Make quote grids wider to fit wireframe, by playing with `grid__items` `a8-12`, `a6-12`, etc. 

• Use `@include media( d ) { padding: 2rem 0; }` to ensure slick shift from desktop to mobile.

**Link(s) to work**

1. [Filter](https://til.hashrocket.com/posts/4jhm8rrq7c-lighten-and-darken-with-css-brightness-filter)
2. [Imager](https://github.com/aelvan/Imager-Craft)

-----

### Day 15: Tuesday, 3rd September, 2019

**Today's Progress**

• Add `imageLazy` macro to lazy load client's images on a project page with `{{ imageLazy( header_media, 'headerMediaImage', '', 'header-media__image' ) }}`. 

• Use `transition: opacity 3.7s ease-out;` to slow down overlay effect for client page.

• Focus on `search-bar` functionality in Twig template. With server-side querying use: `{% set query = craft.app.request.getQueryParam( 'q' ) %}`, and the results set to `{% set search_results = craft.entries.section( sections ).search( query ).orderBy( 'score' ).all() %}`, which will later be toggled with some JavaScript, and/or potentially displayed with an `element api`.

**Link(s) to work**

1. [KA - Search](https://github.com/ten4design/knight-architects/blob/master/templates/search.twig)

-----

### Day 16: Wednesday, 4th September, 2019

**Today's Progress**

• Look into `element API` and use `composer` to `composer require craftcms/element-api` and install the plugin using `./craft install/plugin element-api`.  Add API endpoints with `'section' => 'approach, expertise, careers, awards, projects'` inside the config file. 

• When using icons, `search-box--close { &::before { @extend %icon-pseudo; @extend %icon-pseudo--close; }` ensure that the `::before` pseudo class is used on a class that is **NOT** an `input` field, as they won't work on those. Then use `position: absolute` to place it according to the design.

• In twig syntax to redirect to a specific place, use the following syntax: `<button class="search-box search-box--icon"><a href="{{ url( 'search' ) }}" aria-label="Search"></a></button>` having an 'empty' button, with no text, can have the `url( 'search' )` to redirect it to the specific page. If it's home, use empty string. 

**Link(s) to work**

1. [Search bar](https://github.com/ten4design/goppion/compare/search-bar?expand=1)
2. [Element API](https://github.com/craftcms/element-api)

-----

### Day 17: Thursday, 5th September, 2019

**Today's Progress**

• Build search-box functionality on the side of a canvas/page. To do this, build a component like so:
```
<div class="search-box">
	<form class="search-box__form search-box__form--icon" action="{{ url( 'search' ) }}">
		<label for="search-box" class="invisible">Search</label>
		<input type="text" id="search-box" name="q" placeholder="Search" class="search-box__text-input" value="{{ query ?? '' }}">
	</form>
</div>
```

• Within the `search-box` class ensure to use `position: fixed` and `box-shadow: -20px 0 20px 1px $colour-searchbox-shadow;`  and use `right: -100%;` with a `width: 70%; & z-index: 1;` to ensure that it occupies that much of the screen space. Ensure to add the search icon inside the after pseudo class: `&::after { @extend %icon-pseudo; @extend %icon-pseudo--search; }`. 

• Use JavaScript toggle function to grab data attributes `var togglees = document.querySelectorAll( toggler.getAttribute( 'data-togglees' ) );` and add `toggler.classList.add( 'toggler--b' );` adding the `right: 0%;` to make the pane visible/invisible on click.

**Link(s) to work**

1. [Search bar](https://github.com/ten4design/goppion/compare/search-bar?expand=1)

-----

### Day 18: Friday, 6th September, 2019

**Today's Progress**

• Examine the `toggler` function for adding/removing classes, for search vs closing icons.
```
( function () {
		// Toggle handling
		function handleToggle( toggler ) {
			var togglees = document.querySelectorAll( toggler.getAttribute( 'data-togglees' ) );
			return function () {
				for ( var i = 0; i < togglees.length; i += 1 ) {
					if ( togglees[i].classList.contains( 'toggled' ) ) {
						togglees[i].classList.remove( 'toggled' );
						continue;
					}
					togglees[i].classList.add( 'toggled' );
				}
				if ( toggler.classList.contains( 'toggler--a' ) ) {
					toggler.classList.remove( 'toggler--a' );
					toggler.classList.add( 'toggler--b' );
					return;
				}
				toggler.classList.remove( 'toggler--b' );
				toggler.classList.add( 'toggler--a' );
			};
		}
		var togglers = document.querySelectorAll( '.toggler' );
		for ( var i = 0; i < togglers.length; i += 1 ) {
			togglers[i].addEventListener( 'click', handleToggle( togglers[i] ) );
		}
	} )();
```

• This JS function selects all the attributes with `data-togglees` , checks to see if the `toggler` class exists and replaces the modifier class `--a` with `--b` which is the `closing` vs the `search` icon. Mark up:
```
<div class="search-box">
	<form class="search-box__form search-box__form--icon" action="{{ url( 'search' ) }}">
		<label for="search-box" class="invisible">Search</label>
		<input type="text" id="search-box" name="q" placeholder="Search" class="search-box__text-input" value="{{ query ?? '' }}">
	</form>
</div>
```
and
```
<button class="header__search toggler" data-togglees=".search-box" aria-label="Search"></button>
```

• When `position: absolute` elements, ensure that the icon is moving according to specific breakpoints like so. Remember that icons act like fonts so sizing and color can be altered the same way as fonts with `color` and `font-size`: 

```
.search-box__form {
	&--icon {
		&::after {
			@extend %icon-pseudo;
			@extend %icon-pseudo--search;
			@include font-size( epsilon );
			color: $colour-search-icon;
			position: absolute;
			right: 31.5rem;
			top: 12.5rem;
			@include media( c ) {
				right: 24.5rem;
			}
			@include media( d ) {
				right: 20.5rem;
			}
			@include media( e ) {
				right: 16.5rem;
			}
			@include media( f ) {
				right: 4.5rem;
			}
			@include media( g ) {
				right: 1.5rem;
			}
		}
	}
}
```

**Link(s) to work**

1. [Togglers](https://github.com/ten4design/goppion/blob/master/raw/js/main.js#L68)

-----

### Day 19: Friday, 18th October, 2019 (Learning resumes! Yay)

**Today's Progress**

• Dive into python via codecademy to get a taste of syntax/basics. Basic variable declarations with `color=red` and value converters (integers to strings or floats). Ex. `str(), int(), float()` conversions and `print`. 

• Download/install Anaconda GUI and play with jupyter notebook. 

• Use python's replacement operator `%02d` and import dates from its external `datetime` library like so:
```
from datetime import datetime
now = datetime.now()
print '%02d/%02d/%04d %02d:%02d:%02d' % (now.month, now.day, now.year, now.hour, now.minute, now.second)
```

• Look further into django docs for quick web app builds.

**Link(s) to work**

1. [Django docs](https://docs.djangoproject.com/en/2.2/)

-----

### Day 20: Tuesday, 22nd October, 2019

**Today's Progress**

• Comparators `> < = !=`, Booleans ( `True False`), Conditionals (with python syntax - `elif, ():`)
```
def grade_converter(grade):
    if grade >= 90:
        return "A"
    elif grade >= 80:
        return "B"
    elif grade >= 70:
        return "C"
    elif grade >= 65:
        return "D"
    else:
        return "F"
```
• Skin out company infrastructure via consultation to understand needs and create entire architecture using cloud services, etc.

• Volunteer for JS-based talk in Cyprus

• Look into DataSci track for self-learning via DataCamp

**Link(s) to work**

1. [CC - Python](https://www.codecademy.com/learn/learn-python)
2. [CyprusJS](https://cyprusjs.org/)
3. [DataCamp](https://www.datacamp.com/tracks/data-scientist-with-python)

-----

### Day 21: Friday, 25th October, 2019 

**Today's Progress**

• Look into React Native docs for potential iOS/Android app build. 

• Use RN syntax, which is like JSX to write/fetch styling in App.js like so: ` <Text style={styles.paragraph}>`, paragraph being an object with key/value pairs in the `styles` variable. 

• Create separate component for styling the app image and text. Use `export default class AssetExample extends React.Component` to export it into the App.js parent. Import it like so: `import AssetExample from './components/AssetExample';` - Same shizzle as React! :) 

**Link(s) to work**

1. [App](https://snack.expo.io/Byj8kQecH)
2. [RN docs](https://facebook.github.io/react-native/docs/getting-started)

-----

### Day 22: Monday, 2nd December, 2019 [Commence Data Camp Studies 🌀]

**Today's Progress**

• Start DataCamp's Data Analyst w/ Python route. Learn about `Data Frames` and dot notation to query rows in a data set with `print(credit_records.head())` to show first 5 results.

• Query `cols` with `[]` in case they have spaces or special characters like so: `suspect = credit_records['suspect'].` If they don't use dot notation; `price = credit_records.price`. Use `.inspect` to check out your DB.

• Apply logic to Data Frames to query specific data: `credit_records[credit_recrods.price > 20.00]`


**Link(s) to work**

1. [DC](https://datacamp.com)


-----
