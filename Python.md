# The Holy Python Cheat Sheet
Contents:
1. [Thirty Days Of Python - Udemy Course Notes](https://github.com/eomereu/thirtydaysofpython/blob/master/cheatSheet.md#thirty-days-of-python---udemy-course-notes)  
   - Main Stuff
   1. [Lists](https://github.com/eomereu/thirtydaysofpython/blob/master/cheatSheet.md#lists)
   1. [Dictionaries](https://github.com/eomereu/thirtydaysofpython/blob/master/cheatSheet.md#dictionaries)
   1. [Tuples](https://github.com/eomereu/thirtydaysofpython/blob/master/cheatSheet.md#tuples)
   1. [Loops](https://github.com/eomereu/thirtydaysofpython/blob/master/cheatSheet.md#loops)
   1. [Conditionals & Conditional Expressions](https://github.com/eomereu/thirtydaysofpython/blob/master/cheatSheet.md#conditionals--conditional-expressions)
   1. [Functions](https://github.com/eomereu/thirtydaysofpython/blob/master/cheatSheet.md#functions)
   1. [String Substitution](https://github.com/eomereu/thirtydaysofpython/blob/master/cheatSheet.md#string-substitution)
   1. [Classes](https://github.com/eomereu/thirtydaysofpython/blob/master/cheatSheet.md#classes)
   1. [Ineritence](https://github.com/eomereu/thirtydaysofpython/blob/master/cheatSheet.md#inheritence)
   1. [Import](https://github.com/eomereu/thirtydaysofpython/blob/master/cheatSheet.md#import)  
   1. [Exception Handling](https://github.com/eomereu/thirtydaysofpython/blob/master/cheatSheet.md#exception-handling)

1. [Differences Between Python2 & Python3](https://github.com/eomereu/thirtydaysofpython/blob/master/cheatSheet.md#differences-between-python2--python3)
1. [PEP 8 - Style Guide for Python Code](https://github.com/eomereu/thirtydaysofpython/blob/master/cheatSheet.md#pep-8---style-guide-for-python-code)
   1. [Indentation](https://github.com/eomereu/thirtydaysofpython/blob/master/cheatSheet.md#indentation)
   1. [Maximum Line Length](https://github.com/eomereu/thirtydaysofpython/blob/master/cheatSheet.md#maximum-line-length)
   1. [Line Break](https://github.com/eomereu/thirtydaysofpython/blob/master/cheatSheet.md#line-break)
   1. [Imports](https://github.com/eomereu/thirtydaysofpython/blob/master/cheatSheet.md#imports)
   1. [Whitespaces](https://github.com/eomereu/thirtydaysofpython/blob/master/cheatSheet.md#whitespaces)
   1. [More Recommendations on Whitespaces](https://github.com/eomereu/thirtydaysofpython/blob/master/cheatSheet.md#more-recommendations-on-whitespaces)
   1. [Comments](https://github.com/eomereu/thirtydaysofpython/blob/master/cheatSheet.md#comments)
   1. [Documentation Strings](https://github.com/eomereu/thirtydaysofpython/blob/master/cheatSheet.md#documentation-strings)
   1. [Naming Conventions](https://github.com/eomereu/thirtydaysofpython/blob/master/cheatSheet.md#naming-conventions)
***
***

## [Thirty Days Of Python - Udemy Course Notes](https://github.com/codingforentrepreneurs/30-Days-of-Python-3.6/blob/master/PythonCheatSheet.md)

- There is no type declaration while creating variables in Python,
```python
a = 32
b = "python"
```
- Comments in python are written by square `#` but it doesn't support multi-line commenting.

- String concetenation,
```python
>>> "python" + " three"
'python three'
>>> 2 * 2
4
>>> "ab" * 2
'abab'
```
- Lists (called as arrays in other languages) in python are created with square brackets `[]`. The items in a list don't have to be of same type,
```python
my_list = [] #creating an empty list
["my first item"]
["my first item", "my second item", "true"] #this 'true' is a string
["my first item", "my second item", 52, True, False] #booleans in python start with capitalized letters
```
- It is a much more better to use to stick with one usage along the code, for example using just single quotes `''` or double quotes `""` while handling strings. It increases the readability and stability of the code.

- List indexing starts from 0 in python. Also string indexing...
```python
my_list = ["good job", "nice", "well done"]
>>> my_list[0]
'good job'
>>> "vivaldi"[0]
'v'
>>> my_list[10]
IndexError: list index out of range
```
***

### Lists
1. `list.append(element)`  
    Adds a new elemet at the end of a list,
```python
>>> my_list = [1, 2, 3, 4, 4]
>>> my_list.append(5)
>>> my_list
[1, 2, 3, 4, 4, 5]
```
2. `list.pop()`  
    Removes the last elemet of a list,
```python
>>> my_list.pop()
>>> my_list
[1, 2, 3, 4, 4]
```
3. `list.pop(index)`  
    Removes the element at the given index,
```python
>>> my_list.pop(1) #2 is removed
>>> my_list
[1, 3, 4, 4]
```
4. `len(list)`  
    Returns the length of the list. It is also usable with strings,
```python
>>> len(my_list)
4
>>> len("no string dude")
14
```
5. `list.count(element)`  
    Returns count of how many times *element* occurs in list,
```python
>>> my_list.count(4)
2
```
6. `list.extend(list2)`  
    Appends the contents of *list2* to *list*. If we type a *string* instead of *list2* it will append all single letters one by one to the list,
```python
>>> extra = [5, 6, 6, 7]
>>> my_list.extend(extra)
>>> my_list
[1, 3, 4, 4, 5, 6, 6, 7]
>>> my_list.extend("op")
>>> my_list
[1, 3, 4, 4, 5, 6, 6, 7, 'o', 'p']
```
7. `list.index(element)`  
    Returns the lowest index in the list that element appears on,
```python
>>> my_list.index(4)
2
```
8. `list.insert(index, element)`  
    Inserts *element* into list at offset index,
```python
>>> my_list.insert(1, 2)
>>> my_list
[1, 2, 3, 4, 4, 5, 6, 6, 7, 'o', 'p',]
```
9. `list.remove(element)`  
    Removes the element that is on the lowest index from list if multiple. If there is just one from the element it simply removes it,
```python
>>> my_list.remove(4)
>>> my_list
[1, 2, 3, 4, 5, 6, 6, 7, 'o', 'p']
>>> my_list.remove('o')
>>> my_list
[1, 2, 3, 4, 5, 6, 6, 7, 'p']
```
10. `list.reverse()`  
    Reverses the list,
```python
>>> my_list.reverse()
>>> my_list
['p', 7, 6, 6, 5, 4, 3, 2, 1]
```
11. `sorted(list)`  
    Returns a sorted version of *list* regarding the *key*. Does not alter the original list. It sorts from lowest to highest (from a to z on strings),
```python
>>> list_1 = [1, 52, 5, 66, 33, 27]
>>> sorted(list_1)
[1, 5, 27, 33, 52, 66]
>>> list_2 = ["mehmet", "ali", "zeynep", "kadir"]
>>> sorted(list_2)
["ali", "kadir", "mehmet", "zeynep"]
```
12. `sorted(list, reverse=True)`  
    Returns a reverse-sorted version of *list* regarding the *key*. Does not alter the original list. It sorts from highest to lowest (from z to a on strings),
```python
>>> sorted(list_1, reverse=True)
[66, 52, 33, 27, 5, 1]
>>> sorted(list_2, reverse=True)
["zeynep", "mehmet", "kadir", "ali"]
```
13. `sorted(list, key, reverse)`  
    Returns a sorted version of *list* based on the *key*. On demand reverse property can also be used by setting to True or False. Does not alter the original list.
    `key=len` provides a sorting based on the length of the words, from shortest to longest,
```python
>>> list_3 = ["mike", "alexandra", "joe"]
>>> sorted(list_1, key=len)
["joe", "mike", "alexandra"]
```
`key=str.lower` Hiddenly converts all strings to lowercase to help to sort it in the correct way, if we don't use this sorted function will sort the words beginning with uppercased and lowercased seperately because it actually sorts them according to their UNICODE values, that's why it will first sort the ones beginning with capitalized letters within theirselves and the ones beginning with lowercased letters within thierselves seperately,
```python
>>> names_with_case = ['Harry', 'Suzy', 'al', 'mark']

# sorting w/o using 'key=str.lower' property
>>> sorted(names_with_case)
['Harry', 'Suzy', 'al', 'mark']

# sorting with using 'key=str.lower' property
>>> sorted(names_with_case, key=str.lower)
['al', 'Harry', 'mark', 'Suzy']
```
As well as pre-defined functions, user-defined functions can also be used with `key` argument...  

In below code, it simply reverses the string and then evaluates the first letter for sorting, which in conclusion means they are being sorted based on their last letters,
```python
def reverse_word(word):
    return word[::-1]

>>> words = ['banana', 'pie', 'Washington', 'book']
>>> sorted(words, key=reverse_word)
['banana', 'pie', 'book', 'Washington']
```
14. `list.sort()`  
    Sorts the *list* from lowest to highest (from a to z on strings). It modifies the original list in place and returns 'None',
```python
>>> values_to_sort = [5, 2, 6, 1]
>>> values_to_sort.sort()
>>> values_to_sort
[1, 2, 5, 6]
```
15. `list.sort(key, reverse)`  
    All the properties in `sorted` of *key* and *reverse* also apply here... Furthermore here we can mention about anonymous (lambda in python) functions,  
    
    In below code, it simply reverses the string and then evaluates the first letter for sorting, which in conclusion means they are being sorted based on their last letters but in the reverse order this time unlike the one above,
```python
>>> words = ['banana', 'pie', 'Washington', 'book']
>>> words.sort(key=lambda x: x[::-1], reverse=True)
>>> words
['Washington', 'book', 'pie', 'banana']
```
16. `sum(list)`  
    Returns the summation of the numbers in a given list,
```python
>>> abc = [4,6,3,7]
>>> sum(abc)
20
```
***

### Dictionaries
Dictionaries are like lists but they consist of key-value pairs and curly braces around them. We can use both strings and integers as keys in both python 2 and 3 unlike the other languages. We can have lists, tuples or dictionaries inside dictionaries
```python
my_dict = {
    "name": "Omer",
    "age": 24,
    "isCool": True,
    52: "Ordu",
    my_listing = [1, 2, 3],
    inner_dict = {
        "salut": "hello"
    }
}
```
We can reassign values to the keys,
```python
>>> my_dict["isCool"]
True
>>> my_dict["isCool"] = False
>>> my_dict["isCool"]
False
```
We can create a new key-value pair,
```python
my_dict[66] = "Yozgat"
```
If we try to access to a nonexistent key, we get `KeyError`,
```python
my_dict["surname"] #KeyError: 'surname'
my_dict[3] #KeyError: 3
```
***

### Tuples
Unlike lists and dictionaries, tuples are immutable like strings and so cannot be changed,
```python
my_tup = (1, 2, (4, 5), [21, 54])
```
But lists or dictionaries inside of a tuple can be changed,
```python
my_tup[3][1] = 9
my_tup #1, 2, (4, 5), [21, 9])
```
Also however, we can add things to tuples,
```python
>>> my_tup += "append me man"
>>> my_tup
(1, 2, (4, 5), [21, 54], "append me man")
>>> my_tup += ((9))
TypeError
>>> my_tup += (("9"))
TypeError
>>> my_tup += ((9),)
>>> my_tup
(1, 2, (4, 5), [21, 54], 9)
>>> my_tup += ((9,10))
>>> my_tup
(1, 2, (4, 5), [21, 54], 9, 9, 10)
>>> my_tup += ((12, 13),)
>>> my_tup
(1, 2, (4, 5), [21, 54], 9, 9, 10, (12, 13))
```
***

### Loops
1. `for`  
    This loop doesn't have a classical syntax in python. It can be used to iterate over a sequence of a list, string, tuple, set, array, data frame. for loops cannot be empty, but if you for some reason have a for loop with no content, put in the `pass` statement to avoid getting an error.
```python
for i in "Datacamp":
    pass
for i in list:
    pass
```
***Some useful functions that can be used with `for` loop:***
- `range(start, end, step)`  
    To iterate over a series of items `for` loops use the range function. It will start from including *start* and will end on not-including *end* by going as *step*. If we just type one input inside the parantheses it means *end* and will start from including zero. If we input two values, we mean *start* and *end*. The range function returns a new list with numbers of that specified range based on the length of the sequence,
```python
for i in range(10): #i € [0,10)
    pass
for i in range(1,10,2):
    print (i) #1\3\5\7\9
for i in range(len(sequence)):
    element = sequence[i]
    if type(element) == int:
        sequence[i] = element + 4
```
- `.enumerate(list)`  
    This function can be used with for loop to work with both indexes and values of items in a list,
```python
for idx, val in enumerate(ints):
    print(idx, val)
```
2. `while`
```python
while True:
    pass
```
***

### Conditionals & Conditional Expressions
- The example syntaxes of an `if` condition,
```python
a = 52
b = 52
c = 66
if a == b:
    return True
elif c == b:
    return False
else:
    return None

if a is b:
    print("true")

if a != b:
    print("false")

>>> not True
False
>>> !True
SyntaxError
>>> 3**3 == 27
True
```
As seen above `is` is the same thing with `==`. To oppose something in python we use `not` keyword instead of exclamation mark `!`. Also we use `elif` keyword instead of `else if` keyword in python.

- `isinstance(val, type)`  
    This is a useful function for type checking, it returns True if the val matches the type, False otherwise,
```python
>>> isinstance(3, int)
True
>>> isinstance(3.0, int)
False
>>> isinstance("John", str)
True
```
- In python there is no `x++` or `x--` instead we use,
```python
x += 1
x -= 1
```
- Ternary operator (the short version of if statement),
```python
you_are = "kid" if age < 18 else "adult"
```
***

### Functions
  Functions let us to execute a bunch of code again and again w/o rewriting them every time,
```python
def my_function(int_list):
    avg = sum(int_list)/len(int_list)
    # Above if we use Python 2 and we want it to return the actual floating point number
    #  then we have to type it as following,
    #  avg = sum(int_list)/(len(int_list)*1.0)
    return None
```
  ***There are 2 types of arguments that can be passed to functions:***
1. Positional Arguments  
    Actually these are the ones that are generally used and the classical ones. They have to be given to the function while calling it otherwise we get `TypeError` as *missing required positional arguments*
```python
def my_func(arg_1, arg_2):
    pass
```
2. Keyword Arguments  
    These are the ones that coded with a default value when defining the function. They don't have to be called while we call the function.
```python
def my_func(arg_1, arg_2, kwarg_1=None, kwarg_2="abc"):
    if kwarg_1 != None:
    print(kwarg_1)
```
It is a better practice to send keyword arguments with argument names while calling it, in terms of clarification of things going on,
```python
def func(email=email, to_list=to_list):
    pass
func(email="hello@world.com", to_list=signed_in_ones)
```
***PS:*** *Positional Arguments* must be written before the *Keyword Arguments* while defining the function, otherwise we get `SyntaxError` as *non-default argument follows default argument*

- Anonymous functions are called as 'lambda' functions in python and its syntax is like following,
```python
lambda x: x + 1

# We can directly name it like a variable,
>>> add_one = lambda x: x + 1
>>> add_one(2)
3

# Here it directly takes 2 and 3 as arguments and returns the result,
>>> (lambda x, y: x + y)(2, 3)
5

# An example of a higher order function,
>>> high_ord_func = lambda x, func: x + func(x)
>>> high_ord_func(2, lambda x: x * x)
6
>>> high_ord_func(2, lambda x: x + 3)
7
```
***

### String Substitution
- `str.format(var="value")`  
This is another way of formatting strings,
```python
"This is {var_a} formatted string".format(var_a="variable based")
```  
- `str.format("value")`  
Other than working with variable names we can also work with their positionings,
```python
>>> text = "This {0} an {1}. An {1} {0} an important thing.".format("is", "argument")
>>> text
'This is an argument. An argument is an important thing.'
```
 - `str.format(**dict)`  
While formating a string with use of a dictionary, we need to use double stars `**` notation:
```python
message = "Hello {name}! It's {air_condition} today."
context = {
    "name": "David",
    "air_condition": "heavily raining"
}
>>> message.format(**context)
"Hello David! It's heavily raining today."
```
> It's obliged to provide values of every placeholder, within the string, in the dictionary in order not to get a `KeyError`!
- `str %("value")`  
This method is more practical than the format method,
```python
>>> a = "%s me %s!" %("Format", "mate")
>>> a
'Format me mate!'
>>> b = "How to write %%s %s" %("is like this")
>>> b
'How to write %s is like this'
```
- `"%.xf" %(num)`  
Float substitution is used to show how many decimal place ('x' above) we want to show,
```python
>>> t = "8 decimal places: %.8f" %(52)
>>> t
'8 decimal places: 52.00000000'
>>> f = "Limit the places to 2: %.2f" %(3.146454634736346)
>>> f
'Limit the places to 2: 3.14'
```
- `datetime`  
Date using and substitution can be used via importing a built in library,
```python
import datetime
today = datetime.date.today()

# yyyy, m, d
>>> today
datetime.date(2020, 9, 3)
>>> now = datetime.datetime.now()

# yyyy, m, d, hh, mm, ss, ms
>>> now
datetime.datetime(2020,9, 3, 07, 24, 32, 94518)

# m/d/yy
>>> text = today.strftime('%-m/%-d/%y')
>>> print(text)
9/3/20
```
We can also format our date like the following,
```python    
today.strftime('%d/%m/%Y') #04/09/2020
```

- `str(var)`  
Changes type of 'var' to string

- `string.capitalize()`  
We can capitalize strings with this method,
```python
>>> "ali".capitalize()
'Ali'
```
***

### Classes
Classes are like a generalization of a kind like animals or mammals etc. We create objects/instances of that class,
```python
class Dog:
    name = "Jon"
    color = "brown"
```
Although it can be defined w/o parantheses we may prefer using them for a better and generalized use. While creating an object from a class we must use parantheses after the class name during the assignment. Because it only creates a sample object from that class when we use parantheses, otherwise we cannot create an object,
```python
class Dog():
    name = "Jon"
    color = "brown"

# The line below doesn't create any objects
>>> Dog
<class '__main__.Dog'>
>>> Dog()
<__main__.Dog object at 0x1015e8278>

# The line below creates an object of that class
# Used parantheses as mentioned above
>>> instance = Dog()
>>> obj = Dog()
>>> object = Dog()
# We see the 3 lines above widely in 'django'
>>> obj.name = "Snow"
>>> obj.name
'Snow'
>>> object.name
'Jon'
```
To define a method inside of an object with keyword `self`,
```python
class Dog():
    name = "Jon"
    color = "brown"
def get_color(self):
    return self.color
def say(self, what):
    return("Woof " + what + "!")

>>> obj = Dog()
>>> obj == self
True
>>> obj.get_color()
'brown'
>>> obj.say("Hello")
Woof Hello!
```
Actually here `self` mean the object itself which we created, so there is no need to pass an argument when we call that method. Furthermore to access attributes/features of a created object from a specific class we build up these methods and while using we must include `self` keyword to be able to access features.
>`Self` is recurring to the instance that we create an object of a class!
***

### Inheritence
In order to inherit from a class we should write the name of the inherited class inside of the parantheses our inheriting class,
```python
class Animal():
    can_think = False
    name = "Anything"
    noise = "Grunt"
def make_noise(self):
    return self.noise
class Dog(Animal):
    name = "John Doe"
    noise = "Woof!"
```
  
- Property `@property`  
  Actually property is a method inside of a class. But it differs in the way that its calling style. We have to call the non-property methods with paratheses at the end but if we don't want to use parantheses while calling then we can define that function *(method)* as a property. However if we call the property methods with using parantheses then we get `TypeError`. To define property we simply add `@property` on the line above:
```python
class Dog():
    name = "name"
    def bark(self):
        print("Woof!")
    @property
    def make_noise(self):
        print("Auuuu!")
>>> jon = dog()
>>> jon.bark() #Woof!
>>> jon.make_noise #Auuuu!
# Other cases:
>>> jon.bark()
<bound method dog.bark of <__main__.ani object at 0x7f1bb9bffbb0>>
>>> jon.noise()
Auuuu! \n Traceback... TypeError: 'NoneType' object is not callable

# More other cases:
>>> dog.bark
<function dog.bark at 0x7f1bb9b7f790>
>>> dog.make_noise
<property object at 0x7f1bb9b81b30>
```
The reason we turned messaging function into a class, we can now keep store of user details inside of the atr of the object. Furthermore we can now manipulate/change/add/set the data more dynamically and more safely compared to the version with functions and two simple lists. So from that time on, I can just simply import that class in my file and play with it, rather than openin the file itself and hardcoding it every single time! *(01_String_Substitution_Exercise vs 02_Classes_Exercise)*
***

### Import
1. To import a python module from the same directory we simply do the following,
```python
from My_Python_Module import ClassName, function_name
```
2. To import a python module from another folder/directory we first need to create a file named as `__init__.py` inside of that folder for python to be able to recognize that folder as a python module and grants us access to the modules inside of that folder/directory. Otherwise we get an error. Btw `__init__.py` may be blank:
```python
from Python_Modules.My_Python_Module_1 import ClassName function_name
from Python_Modules.My_Python_Module_2 import AnotherClassName another_function_name
```
So here *Python_Modules* is a folder and its consists following items inside,
```python
__init__.py
My_Python_Module_1.py
My_Python_Module_2.py
```
***

### Exception Handling
Simply put the code that may cause an error into `try` block and specify the action based on specific errors or any error in `except` blocks:
```python
try:
    # All code that may cause an error goes here like:
    SMTP.login(username, password)
except AnySpecificError:
    # Runs only when AnySpecificError occurs
    warn_and_notify_user()
except AnySpecificError:
    # Runs only when AnyOtherSpecificError occurs
    warn_and_notify_user()
except:
    # Runs when any other error occurd besides AnySpecificError and AnyOhterSpecificError
    say_that_an_error_occured()
```
In example:
```python
>>> def this_fails():
...     x = 1/0
...
>>> try:
...     this_fails()
... except ZeroDivisionError as err:
...     print('Handling run-time error:', err)
...
Handling run-time error: division by zero
```
To define and raise our own exception:
```python
if not the_case:
    raise Exception("Requirements not met!")
else:
    begin_process()
```
To intendly raise a built-in exception:
```python
>>> raise NameError('HiThere')
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: HiThere
```
***
***

## Differences Between Python2 & Python3
|Python 2 |Python 3 |
|--- |--- |
|print "NoNeedBrackets" |print("BracketsRequired") |
|print "ASCII"<br>print u"ThisIsUnicode" |print("AlwaysUnicode")<br>print("AlwaysUnicode") |
|int/int = int (5/2=2) |int/int =~ float (5/2=2.5) |
|raw_input() reads string |raw_input() not available |
|input() evaluates data read |input() reads string |
|generator.next() |next(generator) |
|Indent. w both tabs & spcs |disallows mixing |
|- |py2to3utility |
***
***


## [PEP 8 - Style Guide for Python Code](https://www.python.org/dev/peps/pep-0008/)
### Indentation
Use 4 spaces per indentation level. PEP 8 recommends to use spaces over tabs, so to make this happen we can rearrange the function of *tab* key in any editor we use. Whichever way is chosen, it must be followed throughout the whole code as Python 3 no more allows a mixed use of tabs and spaces. Other than this, using spaces will always keep our code correctly-aligned when we forced to copy & paste our code between different editors.

Aligned with opening delimiter:
```python
foo = long_function_name(var_one, var_two,
                        var_three, var_four)

```

Add 4 spaces (an extra level of indentation) to distinguish arguments from the rest:
```python
def long_function_name(
        var_one, var_two, var_three,
        var_four):
    print(var_one)
```
Hanging indents should add a level:
```python
foo = long_function_name(
    var_one, var_two,
    var_three, var_four)
```

The closing brace/bracket/parenthesis on multiline constructs may either line up under the first non-whitespace character of the last line of list, as in:
```python
my_list = [
    1, 2, 3,
    4, 5, 6,
    ]
```

or it may be lined up under the first character of the line that starts the multiline construct, as in:
```python
my_list = [
    1, 2, 3,
    4, 5, 6,
]
```
***

### Maximum Line Length
Limit all lines to a maximum of 79 characters. For flowing long blocks of text with fewer structural restrictions (docstrings or comments), the line length should be limited to 72 characters. Backslashes may still be appropriate at times. For example, long, multiple with-statements cannot use implicit continuation, so "backslashes" are acceptable:
```python
with open('/path/to/some/file/you/want/to/read') as file_1, \
    open('/path/to/some/file/being/written', 'w') as file_2:
    file_2.write(file_1.read())
```
***

### Line Break
Following the tradition from mathematics usually results in more readable code... Easy to match operators with operands:
```python
income = (gross_wages
            + taxable_interest
            + (dividends - qualified_dividends)
            - ira_deduction
            - student_loan_interest)
```
***

### Imports
Imports should usually be on separate lines. It is always a best practice to order imports alphabetically!
```python
import os
import sys
```
***

### Whitespaces
Avoid extraneous whitespace in the following situations.

Immediately inside parentheses, brackets or braces:
```python
spam(ham[1], {eggs: 2})
```
Between a trailing comma and a following close parenthesis:
```python
foo = (0,)
```
Immediately before a comma, semicolon, or colon:
```python
if x == 4: print x, y; x, y = y, x
```
However, in a slice the colon acts like a binary operator, and should have equal amounts on either side (treating it as the operator with the lowest priority). In an extended slice, both colons must have the same amount of spacing applied. Exception: when a slice parameter is omitted, the space is omitted:
```python
ham[1:9], ham[1:9:3], ham[:9:3], ham[1::3], ham[1:9:]
ham[lower:upper], ham[lower:upper:], ham[lower::step]
ham[lower+offset : upper+offset]
ham[: upper_fn(x) : step_fn(x)], ham[:: step_fn(x)]
ham[lower + offset : upper + offset]
```
Immediately before the open parenthesis that starts the argument list of a function call:
```python
spam(1)
```
Immediately before the open parenthesis that starts an indexing or slicing:
```python
dct['key'] = lst[index]
```
More than one space around an assignment (or other) operator to align it with another:
```python
x = 1
y = 2
long_variable = 3
```
***

### More Recommendations on Whitespaces
Always surround these binary operators with a single space on either side: assignment (=), augmented assignment (+=, -= etc.), comparisons (==, <, >, !=, <>, <=, >=, in, not in, is, is not), Booleans (and, or, not).

If operators with different priorities are used, consider adding whitespace around the operators with the lowest priority(ies). Use your own judgment; however, never use more than one space, and always have the same amount of whitespace on both sides of a binary operator:
```python
i = i + 1
submitted += 1
x = x*2 - 1
hypot2 = x*x + y*y
c = (a+b) * (a-b)
```
Don't use spaces around the = sign when used to indicate a keyword argument, or when used to indicate a default value for an unannotated function parameter:
```python
def complex(real, imag=0.0):
    return magic(r=real, i=imag)
```
When combining an argument annotation with a default value, however, do use spaces around the = sign:
```python
def munge(sep: AnyStr = None): ...
def munge(input: AnyStr, sep: AnyStr = None, limit=1000): ...
```
***

### Comments
Comments in python are written by square `#` and it doesn't support multi-line commenting. After the square `#` always leave one space. *(I indently don't put a space after square when I use inline comments.)* Inline comments are unnecessary and in fact distracting if they state the obvious. 
***

### Documentation Strings
Write docstrings for all public modules, functions, classes, and methods. Docstrings are not necessary for non-public methods, but you should have a comment that describes what the method does. This comment should appear after the def line.

We write docstrings inside a double triple quotes:
```python
"""Return a foobang

Optional plotz says to frobnicate the bizbaz first.
"""
```
For one lined docstrings, please keep the closing `"""` on the same line.
***

### Naming Conventions
Never use the characters 'l' (lowercase letter el), 'O' (uppercase letter oh), or 'I' (uppercase letter eye) as single character variable names. Conventions for every data type:

- Package and Module Names  
Modules should have short, all-lowercase names. Python packages should also have short, all-lowercase names, although the use of underscores is discouraged,
```python
import mymathlib
```

- Class Names  
Class names should normally use the CapWords convention.
```python
class MyHolyClass:
    ...
```

- Exception Names  
Because exceptions should be classes, the class naming convention applies here. However, you should use the suffix "Error" on your exception names (if the exception actually is an error).
```python
class ValidationError(Exception):
    ...
```

- Function and Variable Names  
Function names should be lowercase, with words separated by underscores as necessary to improve readability. Variable names follow the same convention as function names. mixedCase is allowed only in contexts where that's already the prevailing style (e.g. threading.py), to retain backwards compatibility.
```python
def my_sacred_func():
    ....
my_own_var = 52
# or in the latter scenario,
mixedCasedVariable = 81
```

- Global Variable Names  
The conventions are about the same as those for functions,
```python
my_global_var = "everywhere"
```

- Method Names and Instance Variables  
Use the function naming rules: lowercase with words separated by underscores as necessary to improve readability. Use one leading underscore only for non-public methods and instance variables. (Although PEP8 says so, mixedCase can also be used)
```python
def instance_method(self):
    ...
@classmethod
def class_method(cls):
    ...
@staticmethod
def static_method():
    ...
```
- Function and Method Arguments  
  Always use 'self' for the first argument to instance methods. Always use cls for the 'first' argument to class methods. [*Example of different method types*](https://levelup.gitconnected.com/method-types-in-python-2c95d46281cd)
```python
class MethodTypes:

    name = "Ragnar"

    def instance_method(self):
        # Creates an instance atribute through keyword self
        self.lastname = "Lothbrock"
        print(self.name)
        print(self.lastname)
    
    @classmethod
    def class_method(cls):
        # Access a class atribute through keyword cls
        cls.name = "Lagertha"
        print(cls.name)

    @staticmethod
    def static_method():
        print("This is a static method")

# Creates an instance of the class
m = MethodTypes()
# Calls instance method
m.instance_method()

MethodTypes.class_method()
MethodTypes.static_method()
```
- Constants  
  Constants are usually defined on a module level and written in all capital letters with underscores separating words,
```python
MAX_OVERFLOW
```