find_class
==========

This little package finds and loads a class by fully qualified string.

Let's assume there is a file in `package/sub/animal.py` with 

```python
class Animal:  
    def say_somthing(self):
        return 'wau'

def a_little_function():
    return 'wuff'

a_tone = 'wiiiiii'
```

Then, you can use `find_class` to get from a string to the python-thing:

```python
a = find_class('package.sub.animal.Animal')().say_something()
b = find_class('package.sub.animal.a_little_function')()
c = find_class('package.sub.animal.a_tone')

assert a == 'wau'
assert b == 'wuff'
assert c == 'wiiiiii'
```