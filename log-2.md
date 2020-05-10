-----

### Day 1 : Tuesday, 13th August, 2019

**Today's Progress**

• Develop a client page where a straight line was needed from the design. Utilize `::before` & `::after` pseudo classes on a parent `<div>` to accurately portray the line. Lesson: Don't use pseudo classes on a parent `<img>` div as that's self closing and does not have pseudo classes!

• Learn about pulling dates from craft with `{{ entry.postDate | date("M d, Y") }}` & their various formats.

• Debugging broken code, especially with matrix blocks. If block is set to a specific section with a variable, always pull data with `variable_name.title` and not `block.title`.

**Link(s) to work**

1. [Entry post date](https://craftcms.stackexchange.com/questions/9890/display-entry-post-date)

-----

### Day 2: Wednesday, 14th August, 2019

**Today's Progress**

• Key learnings: When using includes that have other includes - check to see if the `primaryImage` exists, file relates to the `image macro`, so assign in `entry.primaryImage[0]` - `entry` in this case because it's NOT an index page, so no for loop needed, just an if statement assigned to entry because it'll relate to the entry in this case - `templates > journal  > _entry.twig .`

• Use objects & arrays to set grid classes and transforms to some images from a component, using a dropdown menu in the CMS with narrow, medium, wide parameters that are simple strings, that now coincide with the grids and transforms. Use `{% set sizes = { narrow: ['a6-12', 'halfWidth'] %}` for example, then access it `<div class="grid__item {{ sizes[block.imageWidth.value][0] }}">` like any other array, and ensure to use `.value` to get the string.

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

• Twig includes, content blocks, matrix blocks & conditional logic to render generic components.

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

• Work with helper classes like `mb` or `separated-less` to create space between BEM styled elements by wrapping around them w/o changing semantics. 

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

• Look into importing sprite files with `icomoon`.

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

• Start DataCamp's Data Analyst w/ Python route. Learn about `Data Frames` and dot notation to query rows in a data set with `print(credit_records.head())` to show first 5 results. Environment: `pandas` for data structures and tabular manipulation.

• Query `cols` with `[]` in case they have spaces or special characters like so: `suspect = credit_records['suspect'].` If they don't use dot notation; `price = credit_records.price`. Use `.inspect` to check out your DB.

• Apply logic to Data Frames to query specific data: `credit_records[credit_records.price > 20.00]`. If Column has more than two words, to query it use this notation: `not_poodle = mpr[mpr['Dog Breed'] != "Poodle"]` - notice the use of two square brackets.

• Learn about `matplotlib` to print 2D graphs using the following package: `from matplotlib import pyplot as plt`, then we can do: `plt.plot(x_values, y_values)` and `plt.show`. For example: `plt.plot(ransom.letter, ransom.frequency)` where ransom is the data frame and anything after the `.` is the col name which will match the x & y axis from above arguments. Then use: `plt.show()` to open graph in new window.


**Link(s) to work**

1. [DC](https://datacamp.com)

-----

### Day 23: Tuesday, 3rd December, 2019 

**Today's Progress**

• Use `plt.plot(deshaun.day_of_week, deshaun.hours_worked)` to query cols on deshaun's data frame to solve a 'case'.

• Adding text to plots using: `plt.xlabel("Letter")` & `plt.ylabel("Frequency")` to add horizontal and vertical labels to plot. Finally, use `plt.title("Ransom Note Letters")` to give it a title. To make reading plots easier, use `plt.plot(deshaun.days, deshaun.cases, label="Deshaun")` followed by `plt.legend()` to plot little lines that resemble the labels, that way the reader can easily distinguish what line does what when the graph is plotted.

• Plot arbitrary text on graphs: `plt.text(xcoord, ycoord, "Text")` - e.g. `plt.text(5, 9, "Low Frequency")`. Modify text color with args: `plt.title("Title", fontsize=20, color="green")`.

• Style graph color: `plt.plot(x, y1, color="violet")`, `linewidth=7`, `linestyle="--"`, `marker="x"` - all ways to alter line styles. Also, `plt.style.use('default')` or seaborn, ggplot are "template" examples of plotting styles.

-----

### Day 24: Wednesday, 4th December, 2019 

**Today's Progress**

• Use `print(plt.style.available)` in console to see available 'template' styles, prior to applying `plt.style.use('<insert style here>')`.

• Remember that plotting consists of the following `plt.plot(ransom.letter, ransom.frequency, label="Ransom", linestyle=':', color='gray')` - plotting letters on x axis, frequency on y axis, with labels and linestyle. Then use `plt.show()` to execute.

-----

### Day 25: Thursday, 5th December, 2019 

**Today's Progress**

• Scatter plot: `plt.scatter(df.age, df.height)` - same as `plt.plot` where arg 1 is x axis and arg 2 is y axis. Labeling is also identical: `plt.xlabel('Age (in months)')` & `plt.ylabel('Heightc(in inches)')` followed by `plt.show()`.

• Marker transparency as an arg can be used like so: `alpha=0.1` - `plt.scatter(df.age, df.height, alpha=0.1)` to avoid chaotic graphs when there's an excess of data plotted. Full plot with these edits will look like:
```
plt.scatter(cellphone.x, cellphone.y, color='red', marker='s', alpha=0.1)

plt.ylabel('Latitude')
plt.xlabel('Longitude')

plt.show()
```

• Bar chart plot: `plt.bar(df.precinct, df.pets_abducted, yerr=df.error)`, followed by `plt.ylabel('Pet Abductions')
` where ylabel only needed since xlabel is given. `yerr` is to define errors w/ standard deviation.

• Stacked bar chart plots define two elements in one column. Having the `bottom` arg stacks the second bar on top of the first. E.g. 
```
plt.bar(df.precinct, df.dog, label='Dog')
plt.bar(df.precinct, df.cat, bottom=df.dog, label='Cat')

plt.legend()
plt.show()
```
-----

### Day 26: Friday, 6th December, 2019 

**Today's Progress**

• Finish bars & stacked bars with a refresher exercise on hours vs desk/field work to determine which officer put in most labor and where.Ensure to query the `hours data frame`, with the correct `cols` and `labels`, which then call for `.legend()` & `.show()` to display like so:

```
# Plot the number of hours spent on desk work
plt.bar(hours.officer, hours.desk_work, label='Desk Work')

# Plot the hours spent on field work on top of desk work
plt.bar(hours.officer, hours.field_work, bottom=hours.desk_work, label='Field Work')

# Add a legend
plt.legend()

# Display the plot
plt.show()
```
• Histograms w/ `matplotlib`. Use `plt.hist(gravel.mass) & plt.show()` to plot a histogram. To change the # of bins - `plt.hist(data, bins=nbins)`, eg. `plt.hist(gravel.mass, bins=40)`. To change the range: `plt.hist(data, range=(xmin, xmax))`, eg. `plt.hist(gravel.mass, range=(50, 100))`. To normalize histograms set `sum of bar area=1` using `density=True`- `plt.hist(male_weight, density=True)` & `plt.hist(female_weight, density=True)`.

Note: 

`range` sets the minimum and maximum datapoints that we will include in our histogram.

`bins` sets the number of points in our histogram.

• Recap: Modules: `import pandas as pd` and `import numpy as np` - data frames that store tabular data. `.head()` and `.info()` can be called. Row selection w/ logic: `reports[report.suspect == 'Freddy' ]`. Line plots: `from matplotlib import pyplot as plt`, `plt.plot()` w/ args, labels, legends. Also, used `plt.scatter(), .bar(), .hist()` to solve the case of the missing doggy! :)

**Link(s) to work**

1. [Complete Intro to Data Science in Python](https://www.datacamp.com/statement-of-accomplishment/course/e80ec36b188511b2d2a0b0c749615cf08dc76a5c)

-----

### Day 27: Saturday, 7th December, 2019 

**Today's Progress**

• Recap of Intro to Data Science in python with mobile exercise challenges.

-----

### Day 28: Monday, 9th December, 2019 

**Today's Progress**

• Recap of data visualization library `matplotlib` and remember `import matplotlib.pyplot as plt` to bring it in, and `plt.show()` fn at the end to reveal.

• `print(year[-1])` to access the last element in the years array. 

• Displaying data on a logarithmic scale: `plt.xscale('log')`, on a scatter plot.

• `help(plt.hist)` to view more info in terminal. When plotting a histogram, add bins next to value of `x` - `hist(x, bins=10)`

• `plt.clf()` will just clear the figure - you can still paint another plot onto it. Goes hand in hand with `plt.show()`.

• Add historical data to line plot: if `year = [2000, 2001, 2002, ..., 2019]`, adding more data is easy: `year = [2020] + year`. That reassignment will add next element to array. `plt.xticks & plt.yticks` can be used to match/rename axis labels with arrays. E.g. `plt.yticks([2, 4, 6], ['2B', '4B', '6B'])` will add the 'B's to the elements of that array and match them, to showcase 'billions of years'.


**Link(s) to work**

1. [Python for Data Sci cheat sheet](https://datacamp-community-prod.s3.amazonaws.com/e30fbcd9-f595-4a9f-803d-05ca5bf84612)

-----

### Day 29: Tuesday, 10th December, 2019 

**Today's Progress**

• Continue data visualizations with `numpy`. Below is a recap of `sizing` and using numpy arrays to double up the scale of dots.
```
# Import numpy as np
import numpy as np

# Store pop as a numpy array: np_pop
np_pop = np.array(pop)

# Double np_pop --> Because np_pop is a Numpy array, each array element will be doubled.
np_pop = np_pop * 2

# Update: set s argument to np_pop
plt.scatter(gdp_cap, life_exp, s = np_pop)

# Previous customizations
plt.xscale('log') 
plt.xlabel('GDP per Capita [in USD]')
plt.ylabel('Life Expectancy [in years]')
plt.title('World Development in 2007')
plt.xticks([1000, 10000, 100000],['1k', '10k', '100k'])

# Display the plot
plt.show()
```
• Adding additional customizations to plots is as easy as continuing the arguments. E.g. `plt.scatter(x=gdp_cap, y=life_exp, s=np.array(pop) * 2, c=col, alpha=0.8)` - making it easier to interpret. Adding grid lines: `plt.grid(True)` before `plt.show()`.

• Normal **lists** are long and inconvenient as accessing 'arrays' needs more code. E.g. - 
```
pop=[30, 3, 39]
countries=["afghanistan", "albania", "algeria"]
index_albania= countries.index("albania") = 1 (to grab the index)
pop[index_albania]=3 (to get the same index from pop array)
```
• **Dictionaries** (like objects in JS) have `key:value` pairs that can be accessed with curly braces.
```
world= { "afghanistan: 30, "albania": 3, "algeria": 39 }
world["albania"] = 3 (much quicker and more efficient to use)
```
• python method `dictionary.keys()` reveals all keys in a dictionary (aka object).

•  Keys have to be immutable. Select, Update, Remove is just like objects in JS: `world['sealand']=0.000027` - adds this value to the world dictionary. `world['sealand']=0.000028` updates it. `del(world['sealand'])` deletes it. Lists are better when collection of values, order matters and entire subset is to be selected vs Dictionaries - when lookup table necessary with unique values - faster.

• Accessing dictionaries within dictionaries (objects w/i objects) uses *chaining*. Same as dot notation in JS. `europe['spain']['capital]` - accesses a key within a key to get the value 'madrid'.

• `pandas` - used for high level data manipulation, with multiple data types, built on numpy. Cols resemble variables. Rows resemble observations. Keys act as col labels, values -> data, column by column. `import pandas as pd` `brics = pd.DataFrame(dict)`. DFs have automatic indexes which can be replaced like so: `brics.index=["BR", "RU", "IN"]`.

• Reading from CSV file: `brics= pd.read_csv("path/to/brics.csv", index_col=0)` - removes the automatically placed column.

•  Build dataframe from dictionary(object): `cars = pd.DataFrame(my_dict)`.

-----

### Day 30: Thursday, 12th December, 2019 

**Today's Progress**

• Select column from DataFrame in CSV: `cars['cars_per_cap']` -> Panda Series

• `cars[['cars_per_cap']]` -> Pandas DataFrame

•  Reminder importing: `import pandas as pd` & `cars = pd.read_csv('cars.csv', index_col=0)`

•  Select rows(observation) via indexing: `cars[0:5]`

•  Select rows via `loc` & `iloc`: loc -> label based -> `cars.loc['RU']`. iloc -> integer based -> `cars.iloc[4]`

•  Subdata Frames: `print(cars.loc[['RU', 'MOR'],['country', 'drives_right']])` - where first set of `[]` is `index labels` and second set is `col titles`.

• Select `cols` only with `loc/iloc` - `cars.loc[:, 'country']` & `cars.iloc[:, 1]` (series) & `cars.loc[:,['country']]` & `cars.iloc[:, [1]]` (dataframes)

-----

### Day 31: Saturday, 14th December, 2019 

**Today's Progress**

• Comparisson operators - same as JS

• Numpy operators - querying an array: w/ `logical_and()`, `logical_or()`, `logical_not()`. E.g. `np.logical_and(bmi > 21, bmi < 22)`.

• Conditional operators (same as JS but diff syntax):
```
if condition :
	expression
elif condition :
	expression
else :
	expression
```

-----

### Day 32: Sunday, 15th December, 2019 

**Today's Progress**

• Filtering pandas dataframe. **1. Get column**: To get panda series, select df's column: `brics["area"]` or w/ alternatives: `brics.loc[:, "area"]` & `brics.iloc[:, 2]` would render same result. **2. Compare**: Then: `is_huge = brics["area"] > 8` to print a series of booleans. **3. Subset DF**: Saving result to a variable to later pass into square brackets: `brics[is_huge]` to only print the rows needed.  Alternatively, shorthand: `brics[brics["area"] > 8]`. 

• Use boolean operators for selective results: `brics[np.logical_and(brics["area"] > 8, brics["area"] < 10)]` 

-----

### Day 33: Tuesday, 17th December, 2019 

**Today's Progress**

• Recap of shorthand structure for Pandas Series: `sel = cars[cars['drives_right']]` - create var, store cars dataframe's column results, to later print it. 

• Select observations with `cpc over 500` which is a `boolean series`. Store results in var and pass it into cars data frame to create a subset `many_cars` to render results. 
```
cpc = cars["cars_per_cap"]
many_cars = cpc > 500
car_maniac = cars[many_cars]
print(car_maniac)
```
• Use numpy logical operators with `and` to select elements within a range.
```
cpc = cars['cars_per_cap']
between = np.logical_and(cpc > 100, cpc < 500)
medium = cars[between]
print(medium)
```
• While loop (same as JS) - syntax: 
```
while condition: 
	expression
	
e.g. 
error = 50.0
while error > 1:
	error = error / 4
	print(error)
```
• Adding if/else statements in while loop:
```
offset = -6
while offset != 0:
	print("correcting...")
	if offset  > 0:
		offset = offset - 1
	else:
		offset = offset + 1
	print(offset)
```
-----

### Day 34: Wednesday, 18th December, 2019 

**Today's Progress**

• For loops (similar to JS) but with an index requires `enumerate`. Ensure to always convert indices and variables to strings.
```
for var in seq:
	expression


e.g. (without an index)
fam = [1, 2, 3]
for height in fam:
	print(height)
	
e.g. (with index)
for index, height in enumerate(fam):
	print("index " + str(index) + " :" + str(height))

for x, y in house:
    print("the " + str(x) + " is " + str(y) + " sqm")
    
```

-----

### Day 34: Thursday, 19th December, 2019 

**Today's Progress**

• Looping through data structures as dictionaries (objects) requires a key/value pair. By using method `.items()` on object, errors are prevented.

```
world = {
"cyprus": "23.2",
"greece": "33.1"
}

for k, v in world.items() :
	print(k + "---" + str(v))

```
• Iterate over numpy array (Data Sci equivalent to python lists) use the following function: `for value in np.nditer(my_array)`. See iteration of 1D and 2D numpy array.
```
import numpy as np
for x in np_height :
	print(str(x) + " inches")
for x in np.nditer(np.baseball) :
	print(x)
```
-----

### Day 35: Monday, 23rd December, 2019 

**Today's Progress**

• Using pandas to loop through data structures with `for loops` and the `apply function`.
```
for lab, row in brics.iterrows() :
	print(lab + ": " + row["capital"])
```
• Take each label and each row in a dataframe, iterate over the rows and find the number of characters per row, per country. Then assign these values to the column name_length using loc.
```
for lab, row in brics.iterrows() :
	brics.loc[lab, "name_length"] = len(row["country"])
print(brics)
```
• Shorthand, apply function. `brics["name_length"] = brics["country"].apply(len)`. Where `brics` is the dataframe, country is the `column title` and `len` is the function containing the length of characters, all assigned to a new column called `name_length`.

• Raw data is generated by `iterrows()` -> Pandas Series but not convenient. Select data more easily from Pandas Series w/ `[]`. -> 
```
for lab, row in brics.iterrows() :
	print(row['country'])
```

• Example of adding a new column called COUNTRY, w/ uppercase country names inserted under that column:
```
import pandas as pd
cars = pd.read_csv('cars.csv', index_col=0)
for lab, row in cars.iterrows() :
	cars.loc[lab, "COUNTRY"] = row["country"].upper()
print(cars)
```

-----

### Day 36: Friday, 27th December, 2019

**Today's Progress**

• Random Generators. `rand()` generates a random float b/w 0 and 1.
```
import numpy as np
np.random.rand()
0.95382264
```

• Pseudo random numbers start from a *seed*. `seed()` sets the random seed, so that results are reproducible between simulation. `np.random.seed(123)` e.g. -> 0.6987

• Coin toss example
```
import numpy as np
np.random.seed(123)
coin = np.random.randint(0,2)
print(coin) # 0
if coin == 0:
	print("heads")
else:
	print("tails")
```

• Heads or tails - Random Walk
```
import numpy as np
np.random.seed(123)
tails = [0]
for x in range(10) :
	coin = np.random.randint(0,2)
	tails.append(tails[x] + coin)
print(tails)
```

-----

### Day 36: Friday, 27th December, 2019

**Today's Progress**

• Random Generators. `rand()` generates a random float b/w 0 and 1.
```
import numpy as np
np.random.rand()
0.95382264
```

• Pseudo random numbers start from a *seed*. `seed()` sets the random seed, so that results are reproducible between simulation. `np.random.seed(123)` e.g. -> 0.6987

• Coin toss example
```
import numpy as np
np.random.seed(123)
coin = np.random.randint(0,2)
print(coin) # 0
if coin == 0:
	print("heads")
else:
	print("tails")
```

• Heads or tails - Random Walk
```
import numpy as np
np.random.seed(123)
tails = [0]
for x in range(10) :
	coin = np.random.randint(0,2)
	tails.append(tails[x] + coin)
print(tails)
```
• use `max()` to prevent steps from going below zero. `step = max(0, step - 1)`.

• Histogram, 10.000 runs
```
import numpy as np
import matplotlib.pyplot as plt
np.random.seed(123)
final_tails = []
for x in range(10000) :
	tails = [0]
	for x in range(10) :
		coin = np.random.randint(0,2)
		tails.append(tails[x] + coin)
	final_tails.append(tails[-1])
plt.hist(final_tails, bins = 10)
plt.show()
```
-----

### Day 37: Monday, 2nd January, 2020

**Today's Progress**

• User defined functions. How to define a function
```
def square() :
	new_value = 4 ** 2
	print(new_value)
square()
```
• Add function parameters. Inside the function, parameters. When function is called, arguments. Same as JS.
```
def square(value) :
	new_value = value ** 2
	print(new_value)
square(4)
16
```
• Return values from functions
```
def square(value) :
	new_value = value ** 2
	return new_value
num = square(4)
print(num)
16
```
• `Docstrings` are descriptions placed under the function header between triple quotes ` '''...'''`

-----

### Day 38: Tuesday, 7th January, 2020

**Today's Progress**

• Multiple parameters to return values.
```
def raise_to_power(v1, v2):
	'''Raise v1 to the power of v2'''
	new_value = v1 ** v2
	return new_value
```
• Tuples are immutable. Thus, unmodifiable. Tuples used to display two outcomes with return. Always in brackets.
```
def raise_both(v1, v2):
	'''Raise v1 to the power of v2 and vice versa'''
	new_v1 = v1 ** v2
	new_v2 = v2 ** v1
	new_tuple = (new_v1, new_v2)
	return new_tuple
result = raise_both(2, 3)
print(result)
(8,9)
```
• Unpacking `nums` into `num1`, `num2`, `num3`: `num1, num2, num3 = nums` & constructing even_nums **tuple**: `even_nums = (2, num2, num3)` where the first value in the tuple is replaced with `2`. The other two values will be derived from the preloaded exercise. Unpacking variables assigned to arguments e.g. `yell1, yell2 = shout_all('congratulations','you')`.

• Putting it all together:

```
# Import pandas
import pandas as pd

# Import Twitter data as DataFrame: df
df = pd.read_csv('tweets.csv')

# Initialize an empty dictionary: langs_count
langs_count = {}

# Extract column from DataFrame: col
col = df['lang']

# Iterate over lang column in DataFrame
for entry in df['lang']:

    # If the language is in langs_count, add 1 
    if entry in langs_count.keys():
       langs_count[entry] += 1 
    # Else add the language to langs_count, set the value to 1
    else:
        langs_count[entry] = 1

# Print the populated dictionary
print(langs_count)
```
-----

### Day 39: Wednesday, 8th January, 2020

**Today's Progress**

• Wrapping it all up. 

```
# Define count_entries()
def count_entries(df, col_name):
    """Return a dictionary with counts of 
    occurrences as value for each key."""

    # Initialize an empty dictionary: langs_count
    langs_count = {}
    
    # Extract column from DataFrame: col
    col = df[col_name]
    
    # Iterate over lang column in DataFrame
    for entry in col:

        # If the language is in langs_count, add 1
        if entry in langs_count.keys():
            langs_count[entry] += 1
        # Else add the language to langs_count, set the value to 1
        else:
            langs_count[entry] = 1

    # Return the langs_count dictionary
    return langs_count

# Call count_entries(): result
result = count_entries(tweets_df, 'lang')

# Print the result
print(result)

{'en': 97, 'et': 1, 'und': 2}
```
-----

### Day 40: Thursday, 9th January, 2020

**Today's Progress**

• Scope and user defined functions. Not all objects are accessible everywhere in script. Scope consists of `global`, `local` and `built-in` scopes where python looks for local first, then global then built-in. If the keyword `global` is used to access global name, then that will replace the local scope and thus the value of the local call() will not work. E.g. `square(3)` below won't print 9, but 100.
```
new_val = 10
def square(value):
	'''Return square number'''
	global new_val
	new_val = new_val ** 2
	return new_val
square(3)

100
```
• Altering using `global`. Keyword `nonlocal` can also be used to alter scope of inner functions rather than outer.
```
# Create a string: team
team = "teen titans"

# Define change_team()
def change_team():
    """Change the value of the global variable team."""

    # Use team in global scope
    global team

    # Change the value of team in global: team
    team = "justice league"
# Print team
print(team)

# Call change_team()
change_team()

# Print team
print(team)

teen titans
justice league
```
• `import builtins` gives many built in methods like sum, minus to use.

• Nested functions example. Similar to a `closure`
```
def mod2plus5(x1, x2, x3)
	'''Returns remainder plus five of three values'''
	def inner(x):
		'''Returns remainder plus five of a value'''
		return x % 2 + 5
	return(inner(x1), inner(x2), inner(x3))
	
print(mod2plus5(1, 2, 3))

(6, 5, 6)
	
```
-----

### Day 41: Friday, 10th January, 2020

**Today's Progress**

• Nested functions. Closures. Call the word hello a twice then thrice, with a closure.
```
# Define echo
def echo(n):
    """Return the inner_echo function."""

    # Define inner_echo
    def inner_echo(word1):
        """Concatenate n copies of word1."""
        echo_word = word1 * n
        return echo_word

    # Return inner_echo
    return inner_echo

# Call echo: twice
twice = echo(2)

# Call echo: thrice
thrice = echo(3)

# Call twice() and thrice() then print
print(twice('hello'), thrice('hello'))
```
• Using `nonlocal` keyword to access enclosing scope.
```
# Define echo_shout()
def echo_shout(word):
    """Change the value of a nonlocal variable"""
    
    # Concatenate word with itself: echo_word
    echo_word = word * 2
    
    # Print echo_word
    print(echo_word)
    
    # Define inner function shout()
    def shout():
        """Alter a variable in the enclosing scope"""    
        # Use echo_word in nonlocal scope
        nonlocal echo_word
        
        # Change echo_word to echo_word concatenated with '!!!'
        echo_word = (echo_word + "!!!")
    
    # Call function shout()
    shout()
    
    # Print echo_word
    print(echo_word)

# Call function echo_shout() with argument 'hello'
echo_shout('hello')
```
-----

### Day 43: Tuesday, 14th January, 2020

**Today's Progress**

• Default and flexible arguments. E.g. `Default`
```
def power(num, pow=1):
	'''Raise num to power of pow'''
	new_val = num ** pow
	return new_val
	power(9,2)
	81
	power(9)
	9, 1 # uses default value 1 if 2nd param not assigned
```
• E.g. `flexible` using `*args` in case number of args is unknown, can put many and `*args` keyword will handle
```
def all_args(*args):
	'''Sum all values in *args together'''
	# initialize sum
	sum_all = 0
	# Accumulate sum
	for num in args:
		sum_all += num
	return sum_all
```

• E.g. `flexible` using `**kwargs` for key:value pairs which utilizes a dictionary
```
def print_all(**kwargs)
	'''Print out key:val pairs in **kwargs'''
	# Print out k:v pairs
	for key, value in kwargs.items():
	print(key + \" : \" + value)
print_all(name="dumbledore", job="headmaster")	
```
• Setting `default` arguments, using `.upper()` and using `booleans` as predefined values to concatenate accordingly.
```
# Define shout_echo
def shout_echo(word1, echo=1, intense=False):
    """Concatenate echo copies of word1 and three
    exclamation marks at the end of the string."""

    # Concatenate echo copies of word1 using *: echo_word
    echo_word = word1 * echo

    # Make echo_word uppercase if intense is True
    if intense is True:
        # Make uppercase and concatenate '!!!'
        echo_word_new = echo_word.upper() + '!!!'
    else:
        # Concatenate '!!!' to echo_word
        echo_word_new = echo_word + '!!!'

    # Return echo_word_new
    return echo_word_new

# Call shout_echo() with "Hey", echo=5 and intense=True: with_big_echo
with_big_echo = shout_echo("Hey", echo=5, intense=True)

# Call shout_echo() with "Hey" and intense=True: big_no_echo
big_no_echo = shout_echo("Hey", intense=True)

# Print values
print(with_big_echo)
print(big_no_echo)
HEYHEYHEYHEYHEY!!!
Hey!!!
```
-----

### Day 44: Wednesday, 15th January, 2020

**Today's Progress**

• Functions with variable length arguments `(*args)`. Remember: `args` are `tuples` - like `lists` but immutable. E.g.
```
# Define gibberish
def gibberish(*args):
    """Concatenate strings in *args together."""

    # Initialize an empty string: hodgepodge
    hodgepodge = ""

    # Concatenate the strings in args
    for word in args:
        hodgepodge += word

    # Return hodgepodge
    return hodgepodge

# Call gibberish() with one string: one_word
one_word = gibberish("luke")

# Call gibberish() with five strings: many_words
many_words = gibberish("luke", "leia", "han", "obi", "darth")

# Print one_word and many_words
print(one_word)
print(many_words)

luke
lukeleiahanobidarth
```
• Developing a function that counts how many tweets are in certain languages using default argument assignments like `col_name='lang` for the column.
```
# Define count_entries()
def count_entries(df, col_name='lang'):
    """Return a dictionary with counts of
    occurrences as value for each key."""

    # Initialize an empty dictionary: cols_count
    cols_count = {}

    # Extract column from DataFrame: col
    col = df[col_name]
    
    # Iterate over the column in DataFrame
    for entry in col:

        # If entry is in cols_count, add 1
        if entry in cols_count.keys():
            cols_count[entry] += 1

        # Else add the entry to cols_count, set the value to 1
        else:
            cols_count[entry] = 1

    # Return the cols_count dictionary
    return cols_count

# Call count_entries(): result1
result1 = count_entries(tweets_df, 'lang')

# Call count_entries(): result2
result2 = count_entries(tweets_df, col_name='source')

# Print result1 and result2
print(result1)
print(result2)
{'en': 97, 'et': 1, 'und': 2}
{'<a href="http://twitter.com" rel="nofollow">Twitter Web Client</a>': 24, '<a href="http://www.facebook.com/twitter" rel="nofollow">Facebook</a>': 1, ..... }

```
• Developing a function that counts how many tweets are in certain languages using `*args` for flexible arguments, so any column names can be passed as arguments. Renders same result as example above.
```
  # Define count_entries()
def count_entries(df, *args):
    """Return a dictionary with counts of
    occurrences as value for each key."""
    
    #Initialize an empty dictionary: cols_count
    cols_count = {}
    
    # Iterate over column names in args
    for col_name in args:
    
        # Extract column from DataFrame: col
        col = df[col_name]
    
        # Iterate over the column in DataFrame
        for entry in col:
    
            # If entry is in cols_count, add 1
            if entry in cols_count.keys():
                cols_count[entry] += 1
    
            # Else add the entry to cols_count, set the value to 1
            else:
                cols_count[entry] = 1

    # Return the cols_count dictionary
    return cols_count

# Call count_entries(): result1
result1 = count_entries(tweets_df, 'lang')

# Call count_entries(): result2
result2 = count_entries(tweets_df, 'lang', 'source')

# Print result1 and result2
print(result1)
print(result2)
```
• `lambda` functions - quicker way to write functions w/o `def`. E.g.
```
raise_to_power = lambda x,y: x ** y
raise_to_power(2,3)
8
```
• Anonymous functions with `map` using `lambda`. Map takes 2 arguments. The function and the sequence -> `map(func, seq)` E.g.
```
nums = [48, 6, 9, 21, 1]
square_all = map(lambda num: num ** 2, nums)
print(list(square_all))
[2304, 36, 81, 441, 1]
```
-----

### Day 45: Thursday, 16th January, 2020

**Today's Progress**

• Use `filter()` to filter out elements from a list that doesn't satisfy criteria. Remember that `lambda` functions take a function & sequence as args. E.g.

```
# Create a list of strings: fellowship
fellowship = ['frodo', 'samwise', 'merry', 'pippin', 'aragorn', 'boromir', 'legolas', 'gimli', 'gandalf']

# Use filter() to apply a lambda function over fellowship: result
result = filter(lambda member: len(member) > 6 , fellowship)

# Convert result to a list: result_list
result_list = list(result)

# Print result_list
print(result_list)
['samwise', 'aragorn', 'boromir', 'legolas', 'gandalf']
```
• `reduce()` function concatenates strings together. To use first: `from functools import reduce`. E.g.
```
# Import reduce from functools
from functools import reduce 

# Create a list of strings: stark
stark = ['robb', 'sansa', 'arya', 'brandon', 'rickon']

# Use reduce() to apply a lambda function over stark: result
result = reduce(lambda item1, item2: item1 + item2, stark)

# Print the result
print(result)
```
• Error handling. `Exceptions` caught during execution with `try/except`.
```
def sqrt(x):
	try:
		return x ** 0.5
	except TypeError:
		print('x must be int or float')
sqrt(4)
2.0
```
• `raise` - don't print/work if condition not met. E.g.
```
def sqrt(x):
	'''Returns sqrt of a num'''
	if x < 0
		raise ValueError('x must be non-negative')
	try: 
		return x ** 0.5
	except TypeError: 
	print('x must be int or float')
```
-----

### Day 46: Friday, 17th January, 2020

**Today's Progress**

• A `try/except` example, resulting in `except` as the argument is not an integer.
```
# Define shout_echo
def shout_echo(word1, echo=1):
    """Concatenate echo copies of word1 and three
    exclamation marks at the end of the string."""

    # Initialize empty strings: echo_word, shout_words
    echo_word = ""
    shout_words = ""
    

    # Add exception handling with try-except
    try:
        # Concatenate echo copies of word1 using *: echo_word
        echo_word = word1 * echo

        # Concatenate '!!!' to echo_word: shout_words
        shout_words = echo_word + '!!!'
    except:
        # Print error message
        print("word1 must be a string and echo must be an integer.")

    # Return shout_words
    return shout_words

# Call shout_echo
shout_echo("particle", echo="accelerator")
```
• A `raise` example resulting in the error message when the value of `echo=-1`. E.g.
```
# Define shout_echo
def shout_echo(word1, echo=1):
    """Concatenate echo copies of word1 and three
    exclamation marks at the end of the string."""

    # Raise an error with raise
    if echo < 0:
        raise ValueError('echo must be greater than or equal to 0')

    # Concatenate echo copies of word1 using *: echo_word
    echo_word = word1 * echo

    # Concatenate '!!!' to echo_word: shout_word
    shout_word = echo_word + '!!!'

    # Return shout_word
    return shout_word

# Call shout_echo
shout_echo("particle", echo=3)
```
• Using a lambda function to filter out tweets that contain 'RT' as first two characters. Create a list and print the retweets.
```
# Select retweets from the Twitter DataFrame: result
result = filter(lambda x: x[0:2] == 'RT', tweets_df['text'])

# Create list from filter object result: res_list
res_list = list(result)

# Print all retweets in res_list
for tweet in res_list:
    print(tweet)
    
RT @BIackPplTweets: Young Donald trump meets his neighbor  https://t.co/RFlu17Z1eE
RT @trumpresearch: @WaitingInBagdad @thehill Trump supporters have selective amnisia.
RT @HouseCracka: 29,000+ PEOPLE WATCHING TRUMP LIVE ON ONE STREAM!!!
```
• Using `raise ValueError` in the case that the user provides a column name that isn't in the DataFrame. 
```
# Define count_entries()
def count_entries(df, col_name='lang'):
    """Return a dictionary with counts of
    occurrences as value for each key."""
    
    # Raise a ValueError if col_name is NOT in DataFrame
    if col_name not in df.columns:
        raise ValueError('The DataFrame does not have a ' + col_name + ' column.')

    # Initialize an empty dictionary: cols_count
    cols_count = {}
    
    # Extract column from DataFrame: col
    col = df[col_name]
    
    # Iterate over the column in DataFrame
    for entry in col:

        # If entry is in cols_count, add 1
        if entry in cols_count.keys():
            cols_count[entry] += 1
            # Else add the entry to cols_count, set the value to 1
        else:
            cols_count[entry] = 1
        
        # Return the cols_count dictionary
    return cols_count

# Call count_entries(): result1
result1 = count_entries(tweets_df, 'lang')

# Print result1
print(result1)
```
• Start Intro to SQL module. `row = record`. `col = field`. `Query` = request data from DB. 
```
SELECT name FROM people; # name = column, people = table.

SELECT *    # selects all cols from people table and displays only 10.
FROM people
LIMIT 10;

SELECT DISTINCT role # selects unique mentions of role in roles table.
FROM roles;

SELECT COUNT(*) # selects entire reviews table and gives count of rows
FROM reviews;

SELECT COUNT(DISTINCT birthdate)  # selects unique values from birthdate column in people table and displays count.
FROM people; 
```
• SQL filtering w/ numeric values. Remember `<>` means `not equal` by SQL standards. Also PostgreSQL uses single quotes.
```
SELECT title
FROM films
WHERE title = 'Metropolis';

SELECT title
FROM films
WHERE release_year > 2000;

SELECT COUNT(title)
FROM films
WHERE release_year < 2000;
```

• SQL filtering w/ text values. Date format in ISO uses `('YYYY-MM-DD')`.
```
SELECT *
FROM films
WHERE language = 'French';

SELECT name, birthdate
FROM people
WHERE birthdate = ('1974-11-11');

SELECT *
FROM films
WHERE language = 'Spanish'
AND release_year > 2000
AND release_year < 2010;	# each AND query must be re-written per condition needed
```
 
-----

### Day 47: Monday, 20th January, 2020

**Today's Progress**

• Using the `OR` selector in SQL. Use parentheses when using it with `AND` due to SQL's precedence detection.
```
SELECT title 
FROM films
WHERE release_year = 1994
OR release_year = 2000;
```
```
SELECT title
FROM films
WHERE (release_year = 1994 OR release_year = 1995)
AND (certification = 'PG' OR certification = 'R');
```
```
SELECT title, release_year
FROM films
WHERE release_year >= 1990
AND release_year < 2000
AND (language = 'Spanish' OR language = 'French')
AND gross >= 2000000;
```
• Using the `BETWEEN` selector alongside the others learned.
```
SELECT title
FROM films
WHERE release_year BETWEEN 1994 AND 2000;

SELECT name
FROM kids
WHERE age BETWEEN 2 AND 12
AND nationality = 'USA';

SELECT title, release_year
FROM films
WHERE release_year BETWEEN 1990 AND 2000
AND budget > 100000000
AND (language = 'Spanish' OR language = 'French')
```
• Using the `IN` selector alongside the others learned.
```
SELECT name
FROM kids
WHERE age IN (2, 4, 6, 8, 10);

# instead of 
WHERE age = 2
OR age = 4
OR age = 6 ...etc

SELECT title, certification
FROM films
WHERE certification IN ('NC-17', 'R');
```
• Using the `NULL & IS NULL` selector alongside the others learned. `NULL` is a missing/unknown value. To count the missing birthdates in `people` table w/ `IS NULL`.
```
SELECT COUNT(*)
FROM people
WHERE birthdate IS NULL;
```
• Filter missing values to get filled results w/ `IS NOT NULL`
```
SELECT name
FROM people
WHERE birthdate IS NOT NULL;

SELECT COUNT(*)
FROM films
WHERE language IS NULL; 
```
-----

### Day 48: Tuesday, 21st January, 2020

**Today's Progress**

• `LIKE / NOT LIKE` keywords in SQL can be used with 'wildcards' to match parts of a string. The `%` wildcard matches 0, 1+ characters, whereas the `_` matches a single character. E.g.
```
SELECT name
FROM companies
WHERE name LIKE 'Data%';

SELECT name
FROM companies
WHERE name LIKE 'DataC_mp'

SELECT name
FROM companies
WHERE name NOT LIKE '_r%';	# Won't include names with 'r' as 2nd character.
```
• Aggregate functions using predetermined keywords, also with `WHERE`.
```
SELECT AVG(budget)
FROM films;

SELECT MAX(budget)	# Also use MIN
FROM films;

SELECT SUM(budget)
FROM films;

SELECT SUM(budget)
FROM films
WHERE release_year >= 2000;

SELECT MAX(gross)
FROM films
WHERE release_year BETWEEN 2000 AND 2002;
```
• Arithmetic
```
SELECT ( 4 * 3 );

SELECT ( 4 / 3); # 1. Specify float for precision

SELECT ( 4.0 / 3.0 ); # 1.333
```

• Aliasing w/ keyword `AS`
```
SELECT MAX(budget) AS max_budget
       MAX(duration) AS max_duration
FROM films;

SELECT AVG(duration) / 60.0 AS avg_duration_hours
FROM films;

SELECT title, gross - budget AS net_profit
FROM films;

SELECT title, duration / 60.0 AS duration_hours
FROM films;
```
-----

### Day 49: Wednesday, 22nd January, 2020

**Today's Progress**

• Get % of dead people, alias result. Remember to use 100.0 decimal to render correct calculation as per SQL standards.
```
SELECT COUNT(deathdate) * 100.0 / COUNT(*) AS percentage_dead
FROM people;
```
• Use MAX/MIN
```
SELECT MAX(release_year) - MIN(release_year) AS difference
FROM films;
```
• Using parentheses to enclose calculations with MIN/MAX 
```
SELECT (MAX(release_year) - MIN(release_year) / 10.0 AS number_of_decades
FROM films;
```
• `ORDER BY` - sorts by asc/dec order. Default ascending. Use keyword `DESC` otherwise. Some examples that fuse learnings all together:
```
SELECT title
FROM films
ORDER BY release_year DESC;
```
```
SELECT title
FROM films
WHERE release_year IN (2000, 2012)
ORDER BY release_year;
```
```
SELECT *
FROM films
WHERE release_year <> 2015
ORDER by duration;
```
```
SELECT title, gross
FROM films
WHERE title like 'M%'
ORDER BY title;
```
```
SELECT imdb_score, film_id
FROM reviews
ORDER BY imdb_score DESC;
```
```
SELECT name, birthdate
FROM people
ORDER BY name, birthdate 	# multiple col sorting - will sort by name A-Z and birthdate - oldest to newest. Col order matters!
```
• `GROUP BY`
```
SELECT sex, count(*)
FROM employees
GROUP BY sex;	# works well with COUNT + MAX/MIN
```
```
SELECT sex, count(*)
FROM employees
GROUP BY sex
ORDER BY count DESC;
```
```
SELECT imdb_score, count(*)
FROM reviews
GROUP BY imdb_score;
```
-----

### Day 50: Thursday, 23rd January, 2020

**Today's Progress**

• `HAVING` clause. Used because aggregate functions cannot be used in `WHERE` clauses.
```
SELECT release_year
FROM films
GROUP BY release_year
HAVING COUNT(title) > 10;
```

• Big query containing everything learned so far
```
SELECT release_year, AVG(budget) AS avg_budget, AVG(gross) AS avg_gross
FROM films
WHERE release_year > 1990 
GROUP BY release_year
HAVING AVG(budget) > 60000000
ORDER BY AVG(gross) DESC;
```
```
-- select country, average budget, average gross
SELECT country, AVG(budget) AS avg_budget, AVG(gross) AS avg_gross
-- from the films table
FROM films
-- group by country 
GROUP BY country
-- where the country has more than 10 titles
HAVING COUNT(title) > 10
-- order by country
ORDER BY country
-- limit to only show 5 results
LIMIT 5
```
• Introducing `JOIN` for multiple table joins to grab data from two tables.
```
SELECT title, imdb_score
FROM films
JOIN reviews
ON films.id = reviews.film_id
WHERE title = 'To Kill a Mockingbird';
```
-----

### Day 51: Friday, 24th January, 2020

**Today's Progress**

• `INNER JOIN` - matches IDs from keys in tables.

```
SELECT * 
FROM left_table
INNER JOIN right_table
ON left_table.id = right_table.id
```
```
SELECT cities.name AS city, countries.name AS country, countries.region
FROM cities
INNER JOIN countries
ON cities.country_code = countries.code;
```
• Tables can be aliased too. Example above aliased:
```
SELECT c1.name AS city, c2.name AS country, countries.region
FROM cities AS c1
INNER JOIN countries AS c2
ON c1.country_code = c2.code;
```
-----

### Day 52: Monday, 27th January, 2020

**Today's Progress**

• Inner joins continued with double joins to prevent scattering of data.
```
SELECT c.code, name, region, e.year, fertility_rate, unemployment_rate
  FROM countries AS c
  INNER JOIN populations AS p
    ON c.code = p.country_code
  INNER JOIN economies AS e
    ON c.code = e.code AND p.year = e.year;
```

• `USING` clause to shorten query typing when common field names are present
```
SELECT * 
FROM countries
INNER JOIN economies
ON countries.code = economies.code;
```
```
SELECT *
FROM countries
INNER JOIN economies
USING(code);
```
-----

### Day 53: Tuesday, 28th January, 2020

**Today's Progress**

• Self joins - join tables to themselves
```
SELECT p1.country AS country1, p2.country AS country2, p1.continent
FROM prime_ministers AS p1
INNER JOIN prime_ministers AS p2
ON p1.continent = p2.continent AND p1.country <> p2.country
LIMIT 14;
```
• `CASE/WHEN` for multiple if/else statements
```
SELECT name, continent, indep_year
CASE WHEN indep_year < 1900 THEN 'before 1900'
     WHEN indep_year <= 1930 THEN 'between 1900 and 1930'
     ELSE 'after 1930' END
     AS indep_year_group
FROM states
ORDER BY indep_year_group;
```
```
SELECT p1.country_code,
       p1.size AS size2010, 
       p2.size AS size2015,
       -- 1. calculate growth_perc
       ((p2.size - p1.size)/p1.size * 100.0) AS growth_perc
-- 2. From populations (alias as p1)
FROM populations AS p1
  -- 3. Join to itself (alias as p2)
  INNER JOIN populations AS p2
    -- 4. Match on country code
    ON p1.country_code = p2.country_code
        -- 5. and year (with calculation)
        AND p1.year = p2.year - 5;
```
• Use of `INTO` clause to create new table from existing one with new column group. Use new col `popsize_group` to select other elements. 
```
SELECT country_code, size,
  CASE WHEN size > 50000000
            THEN 'large'
       WHEN size > 1000000
            THEN 'medium'
       ELSE 'small' END
       AS popsize_group
INTO pop_plus       
FROM populations
WHERE year = 2015;

-- 5. Select fields
SELECT name, continent, geosize_group, popsize_group
-- 1. From countries_plus (alias as c)
FROM countries_plus AS c
  -- 2. Join to pop_plus (alias as p)
INNER JOIN pop_plus AS p
    -- 3. Match on country code
ON c.code = p.country_code
-- 4. Order the table    
ORDER BY geosize_group;
```
-----

### Day 54: Wednesday, 29th January, 2020

**Today's Progress**

• Outer Joins consist of `LEFT & RIGHT` joins, which behave similar to `INNER JOINS`. Though when paired, if IDs on LEFT/RIGHT tables don't match, then the table records(rows) will be blank.
```
SELECT c1.name AS city, code, c2.name AS country, region, city_proper_prop
FROM cities AS c1
LEFT JOIN countries AS c2
ON c1.country_code = c2.code
ORDER BY code DESC;
```
```
SELECT region, AVG(gdp_percapita) AS avg_gdp
FROM countries AS c
  LEFT JOIN economies AS e
    ON c.code = e.code
WHERE year = 2010
GROUP BY region
ORDER BY avg_gdp DESC;
```
•  `FULL JOIN` - joins both tables and displays each side, showing empty cells for non-ID related cells. E.g.
```
SELECT left_table.id AS L_id, right_table.id AS R_id, left_table.val AS L_val, right_table.val AS R_val
FROM left_table
FULL JOIN right_table
USING(id);
```
```
SELECT p1.country AS pm_co, p2.country AS pres_co, prime_minister, president
FROM prime_ministers AS p1
FULL JOIN presidents AS p2
ON p1.country = p2.country;
```
```
SELECT c1.name AS country, region, l.name AS language, basic_unit, frac_unit
FROM countries AS c1
  FULL JOIN languages AS l
    USING (code)
  FULL JOIN currencies AS c2
    USING (code)
WHERE region LIKE 'M%esia';
```
```
SELECT c.name AS country, region, life_expectancy AS life_exp
FROM countries AS c
  LEFT JOIN populations AS p
    ON c.code = p.country_code
WHERE year = 2010
ORDER BY life_exp
LIMIT 5;
```
• `CROSS JOIN` joins the IDs of left table to every possible combination on a table to that of the right side.

-----

### Day 55: Thursday, 30th January, 2020

**Today's Progress**

• `UNION` (theory) clause to fuse together two tables, without including duplicates
```
SELECT *
FROM economies2010
	UNION
SELECT *
  FROM economies2015
ORDER BY code, year;
```
• `UNION ALL` clause to fuse together economies and populations tables, with duplicate results, ordered by code, year.
```
SELECT code, year
  FROM economies
	UNION ALL
SELECT country_code, year
  FROM populations
ORDER BY code, year;
```
-----

### Day 56: Monday, 3rd February, 2020

**Today's Progress**

• `INTERSECT` combines common fields in a query and only shows those. 
```
SELECT code, year
FROM economies
INTERSECT
SELECT country_code, year
FROM populations
ORDER BY code, year; 
```
• `EXCEPT` - shows only records that are in 1 table but not the other.
```
SELECT city.name
FROM cities AS city
EXCEPT
SELECT country.capital
FROM countries AS country
ORDER BY name;
```
-----

### Day 57: Tuesday, 4th February, 2020

**Today's Progress**

• Semi joins - writing sub-queries within queries to provide more refined results. First, select names from languages table, where the code from countries(the other table) identifies the region as 'Middle East'. 
```
-- Select distinct fields
SELECT DISTINCT name
  -- From languages
  FROM languages
-- Where in statement
WHERE code IN
  -- Subquery
  (SELECT code 
    FROM countries
    WHERE region='Middle East')
-- Order by name
ORDER BY name;
```
-----

### Day 58: Wednesday, 5th February, 2020

**Today's Progress**

• Diagnosing errors with antijoins
```
SELECT code, name
  FROM countries
  WHERE continent = 'Oceania'
  	AND code NOT IN
  	(SELECT code 
  	FROM currencies);
```
• Using sub-queries and mutiple theory clauses with UNION and EXCEPT to query three tables to identify the country codes that are included in either `economies` or `currencies` but not in `populations`.
```
-- Select the city name
SELECT c1.name
  -- Alias the table where city name resides
  FROM cities AS c1
  -- Choose only records matching the result of multiple set theory clauses
  WHERE country_code IN
(
    -- Select appropriate field from economies AS e
    SELECT e.code
    FROM economies AS e
    -- Get all additional (unique) values of the field from currencies AS c2  
    UNION
    SELECT c2.code
    FROM currencies AS c2
    -- Exclude those appearing in populations AS p
    EXCEPT
    SELECT p.country_code
    FROM populations AS p
);
```
-----

### Day 59: Thursday, 6th February, 2020

**Today's Progress**

•  Subqueries inside WHERE & SELECT.
```
SELECT name, fert_rate
FROM states
WHERE continent = 'Asia'
AND fert_rate <
(SELECT AVG(fert_rate)
FROM states);
```
```
SELECT DISTINCT continent,
(SELECT COUNT(*)
FROM states
WHERE prime_ministers.continent = state.continent) AS countries_num
FROM prime_ministers
```
• Select all fields from populations with records corresponding to larger than 1.15 times the average in 2015 with a subquery.
```
SELECT *
FROM populations
WHERE life_expectancy > 1.15 *
    (SELECT AVG(life_expectancy)
    FROM populations
    WHERE year = 2015)
    AND year = 2015;
```
•  Get the urban area population for only capital cities.
```
SELECT name, country_code, urbanarea_pop
  FROM cities
WHERE cities.name IN
  (SELECT countries.capital
   FROM countries)
ORDER BY urbanarea_pop DESC;
```
-----

### Day 60: Friday, 7th February, 2020

**Today's Progress**

•  Using subqueries to do render same result as INNER JOIN
```
SELECT countries.name AS country, COUNT(*) AS cities_num
  FROM cities
    INNER JOIN countries
    ON countries.code = cities.country_code
GROUP BY country
ORDER BY cities_num DESC, country
LIMIT 9;
```
Same result as:
```
SELECT countries.name AS country,
(SELECT COUNT(*)
FROM cities
WHERE countries.code = cities.country_code) AS cities_num
FROM countries
ORDER BY cities_num DESC, country
LIMIT 9;
```
•  FROM clause subqueries
```
SELECT DISTINCT monarchs.continent, subquery.mex_perc
FROM monarchs,
(SELECT continent, MAX(women_parli_perc) AS max_perc
FROM states
GROUP BY continent) AS subquery
WHERE monarchs.continent = subquery.continent
ORDER BY continent;
```
-----

### Day 61: Saturday, 8th February, 2020

**Today's Progress**

•  FROM clause subqueries continued. Create a subquery after FROM statement, selecting the code and the count of the names of the countries aliased as lang_num from the languages table. Group them by code and name and alias as subquery. Ensure that the countries.code is matched with the subquery.code of the countries, thus creating a join. On outer SELECT, local_name of country and the number of languages from the subquery.
```
-- Select fields
SELECT local_name, subquery.lang_num
  -- From countries
  FROM countries,
  	-- Subquery (alias as subquery)
(SELECT code, COUNT(name) AS lang_num
    FROM languages
    GROUP BY code) as subquery
  -- Where codes match
  WHERE countries.code = subquery.code
-- Order by descending number of languages
ORDER BY lang_num DESC;
```
•  Advanced subquery.
```
SELECT name, continent, inflation_rate
FROM countries
INNER JOIN economies
ON countries.code = economies.code
WHERE year = 2015
    AND inflation_rate IN (
        SELECT MAX(inflation_rate) AS max_inf
        FROM (
             SELECT name, continent, inflation_rate
             FROM countries
             INNER JOIN economies
             ON countries.code = economies.code
             WHERE year = 2015) AS subquery
        GROUP BY continent);
```
•  Use a subquery to get 2015 economic data for countries that do not have `gov_form` of 'Constitutional Monarchy' or
'Republic' in their gov_form.
```
-- Select fields
SELECT code, inflation_rate, unemployment_rate
  -- From economies
  FROM economies
  -- Where year is 2015 and code is not in
  WHERE year = 2015 AND code NOT IN
  	-- Subquery
  	(SELECT code
   FROM countries
   WHERE (gov_form = 'Constitutional Monarchy' OR gov_form LIKE '%Republic'))
-- Order by inflation rate
ORDER BY inflation_rate;
```
-----

### Day 62: Monday, 10th February, 2020

**Today's Progress**

• Recap of SQL terms. `JOIN` combines cols from one or more tables in a relational database via lookup processes. `INNER JOIN` - keeps records in which key is in both tables. `LEFT JOIN` if key doesn't exist in right table, it'll show it as missing data. `RIGHT JOIN` - same as left, but vice versa. `FULL JOIN` - Both L & R w/ missing values will be shown. `CROSS JOIN` - matches all records from fields specified in one table w/ others specified in another. 

• `UNION` - includes every record but doesn't double count. `UNION ALL` - replicates and includes all in both tables. `INTERSECT` - gives only those records found in both of the two tables. `EXCEPT` - records in one table but not the other. `Semi join` - filter first table based on conditions set on a second table. `Anti join` - Good for diagnosing problems w/ other joins, will render all conditions not met. Subqueries - common in WHERE, SELECT, FROM and ON clauses.

• Get the country names and other 2015 data in the economies table and the countries table for Central American countries with an official language.
```
SELECT DISTINCT c.name, e.total_inv, e.imports
FROM countries AS c
LEFT JOIN economies AS e
ON (c.code = e.code
AND c.code IN (
SELECT l.code
FROM languages AS l
WHERE official = 'True'
) )
WHERE region = 'Central America' AND year = 2015
ORDER BY c.name;
```
•  Calculate the average fertility rate for each region in 2015
```
SELECT c.region, c.continent, AVG(p.fertility_rate) AS avg_fert_rate
  FROM countries AS c
    INNER JOIN populations AS p
      ON c.code = p.country_code
  WHERE year = 2015
GROUP BY region, continent
ORDER BY avg_fert_rate;
```
•  Determine the top 10 capital cities in Europe and the Americas in terms of a calculated percentage using city_proper_pop and metroarea_pop in cities.
```
SELECT name, country_code, city_proper_pop, metroarea_pop,  
      city_proper_pop / metroarea_pop * 100 AS city_perc
FROM cities
WHERE name IN
  (SELECT capital
   FROM countries
   WHERE (continent = 'Europe'
      OR continent LIKE '%America'))
     AND metroarea_pop IS NOT NULL
ORDER BY city_perc DESC
LIMIT 10;
```
-----

### Day 63: Tuesday, 11th February, 2020

**Today's Progress**

• Query `information_scheme` w/ `SELECT`
```
SELECT table_name
FROM information_schema.columns
WHERE table_schema = 'public';
```
• `CREATE TABLE`
```
CREATE TABLE table_name(
col_a data_type,
col_b data_type,
col_c data_type
);
```
```
CREATE TABLE weather (
clouds text,
temperature numeric,
weather_station char(5)
);
```
•  To print data from a table simply use
```
SELECT *
FROM table_name
```
•  To add columns to an existing table
```
ALTER TABLE table_name
ADD COLUMN column_name data_type;

e.g.

ALTER TABLE professors
ADD COLUMN university_shortname text;

SELECT *
FROM professors;
```
•  If DB structure changes, `INSERT DISTINCT` records into new tables like so:
```
INSERT INTO table_name(col_a, col_b)
VALUES ("value_a", "value_b");

e.g.
INSERT INTO organizations
SELECT DISTINCT organization,
organization_sector
FROM university_professors;
```
•  `RENAME` a column like so: 
```
ALTER TABLE table_name
RENAME COLUMN old_name TO new_name;
```
•  `DROP` a column like so:
```
ALTER TABLE table_name
DROP COLUMN column_name;
```
-----

### Day 64: Wednesday, 12th February, 2020

**Today's Progress**

•  Migrate data with `INSERT INTO` and `SELECT DISTINCT`. Then `DROP` (Delete) unecessary `university_professors` table.
```
INSERT INTO affiliations
SELECT DISTINCT firstname, lastname, function, organization
FROM university_professors;

SELECT * 
FROM affiliations;

DROP TABLE university_professors;
```
•  Better data quality w/ constraints. Integrity constraints are 1) `Attribute Constraints` - e.g. data types on columns. 2) `Key constraints` - e.g. primary keys. 3) `Referential integrity constraints` - enforced by foreign keys. Constraints give data structure, help w/ consistency and data quality, are data science prerequisites, and postgreSQL helps with enforcement.

