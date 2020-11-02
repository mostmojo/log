-----

### Day 1 : Sunday, 1st November, 2020

**Today's Progress**

•  Create flask app in python for client music recording studio app after watching a Flask Blog series (8 episodes thus far) of Corey Schafer on YouTube.

• Set up package with `if __name__ == '__main__': app.run(debug=True)`, `__init__.py`, `routes`, `templates` and `static files`. Ensure to understand package cycle in flask from run.py instantiation of app, to init, importing of flask and calling classes to save into app variable, and import routes, that way routes can be utilised with their functions i.e. `@app.route('/') def home(): return render_template('/home.html', title='Home')`. Finally, utilise the `from flask import render_template, url_for, flash, redirect, request` flask methods for ease of use when developing.

• Look into Jinja2 extends vs include terms for: `{% extends 'layout.html' %}` & `{% include 'partials/guitar_block.html' %}`.

• Read on Python Anywhere deployment via Github and create account.

**Link(s) to work**

1. [Corey Schafer](https://www.youtube.com/watch?v=u0oDDZrDz9U&t=1562s)
2. [Python Anywhere Deployment](https://medium.com/@tossia13/lets-take-it-online-deploying-your-flask-application-to-pythonanywhere-3ab87c1c851c)

-----

### Day 2 : Monday, 2nd November, 2020

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
