-----

### Day 1: Sunday, 1st November, 2020

**Today's Progress**

•  Create flask app in python for client music recording studio app after watching a Flask Blog series (8 episodes thus far) of Corey Schafer on YouTube.

• Set up package with `if __name__ == '__main__': app.run(debug=True)`, `__init__.py`, `routes`, `templates` and `static files`. Ensure to understand package cycle in flask from run.py instantiation of app, to init, importing of flask and calling classes to save into app variable, and import routes, that way routes can be utilised with their functions i.e. `@app.route('/') def home(): return render_template('/home.html', title='Home')`. Finally, utilise the `from flask import render_template, url_for, flash, redirect, request` flask methods for ease of use when developing.

• Look into Jinja2 extends vs include terms for: `{% extends 'layout.html' %}` & `{% include 'partials/guitar_block.html' %}`.

• Read on Python Anywhere deployment via Github and create account.

**Link(s) to work**

1. [Corey Schafer](https://www.youtube.com/watch?v=u0oDDZrDz9U&t=1562s)
2. [Python Anywhere Deployment](https://medium.com/@tossia13/lets-take-it-online-deploying-your-flask-application-to-pythonanywhere-3ab87c1c851c)

-----

### Day 2: Monday, 2nd November, 2020

**Today's Progress**

•  Jose Portilla Python course, with immutable strings, string methods and basic concatenations. E.g. `x.split()`, `x.lower()`, `x.upper()`.

• Use the python operators for fun to refresh, with indexing.

```
name = 'Sam'
last_letters = name[1:]
print(last_letters)
# 'am'
print('P' + last_letters)
# 'Pam'
```
• Look into Bootstrap for larger scale application and start developing components for client (Zen).

• Continue Jose's course and into string formatting, aka `string interpolation` using `format()` and `f-strings`. E.g. - `print('The {q} {b} {f}'.format(f='fox',b='brown', q='quick'))` => The quick brown fox.

• Use `f strings` aka `Formated String Literals` for a more modern, easier approach, using the `f` and variables within a string, like so:
```
name = 'Jose'
age = '3'
print(f'Hi, my name is {name}. I am {age} years old')
# Hi, my name is Jose. I am 3 years old
```

**Link(s) to work**

1. [Udemy Pierian Data Course](https://www.udemy.com/course/complete-python-bootcamp/learn/lecture/9388532#announcements)

-----

### Day 3: Tuesday, 3rd November, 2020

**Today's Progress**

•  Continue Pieran course, on Python `lists` and learn about `.append()` & `.sort()` & `.reverse()` & `.pop()` methods.

**Link(s) to work**

1. [Udemy Pierian Data Course](https://www.udemy.com/course/complete-python-bootcamp/learn/lecture/9388536#announcements)


-----

### Day 4 : Wednesday, 4th November, 2020

**Today's Progress**

•  Learn about JavaScript obfuscation to 'hide' functions by reprocessing them to prevent people from taking your work

•  Python dictionaries (JS Objects) - learn shorthand querying, while using Py's methods, like so: 
```
d = {'key1': ['a', 'b', 'c']}
d['key1'][2].upper()
# 'C'
```
•  Update dictionary `d['k1'] = 13`. Also use `d.keys()`, `d.values()`, `d.items()` to showcase the `dict_keys`, `dict_values` & `dict_items`. Remember that
`items()` are rendered as tuples ( normal brackets ) and their values can be manipulated accordingly. E.g. - `dict_items([('k1', 100), ('k2', '200')])`.

•  Utilize this with ZEN Studios client website `{% for title, description in microphones_dict.items() %}` with Jinja2 templating, to get the title and description within a microphones dictionary and render the title tags within a dictionary in the `routes.py` folder.

•  `Tuples` - written in () but similar to [] lists, just immutable. e.g. `t = (1,2,3)`. If we try to reassign `t[0] = 222` -> `Type Error`. Tuples have 2 methods - `index` & `count`. E.g. `t.count(1)` -> `1`.

•  `Sets` - unordered collections of unique elements, e.g. - `mylist = [1,1,1,2,2]`, `set(mylist)`, `{1,2}`. The are rendered in square brackets like dictionaries but just have the unique values. You can also use .add() method to add anything to a set variable.

**Link(s) to work**

1. [JS Obfuscator](https://obfuscator.io/)

-----

### Day 5: Thursday, 5th November, 2020

**Today's Progress**

•  Look into various nav bar animations for responsive design, @keyframes and how they interact

• Continue Jose's course - go through refresher on comparison operators `2 == 2 --> True | 4 != 5 --> True`

• Logical operators in python `and, or, not` e.g. `'h' == 'h' and 2 == 2 --> True`

• Recap on if, elif and else statements with python's `control flow` syntax containing colons and indentation like so:

```
name = 'Sam'

if name == 'Frank':
  print('Hi Frank')
elif name == 'Alex':
  print('Hi Alex')
else:
  print('What is your name?)
```

**Link(s) to work**
1. [W3 Schools Nav](https://www.w3schools.com/howto/howto_js_topnav_responsive.asp)