•  CAST convert text based values into integers to perform calculations
```
SELECT CAST(some_col AS integer)
FROM table;

SELECT transaction_date, amount + CAST(fee AS integer) AS net_amount
FROM transactions;
```
• Data types consist of: `text, varchar[(x)], char[(x)], boolean, date/time, numeric, integers`. E.g. of type declarations:
```
CREATE TABLE students (
ssn integer,
name varchar(64),
dob date,
average_grade numeric(3,2) -- e.g 5.24
tuition_paid boolean
);
```
• Alter types after table creation and round number upwards.
```
ALTER TABLE students
ALTER COLUMN average_grade
TYPE integer
USING ROUND(average_grade);
```
• Using substrings to _truncate_ values
```
ALTER TABLE professors
ALTER COLUMN firstname
TYPE varchar(16)
USING SUBSTRING(firstname FROM 1 FOR 16);
```
-----

### Day 65: Thursday, 13th February, 2020

**Today's Progress**

•  `NOT NULL` and unique constraints - disallow NULL values on given column. Must hold true for current state. E.g.
```
CREATE TABLE students (
ssn integer not null,
lastname varchar(64) not null,
home_phone integer,
office_phone integer
);
```
After table has been created, it can be altered to insert `NOT NULL` or `DROP` constraints like so:
```
ALTER TABLE students
ALTER COLUMN home_phone
SET NOT NULL;

ALTER TABLE students
ALTER COLUMN ssn
DROP NOT NULL;
```
• Adding `UNIQUE` constraint
```
CREATE TABLE table_name (
column_name UNIQUE
);

ALTER TABLE table_name
ADD CONSTRAINT some_name UNIQUE(column_name);
```
• `Keys` are attributes that identify a record uniquely. `Superkey` attributes can be removed, `candidate key` - only one can be the chosen key. Below, a `candidate key` is identified by the f&lastname columns from the professors table, as they uniquely define the record. Anything else will bring duplicates and/or can be removed.
```
SELECT COUNT(DISTINCT(lastname, firstname)) 
FROM professors;
```
• `Primary keys` -  chosen from candidate keys as unique identifiers to DB table. i.e. - `license_no, id`. To create primary key & alter existing table:
```
CREATE TABLE products (
product_no integer PRIMARY KEY,
name text,
price numeric
);

ALTER TABLE table_name
ADD CONSTRAINT some_name PRIMARY KEY(column_name);
```
-----

