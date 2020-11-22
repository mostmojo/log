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

•  Look into various navbar animations for responsive design, @keyframes and how they interact

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

-----

### Day 6: Friday, 6th November, 2020

**Today's Progress**

•  Review flask app with run, init and routes pathways and ensure to understand the python package.
•  

**Link(s) to work**

1. [Corey Schafer](https://www.youtube.com/watch?v=u0oDDZrDz9U&t=1562s)

-----

### Day 7: Saturday, 7th November, 2020

**Today's Progress**

•  Continue course - Files. Learn file writing syntax to open files in python `myfile = open('myfile.txt')` and `pwd` to check for directory. `myfile.read()` to read files. `myfile.seek()` to reset the cursor. `myfile.readlines()` to get a list that is spaced on individual lines, which can be indexed and manipulated. Use `pwd` to get file path like so: `myfile = open("/Users/jacob/Folder/myfile.txt")` and `myfile.close()` to close file. 

•  New way to `READ` and autoclosing files:

```
with open(myfile.txt) as my_new_file:
  contents= my_new_file.read()
  contents
```

•  WRITE (overwrites existing file)
```
with open('myfile.txt', mode='w') as f:
  f.write('I CREATED THIS NEW LINE')

with open('myfile.txt', mode='r') as f:
  print(f.read())
# I CREATED THIS NEW LINE
```

•  APPEND (adds to the last line, no overwrite)
```
with open('myfile.txt', mode='a') as f:
  f.write('\n SOMETHING NEW WRITTEN HERE')
```
• If, elif, else statements for `control flow` - colons & indentation.
```
name = 'Sam'
if name == 'Frank':
  print('Hi Frank')
elif name == 'Sam':
  print('Hi Sam')
else:
  print('What\'s your name?')
```

• For loops - to iterate through strings, tuples and dictionaries via `tuple unpacking`. To get the full items you need to use the `items()` method on the dictionary for tuple unpacking. for `item in d.items():`.
```
d = {'k1':1,'k2':2,'k3':1}
for item in d
  print(item)
# k1
# k2
# k3
```
**Link(s) to work**

1. [Udemy Pierian Data Course](https://www.udemy.com/course/complete-python-bootcamp/learn/lecture/9388536#announcements)

-----

### Day 8: Sunday, 8th November, 2020

**Today's Progress**

•  Go over while loops in python and the `break`, `continue`, `pass` statements 

•  Useful operators - `range(3,10,2)`, `enumerate`, which unpacks in tuples, `zip` and `in`, `minmax` and `from random import shuffle` import function + `randint`.

•  Grab user input `result = int(input('Enter a number: '))`. Remember all user input is in `str`. Can either `int(result)`, or `float(result)` post or pre data grabbing.

• Use a for within a for loop for client ZEN, to grab data within a dictionary like so:

```
routes.py
guitar_pedals = {
    "Distortion": {"DT1": {"Distortion pedal with powerful tone": "https://image..."}
}
...
pedals.html
	{% for pedal_title, description_key in pedal_model.items() %}
			{% for desc, img_path in description_key.items() %}
	{% endfor %}
	{% endfor %}
```

**Link(s) to work**

1. [Udemy Pierian Data Course](https://www.udemy.com/course/complete-python-bootcamp/learn/lecture/9407968#content)

-----

### Day 9: Monday, 9th November, 2020

**Today's Progress**

•  List comprehension with for loops and one liners. The example below appends a calculation of each temp in celsius into the empty farenheit list. E.g.
```
celsius = [0,10,20,34.5]
farenheit = []

for temp in celsius:
    farenheit.append((9/5)*temp+32)
# [32.0,50.0,68.0,94.1]
```
or one liners (not as legibile)
```
farenheit = [((9/5)*temp +32) for temp in celsius]
```
•  Another simpler example
```
mystr = "hello"
mylist=[]
for letter in mystr:
  mylist.append(letter)
mylist
# ['h','e','l','l', 'o']
```
As a one liner 
```
mylist=[letter for letter in mystr]
```

-----

### Day 10: Tuesday, 10th November, 2020

**Today's Progress**

•  Go through solutions of python test with .split(), range(), list comprehension, fizzbuzz task and indexing.

•  Revisit py inbuilt methods .append(), .pop() and dive into function declarations, the print (NoneType - can't be saved) and return statement (allowing saving ability). Start writing logic into functions like so:
```
# Return True if any num is even
def check_even_list(num_list):
	for number in num_list:
		if number %2==0:
			return True
		else:
			pass
check_even_list([2,4,5])
```
•  Read into Flask WTForms and Flask Mail
**Link(s) to work**

1. [Flask Mail & Flask WTForms](https://code.tutsplus.com/tutorials/intro-to-flask-adding-a-contact-page--net-28982)

-----

### Day 11: Wednesday, 11th November, 2020

**Today's Progress**

•  Deployed client site test to Python Anywhere using a virtual environment, bash scripts and GitHub.

•  Read about the benefits of virtual environments in Python's Flask framework versus downloading packages globally and effects they have per project.

•  Look into Wagtail CMS docs for client to gauge feasibility of using Python as a backend CMS for a basketball betting blog-based project.

**Link(s) to work**

1. [Python Anywhere](https://www.pythonanywhere.com/user/mostmojo/)
2. [Py Anywhere Deployment](https://medium.com/@tossia13/lets-take-it-online-deploying-your-flask-application-to-pythonanywhere-3ab87c1c851c)
3. [Virtual Flask Environment](https://topherpedersen.blog/2019/12/28/how-to-setup-a-new-flask-app-on-a-mac/)
4. [Wagtail CMS](https://docs.wagtail.io/en/stable/getting_started/tutorial.html)
5. [Wagtail YT Tuts](https://www.youtube.com/playlist?list=PLMQHMcNi6ocsS8Bfnuy_IDgJ4bHRRrvub)

-----

### Day 12:Thursday, 12th November, 2020

**Today's Progress**

• Continue functional logic in python
```
def check_even_list(num_list):
	#return list of even numbers

	#placeholder vars
	even_numbers = []
	
	for number in num_list:
		if number %2 ==0:
			even_numbers.append(number)
		else:
			pass
	return even_numbers
check_even_list([1,2,3,4,5])
# [2,4]

```
• Tuple unpacking functions
```
work_hours = [('Abbey': 100), ('Chris': 500), ('Rob': 800)]

def employee_check(work_hours):
	current_max = 0
	employee_of_month = ""
	
	for employee, hours in work_hours:
		if hours > current_max
			current_max = hours
			employeee_of_month = employee
		else:
			pass
	return(employee_of_month, current_max)
	
employee_check(work_hours)
('Rob': 800)
```

• Return statement in tuple unpacking can be saved in a variable that'll show the tuple like so: ('Rob': 800), or can be saved in its k:v and be manipulated like so: name,hours = employee_check(work_hours) -> name -> 'Rob'

**Link(s) to work**

1. [Python Anywhere](https://www.pythonanywhere.com/user/mostmojo/)

-----

### Day 13: Friday, 14th November, 2020

**Today's Progress**

•  Read Heroku docs and CODEMY to upload ZEN client app to heroku. Utilized Py's virtual environment with `pip3 install virtualenv`, `virtualenv venv --system-site-packages`, `source venv/bin/activate deactivate`. Learned how to `pip freeze > requirements.txt` to ensure app is created in production with all its reqs. 

•  Made a 'Three cup monty game' in python to make different functions interact
```
from random import shuffle

def shuffle_list(mylist):
    shuffle(mylist)
    return mylist

def player_guess():
    guess = ''
    while guess not in ['0', '1', '2']:
        guess = input('Pick a number. 0, 1, or 2: ')
    return int(guess)

def check_guess(mylist, guess):
    if mylist[guess] == 'X':
        print('Correct! 😊')
    else:
        print("Wrong!")
        print(mylist)

# initialize list
mylist = ['', 'X', '']

# shuffle list
mixed_up_list = shuffle_list(mylist)

# check player guess
player_guess = player_guess()

# check guess
check_guess(mixed_up_list, player_guess)
```

**Link(s) to work**

1. [ZEN - Heroku](https://zenstudios.herokuapp.com/)
2. [Codemy - Heroku tuts](https://www.youtube.com/watch?v=Li0Abz-KT78)

-----

### Day 14 & 15: Friday, Saturday 14th, 15th, November, 2020

**Today's Progress**

•  Continue Pieran Data course. Complete a series of puzzle exercises to strengthen python learning.

```
1. 

def lesser_of_two_evens(a,b):
    if a%2 == 0 and b%2 == 0:
        if a < b:
            return min(a,b)
    else: 
        if a > b:
            return max(a,b)
	    
2. 
def animal_crackers(text):
    split_word = text.lower().split()
    
    return split_word[0][0] == split_word[0][0]

3. 
def makes_twenty(n1,n2):
    return (n1+n2) == 20 or n1 == 20 or n2 == 20

4.
def old_macdonald(name):
    first_part = name[:3]
    second_part = name[3:]
    
    return first_part.capitalize() + second_part.capitalize()

5.
def master_yoda(text):
    wordlist = text.split()
    rev_text = wordlist[::-1]
    return " ".join(rev_text)

6.
def almost_there(n):
   return (abs(100-n) <= 10) or (abs(200-n) <= 10)
```
