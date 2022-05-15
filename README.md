# Python

Python A repository to study Python from scratch  

# Intro

This is a very good way to study python. Explore de files in it's repository and try youself.

# Hello World

The first example you can have

```Python
MESSAGE = "Hello, world!"
prin(MESSAGE, '\nYour first Python program");
}
```

# Structure

Structure in python was designed to be clean  
Simplicity is the allways the goal in python, because of this you need to respect some rules:  

## Indentation

Indentation metters  
Indentation is the number of space you use at left site to visually organize your code for reading  
I mean, human reading, not machine reading.

let's compare some structures of python with other languages

```Python
# Some full example in python
```
```C++
// Some full example in other Language
```

# Api 

This is a setup to create API

This amazing example shows how easy is to create an Api from scratch using HttpServer

```Python
from http.server import BaseHTTPRequestHandler, HTTPServer

class handler(BaseHTTPRequestHandler):
    def do_GET(self):
        message = "Hello, World!"
        self.wfile.write(bytes(message, "utf8"))

with HTTPServer(('', 8000), handler) as server:
    server.serve_forever()
```

This is very simple demonstration of python power, however if you want do dev some Api with python I recomend you try this FastApi library

see [row to create FastApi](https://github.com/ricardodarocha/Python/main/FastApy.py)

# Log

Loggin is very usefull Skill for any language  
Let's check our software and helps the user to understing when somthing was wrong  
```python
import logging

logging.debug('Hello, the program has started...')
logging.info('Info message')
logging.warning('Warning message')
logging.error('Error message')
logging.critical('Critical message')
```

Check an [**most explained example**](https://machinelearningmastery.com/logging-in-python/)

# A cool progress bar 

Thats library show us why python is a cool language  
```python
from time import sleep
from tqdm import tqdm

for n in tqdm(range(100)):
  sleep(1)
```

this is the result
```bash

▓▓▓▓▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒ 20% 
```
# Sumary by Subject

The examples by subject are in \General Folder

## Variables

You can declare variables just write the name of variable following symbol '=' and the value
```Python
name = 'Ricardo'
email = 'ricardodarocha@outlook.com'
```
## Types

Variable in Python are not typed, that means the compiler infer the type of variable on run time.

```Python
number = 1 #Number is a integer number
number = '1' #Now, number is a string
```

## Modules

```Python
from module import some
```

## Loop expressions

Loop is very fun in python  
Take some examples  

```python
for x in range(10){ // starts with 0, 10 is not inclusive
      if x%2==0
         print!(f"{x} is even")}
      if x==5:
         continue;
      print(f"{x}")
      
      if x==5:
         return x //If is a function, returns x
```

Loops in details [](https://github.com/ricardodarocha/Python/blob/main/general/loopExpressions)

## Error Handling

```Python
while True:
     try:
         x = int(input("Please enter a number: "))
         break
     except ValueError:
         print("Oops!  That was no valid number.  Try again...")
     except:
     # If not ValueError, then is a not mapped error kind, I mean an unknown error
         print("Oops!  Unknown Error")
```

Check [erro handling](https://docs.python.org/3/tutorial/errors.html docs

## Writing documentations

Python has full support on docstrings. Docstrings are commets in code you can write to make your code most readable for third consumers and colabs.

All about documentations  
See this Topic [here](https://realpython.com/documenting-python-code/)

## Writing  Tests

Tests are the heart of some software architecture, like TDD  
To write tests you can do something like 

```Python
assert sum([1, 2, 3]) == 6, "Should be 6"
```

Check [testing](https://realpython.com/python-testing/)

That prevines somebody tho change the values of array without checking it's can be changed

# Links

**Realç Python** [testing](https://realpython.com/