### Day 66: Friday, 14th February, 2020

**Today's Progress**

• `Surrogate keys` - are essentially primary keys, built from other columns. Usually, `ids` to better define records. To add surrogate key w/ serial data type:
```
ALTER TABLE cars
ADD COLUMN id serial PRIMARY KEY;
```
• Make two columns a surrogate key, and make that one concatenated column a `pk` like so:
```
ALTER TABLE table_name
ADD COLUMN col_c varchar(256);

UPDATE table_name
SET col_c = CONCAT(col_a, col_b);

ALTER TABLE table_name
ADD CONSTRAINT pk PRIMARY KEY(col_c);
```
•  Add an ID column to a table and make it a pk. Query DB to check results. `Serial` - turns `cols` into auto incrementing number.
```
ALTER TABLE professors
ADD COLUMN id serial;

ALTER TABLE professors
ADD CONSTRAINT professors_pkey PRIMARY KEY(id);

SELECT *
FROM professors
LIMIT 10;
```
•  Process of checking record numbers, altering table to add ID col from CONCAT'd other two cols and making ID a pk.
```
-- Count the number of distinct rows with columns make, model
SELECT COUNT(DISTINCT(make, model)) 
FROM cars;

-- Add the id column
ALTER TABLE cars
ADD COLUMN id varchar(128);

-- Update id with make + model
UPDATE cars
SET id = CONCAT(make, model);

-- Make id a primary key
ALTER TABLE cars
ADD CONSTRAINT id_pk PRIMARY KEY(id);

-- Have a look at the table
SELECT * FROM cars;
```
• Example using UNIQUE social security numbers with 9 characters. Remember: `CHAR` is used for Fixed Length.
`VARCHAR` is used for Variable Length.
```
CREATE TABLE students (
lastname varchar(128) NOT NULL, # Up to 128 chars
ssn integer[9] UNIQUE,
phone_no char(12) # Fixed at 12
);
```
• 1:N relationships require `Foreign keys`, which point to the PK of another table. 
```
CREATE TABLE manufacturers (
name varchar(255) PRIMARY KEY
);

INSERT INTO manufacturers
VALUES ('Ford'), ('VW'), ('GM');

CREATE TABLE cars (
model varchar(255) PRIMARY KEY,
manufacturer_name integer REFERENCES manufacturer(name)
);

INSERT INTO cars
VALUES ('Ranger', 'Ford'), ('Beetle', 'VW');
```
• To alter existing table
```
ALTER TABLE a
ADD CONSTRAINT a_fkey FOREIGN KEY (b_id)
REFERENCES b (id);
```
• Note: FK referencing a PK w/ `id` is named `x_id` where `x` is the name of the referencing table in singular form. E.g. `university_id` would be the foreign key column in another table, referencing the `id` of the universities table. E.g.
```
ALTER TABLE professors
RENAME COLUMN univ_shortname TO university_id;

ALTER TABLE professors
ADD CONSTRAINT professors_fkey FOREIGN KEY (university_id) REFERENCES universities (id);
```
-----

