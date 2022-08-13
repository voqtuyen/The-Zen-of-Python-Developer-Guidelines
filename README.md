# The Zen of Python - Developer Guides

PEP 20 (a.k.a. The Zen of Python)

```bash
The Zen of Python, by Tim Peters

Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex.
Complex is better than complicated.
Flat is better than nested.
Sparse is better than dense.
Readability counts.
Special cases aren't special enough to break the rules.
Although practicality beats purity.
Errors should never pass silently.
Unless explicitly silenced.
In the face of ambiguity, refuse the temptation to guess.
There should be one-- and preferably only one --obvious way to do it.
Although that way may not be obvious at first unless you're Dutch.
Now is better than never.
Although never is often better than *right* now.
If the implementation is hard to explain, it's a bad idea.
 If the implementation is easy to explain, it may be a good idea.
Namespaces are one honking great idea -- let's do more of those!
```

The Zen of Python is available in Python via 
```python
import this
```

#### 1. Beautiful is better than ugly

#### 2. Explicit is better than implicit

#### 3. Simple is better than complex

#### 4. Complex is better than complicated

#### 5. Flat is better than nested

Bad
```python
if condition_1:
    if condition_2:
        # Do something
    else:
        return
else:
    return
```

Good
```python
if not condition_1:
    return
if not condition_2:
    return
# Do something
```

#### 6. Sparse is better than dense

Bad
```python
# Example 1
print('Hello'); print('World')

# Example 2
if is_authenticated: print('You are authenticated')

# Example 3
if <complex condition 1> and <complex condition 2> and <complex condition 3>:
    # Do something
```

Good
```python
# Example 1
print('Hello')
print('World')

# Example 2
if is_authenticated:
    print('You are authenticated')

# Example 3
condition_1 = <complex condition 1>
condition_2 = <complex condition 2>
condition_3 = <complex condition 3>
if condition_1 and condition_2 and condition_3:
    # Do something

```

#### 7. Readability counts.

#### 8. Special cases aren't special enough to break the rules.

#### 9. Although practicality beats purity.

#### 10. Errors should never pass silently. Unless explicitly silenced.

Bad
```python
try:
    # Do something with possible exceptions
except:
    pass
```
- The except clause without any specified exception will catch everything and ignore it.
- A broad except clause can hide bugs and leave them to cause some problem later on

Good
```python
try:
    # Do something with possible exceptions
except:
    print('An exception happend')
    raise
```
- Always explicitly identify the exceptions you will catch by name and handle only those exceptions
- You can simply log the exceptions or otherwise acknowledge the exception and re-raise it

#### 11. In the face of ambiguity, refuse the temptation to guess.

#### 12. In the face of ambiguity, refuse the temptation to guess.

#### 13. There should be one-- and preferably only one --obvious way to do it.

#### 14. Although that way may not be obvious at first unless you're Dutch.

Example 1
```python
programming_language = 'Python'

# Method 1
print('The Zen of %s' % programming_language)

# Method 2
print('The Zen of {}'.format(programming_language))

# Method 3
print(f'The Zen of {programming_lanaguage}')
```

Example 2
```python
programming_language_1 = 'Python'
programming_language_2 = "Python"
```

In case there are multiple ways to solve a problem in Python, then developer needs to be familiar with all of the different methods. However, developers should follow the same choice throught the code base for better readibility

#### 15. Now is better than never.

#### 16. Although never is often better than *right* now.

#### 17. If the implementation is hard to explain, it's a bad idea.

#### 18. If the implementation is easy to explain, it may be a good idea.

#### 19. Namespaces are one honking great idea -- let's do more of those!

## References
1. https://peps.python.org/pep-0020/
2. The Hitchhiker's Guide to Python, Kenneth Reitz & Tanya Schlusser