### Day 67: Saturday, 15th February, 2020

**Today's Progress**

• Start DevEd's course. Form simple `header` with `nav` & follow up `section`.

• Refresher on `display: flex` properties, justifications, alignment and positioning. 

• Media queries, anchoring, linear gradient background effects, and background (size, cover, repeat) properties. Fun! 🤓

**Link(s) to work**

1. [Travelly](https://github.com/mostmojo/travelly)

-----

### Day 68: Monday, 17th February, 2020

**Today's Progress**

• Continue `Travelly` build to further expore HTML & CSS structure of individual components.

• Refresher on JOINING queries in PostgreSQL. Select all professors working for universities in the city of Zurich.
```
SELECT professors.lastname, universities.id, universities.university_city
FROM professors
JOIN universities
ON professors.university_id = universities.id
WHERE universities.university_city = 'Zurich';
```
-----

### Day 69: Tuesday, 18th February, 2020

**Today's Progress**

• Continue `Travelly` and input `@keyframes` to use `animation: cloudsAnimation 3s infinite alternate ease-in-out;` property and move clouds around.
```
@keyframes cloudsAnimation {
	from {
		transform: translate(10%, -10%);
	}
	to {
		transform: translate(0%, 0%);
	}
}
```
•  Use `linear gradient` with `clip` and `text-fill` properties to for the `h3` as a 'hack' to create appealing text background.
```
	background: linear-gradient(#131c27, #663b34);
	-webkit-background-clip: text;
	-webkit-text-fill-color: transparent;
```
• Play with components' `position: relative` & `position: absolute` to position clouds accordingly. Insert `z-index` in `@media screen and (max-width: 932px) { }` to ensure clouds are further in the background on smaller screens. Use `overflow: hidden;` to prevent clouds from overlapping other components when animation is applied.

-----

### Day 70 - 76: Wednesday 19th February - Monday, 24th February, 2020

**Today's Progress**

• Build website for dietary supplement in HTML, CSS & JS.

• Read on bootstrap classes for quick prototyping, add responsive layout and spacing classes. Utilize in product build.

• Implement tracking cookies with Geoplugin API, capture scrolling site behavior and create timer function.

**Link(s) to work**

1. [Keto](https://github.com/mostmojo/keto_challenge)
2. [JavaScript functions](https://github.com/mostmojo/keto_challenge/blob/master/js/scripts.js)
3. [Geoplugin](www.geoplugin.net)

-----

### Day 77: Tuesday, 25th February, 2020

**Today's Progress**

• Continue with Travelly site build. Implement `<form>` with flexbox, to ensure it's responsive. 

• Add relative padding for correct spacing and add `required` fields on `<input>` classes to ensure emails are caught correctly.

• Use `background` properties to position images with `linear gradient`.

```
background: linear-gradient(rgba(0, 0, 0, 0.5), transparent), url('/img/contact-mountain.png');
background-size: cover;
background-repeat: no-repeat;
```

**Link(s) to work**

1. [Travelly](https://github.com/mostmojo/travelly)
2. [formspree](https://formspree.io/)
3. [Site](https://mostmojo.github.io/Travelly/)

-----

### Day 78: Wednesday, 26th February, 2020

**Today's Progress**

• Use `formspree` to implement `POST` request in form with the following properties:
```
<form action="https://formspree.io/xayjolzr" method="POST">
```
• Use `position: sticky; top: 0px; z-index: 3;` on `.main-header` class to make nav bar scrollable but stay on top.

-----

### Day 79: Thursday, 27th February, 2020

**Today's Progress**

• Use Mozilla Dev tools to scout for accessibility perks. Implement higher opacity on `background: linear-gradient(rgba(0, 0, 0, 0.8), transparent), url('./img/landing-page.jpg');`

• Use semantic HTML5 tags `<header>, <footer>, <nav>, <main>` to cater for screen readers. Apply `line-height: 1.8` property to `.card` text for better readability. 

• Add `alt` tags in case images don't render: `<a href="#" title="twitter-social-media"><img src="./icons/twitter.svg" alt="twitter-social-media"/></a>`

• Add matching `for` and `id` form values so labels will point to inputs when clicked, like so:

```
<label for="email">Email:</label>
<input id="email" type="email" required name="_replyto">
```
• Add `:focus` pseudo class to button to insert `outline-style` and `outline-color` for accessibility.
```
button:focus {
	background: #2c3f57;
	outline-style: solid;
	outline-color: #7598c3;
}
```

• Add `@font-face` property to `style.css` to import downloaded fonts from a fonts folder on new photography site.
```
@font-face {
	font-family: 'Vibes';
	src: url('./fonts/GreatVibes-Regular.ttf');
}
```
• Use variables to make styling more scalable and resuable. 
```
html {
	font-size: 62.5%;
	--header1: calc(2rem + 1vw);
	--header2: calc(3.5rem + 1vw);
	--header3: calc(3rem + 1vw);
	--header4: calc(2.4rem + 1vw);
	--text: calc(1.5rem + 1vw);
	--big-text: calc(2.4rem + 1vw);
	--special-color: #906272;
	--background-color: #414141;
	--grey-text: #525252;
}

...

h1 {
	font-size: var(--header1);
}
```
• Use classes like `.flex` to apply them regularly without having to type out the whole load of CSS. Hax 🤓
```
.flex {
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
}
```
**Link(s) to work**

1. [Travelly](https://github.com/mostmojo/travelly)
2. [Photography site](https://github.com/mostmojo/photography-site)

-----

### Day 80: Saturday, 7th March, 2020

**Today's Progress**

• Use `flex: 1 1 40rem` to position items in a flexbox to take up x amount of space

• Use `@keyframes` to create animations on classes like so:
```
@keyframes opening {
	from {
		opacity: 0;
	}
	to {
		opacity: 1;
	}
}

@keyframes plant-entrance {
	from {
		transform: translateY(10%) rotateZ(-10deg);
	}
	to {
		transform: translateY(0%) rotateZ(0deg);
	}
}

```
• Create advanced animations to shake plant `png` image like so:
```
@keyframes plant-entrance {
	from {
		transform: translateY(10%) rotateZ(-10deg) rotateX(-90deg);
	}
	to {
		transform: translateY(0%) rotateZ(0deg) rotateX(0deg);
	}
}

@keyframes plant-shake {
	from {
		transform: rotateZ(-5deg);
	}

	to {
		transform: rotateZ(0deg);
	}
}

// Add to a class .plant ->

	animation: plant-entrance 1.5s ease-in-out 0.5s forwards,
	plant-shake 2.5s infinite ease alternate-reverse 2s;
	transform-origin: bottom;

```

• Install gitbash on Windows and connect SSH keys with Github, create git shortcuts with `alias gst='git status'`

**Link(s) to work**

1. [Gitbash](https://www.pluralsight.com/guides/using-git-and-github-on-windows)

-----

### Day 81: Sunday, 8th March, 2020

**Today's Progress**

• Create a hidden checkbox overlaying three spans that make a burger menu/ When the state of the checkbox is checked, then implement the mobile navigation style menu.
```
		<nav>
			<h1 id="logo">Artemis</h1>
			<input type="checkbox" class="menu-check" />
			<ul class="nav-links">
				<li><a href="#about">About</a></li>
				<li><a href="#work">Work</a></li>
				<li><a href="#contact">Contact</a></li>
			</ul>
			<div class="burger">
				<span></span>
				<span></span>
				<span></span>
			</div>
		</nav>
		
		...
@media screen and (max-width: 842px) {

	.hero {
		width: 100%;
	}

	.hero-introduction p {
		padding: 5rem 3rem;
	}

	/* Burger menu */

	.burger {
		position: relative;
		display: block;
	}

	.burger span {
		padding: 0.2rem 2rem;
		background: var(--grey-text);
		margin: 0.5rem 0rem;
		display: block;
		transition: all 0.5s ease;
	}

	.nav-links a {
		color: white;
		font-size: var(--header3);
		text-decoration: underline;
	}

	.nav-links {
		background: var(--background-color);
		position: fixed;
		width: 100%;
		height: 100%;
		top: 0;
		left: 100%;
		flex-direction: column;
		align-items: center;
		transition: transform 1s ease;
	}

	.menu-check {
		display: block;
		position: absolute;
		top: 50%;
		right: 5%;
		transform: translate(5%, -50%);
		width: 5rem;
		height: 5rem;
		cursor: pointer;
		opacity: 0;
		z-index: 100;
	}

	/* When menu-check, which is an `input type checkbox`, is checked, then alter the nav-links class plox */
	.menu-check:checked + .nav-links {
		transform: translateX(-100%);
	}

	/* When menu-check, which is an `input type checkbox`, is checked, then alter the burger span class to make the menu white */
	.menu-check:checked ~ .burger span {
		background-color: white;
	}

	/* When menu-check, which is an `input type checkbox`, is checked, then alter the burger span class to tilt and form an `X` */
	.menu-check:checked ~ .burger span:nth-child(1) {
		transform: rotateZ(45deg) translateY(300%);
	}

	.menu-check:checked ~ .burger span:nth-child(2) {
		opacity: 0;
	}

	.menu-check:checked ~ .burger span:nth-child(3) {
		transform: rotateZ(-45deg) translateY(-300%);
	}

}
		
```
• To change the three spans to make an `X` shape, use `nth-child(1)` to select the spans and rotate or translate them like so:
```
/* When menu-check, which is an `input type checkbox`, is checked, then alter the nav-links class plox */

	.menu-check:checked ~ .burger span:nth-child(1) {
		transform: rotateZ(45deg) translateY(300%);
	}
```
-----

### Day 82-85: Monday, 9th March - Thursday, 12th March, 2020

**Today's Progress**

• Create slot machine game in JS, JQuery, HTML & CSS

• Implement responsive layouts and use firefox dev tools to debug

• Use xcode's simulator for mobile responsiveness & browser stack

• Snippet from jQuery 
```
    /* On click, hide the welcome banner and reveal the slot machine */

    $('.go-button').click(function () {

        $('#mod' + (clk + 1)).fadeOut(100, function () {
            /*$('#lol').fadeIn(100);*/
            $('#lol').fadeTo(300, 100);
        });
        if (clk === 1) {
            counter_update(0, 7);
        } else if (clk === 2) {
            counter_update(7, 90);
        }
        $('#scoreboard').show('fast');
    });
```

**Link(s) to work**

1. [slot](https://github.com/mostmojo/mp-slot)

-----

### Day 86: Friday, 13th March, 2020

**Today's Progress**

• Implement `confetti` with jQuery inside a modal like so:
```
function modal3() {
	$('#lol').fadeOut(50);
	$('#scoreboard').fadeOut(50);

	$('#mod4').fadeIn(50);
	console.log('Click: ' + clk);
	$(document).ready(function() {
		$('body').css({
			'background-image': 'url("./assets/confetti.gif")',
			'background-repeat': 'repeat',
			'background-color': '#000'
		});
	});
}
```
• Use fadeIn/fadeOut to show and hide specific elements from HTML like so:
```
//Handle The Game End
$('#fin_btn').click(function() {
	$('#sl_machine').fadeOut(50);
	$('#mod4').fadeOut(50);
	$('#fp').fadeIn(50);
	$('#mod5').fadeIn(50);
});
```
-----

### Day 87-88: Saturday, 14th March, Sunday, 15th March 2020

**Today's Progress**

• Work on completing photography site, responsively in HTML, CSS & JS. Utilise the power of flexbox and %s for width adaptivity. E.g.
```
.hero {
	min-height: 90vh;
	width: 95%;
	margin: 0 0 0 auto;
	display: flex;
	flex-wrap: wrap;
	overflow: hidden;
}
```

• Use the `flex: 1  1 20rem;` attribute to space out flex'd items like so:
```
nav {
	width: 90%;
	margin: auto;
	display: flex;
	align-items: center;
	min-height: 10vh;
	padding: 2rem 0;
}

#logo {
	flex: 1 1 20rem;
}

.nav-links {
	display: flex;
	justify-content: space-around;
	flex: 1 1 20rem;
}
```
Use JS (` .querySelector `&` .classList.toggle ` & `.addEventListener`) to grab the nav bar, reveal it and connect it to links on the page like so:
```
const nav = document.querySelector('.nav-links');
const burger = document.querySelector('.burger');
const links = nav.querySelectorAll('a');

burger.addEventListener('click', () => {
	nav.classList.toggle('nav-open');
	burger.classList.toggle('toggle');
});

links.forEach(link => {
	link.addEventListener('click', () => {
		nav.classList.toggle('nav-open');
		burger.classList.toggle('toggle');
	});
});
```
**Link(s) to work**

1. [site](https://mostmojo.github.io/photography-site/)

-----

### Day 89-91: Monday, 16th March, Wednesday, 18th March 2020

**Today's Progress**

• Create PIN lock in jQ and Vanilla JS, with modules to 'Try again' and 'Congrats' upon successfully guessing the password. Use `getElementById and .querySelector` to grab classes and ids and trigger events like so:
```
// Function to make TRY AGAIN modal disappear when GO button is clicked

const goButton = document.querySelector('.fail-go');
const failContainer = document.querySelector('.fail-container');

goButton.addEventListener('click', () => {
	failContainer.classList.remove('toggle-show');
	failContainer.classList.add('toggle-hide');
	attempt++;
	document.querySelector('.pinly-highlight').style.backgroundColor = '#3e8f77';
	console.log(attempt);
});
```
```
// Function to hide CONGRATS & PINLY module and reveal THANK YOU module on email submission

const submit = document.querySelector('.congrats-submit');
const congrats = document.querySelector('.congrats');
const thanks = document.querySelector('.thankyou');
const pinlyWrap = document.querySelector('.pinly-wrap');

submit.addEventListener('click', () => {
	// Hide Congrats
	pinlyWrap.classList.add('toggle-hide');
	congrats.classList.add('toggle-hide');
	// Show Thank you
	thanks.classList.add('toggle-show-1');
	setTimeout(function() {
		thanks.classList.remove('toggle-show-1');
	}, 4000);
	// thanks.classList.add('toggle-hide-1');
});
````
• Research and utilise media queries for all devices.

• Create video tags for custom video player with play/pause buttons. Research video preload to avoid performance issues.
```
<head> 
...
<link rel="preload" href="./assets/animation-video.mp4" as="video" type="video/mp4">
</head>
<video id="video1" class="bg-video__content" autoplay preload loop>
	<source src="./assets/animation-video.mp4" type="video/mp4" />
	<source src="./assets/animation-video.mp4" type="video/ogg" />
	Your browser does not support the video tag.
</video>
```

**Link(s) to work**

1. [Media queries](https://gist.github.com/mostmojo/23db2f7a8b7c2a349f204089bef2ab79)
2. [Vault](https://github.com/mostmojo/vault-sp)

-----

### Day 92: Thursday, 19th March, 2020

**Today's Progress**

• Continue with Rock, Paper, Scissors game. Learn about `position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%);` to center an element in the center. Hallelujah! @dkouvdis. 

• Destructuring in JS, to create a counter to ensure user wins on the 3rd time the game is played and launch an alert. Use data attributes inside HTML to grab elements. Thanks to @hannahwoodward & @mio31337 for assistance.  

• Make pulsating effects in CSS with @keyframes for 'bubbly' titles.

• Read about responsive and fluid typography with `vh` and `vw` units using: `html { font-size: calc(1em + 1vw); }`

-----

### Day 93-94: Friday, 20th March, Saturday, 21st March, 2020

**Today's Progress**

• Build two websites with `<video>` tags, learn about `autoplay` & `preload` and ensure mobile responsiveness and performance is good. Use `transform: translateY(2px);` to make buttons look animated with `transition: all 0.4s ease;`.

• Continue with Dev Ed's course and build final portfolio page. Use `background, clip-text and text-fill` properties to create a gradient-like background for the `h2` like so:
```
	h2 {
		font-size: 8rem;
		padding-top: 2rem;
		background: linear-gradient(left, #38d39f, #38a4d3);
		background-clip: text;
		-webkit-text-fill-color: transparent;
		display: inline-block;
	}
```
• Create a `mixin` for `display: flex` properties with arguments in SASS like so: 
```
@mixin flex($justify, $align, $direction) {
	display: flex;
	justify-content: $justify;
	align-items: $align;
	flex-direction: $direction;
}

...

.intro {
	@include flex(space-between, center, row);
	min-height: 90vh;
	width: 90%;
	margin: auto;
	flex-wrap: wrap;
}
```
• Remember: `flex: 1 1 40rem;` is shorthand for `flex-grow`, `flex-shrink`, and `flex-basis.`
**Link(s) to work**

1. [Repo](https://github.com/mostmojo/folio)

-----

### Day 95: Sunday, 22nd March, 2020

**Today's Progress**

• Continue with portfolio site. Learn about `transform` properties to utilise positioning like so:
```
#clock-arrow {
	animation: clock 1.5s infinite linear;
	transform-box: fill-box;
	transform-origin: bottom;
}
```
• Use @keyframes with `rotateZ` for 3D rotation, of a specific point:
```
@keyframes me {
	from {
		transform: rotateZ(-2.5deg);
	}
	to {
		transform: rotateZ(2.5deg);
	}
}
```

• Explore `three.js` by researching and forking a game.

**Link(s) to work**

1. [Carrot hunt](https://mostmojo.github.io/carrot-hunt/)

-----

### Day 96 - 101: Monday 23rd March - Saturday, 28th March, 2020 :)

**Today's Progress**

• Spend the week creating various websites for client featuring HTML, CSS & JavaScript.

• Create a counterdown timer for a page with vanilla JS and ensure sites are mobile responsive on all platforms.

• Use Wistia service for responsive video tags to ensure cross browser and cross-device compatibility.

**Link(s) to work**

1. [Countdown timer](https://twitter.com/most_mojo/status/1243219113201356800?s=20)
2. [Video tags](https://twitter.com/most_mojo/status/1240302686374895618?s=20)
