>**Topics**: Functions; Arguments & Return Values; Input, Print; Int, Float, Str, Bool; Importing Modules; Math and Random Modules

#### Vocabulary
- **Function Definition**: Group lines of codes, prompt to run the group. Build up function for later usage.
- **Call / Invoke**: Call a Function, run the group codes, and back to Function to execute following codes
- **Parameter**: Variable with input to function
- **Argument**: Values assigned to the function (provide data to Function)
- **Keyword Argument**: Specific parameter value
- **Default Argument**: Default value for parameter (no argument is provided)
- **Return Value**: Function output
```python
#Basic Function Example 
#Function Definition
def calculator(a = 5): #a is a Parameter, 5 is Defult Argument
	return a ** 2

#Call / Invoke
calculator(a = 3) #3 is an Argument
```
```python
#Keyword Argument Function Example
#Function Definition
def introduce(name, age): #name, age are Parameters
	print("Hi, my name is " + str(name) + ", I'm " + str(age) + " years old")

#Call / Invoke
introduce(age = 25, name = "Bob") #Keyword Argument
```

#### Functions
- Functions will not be used until called
- `help()`: Build-in Function for Instructions
- `print(value, spe = " ", end = "\n")`: Print Code `Default Value`
	- `sep = "?"`: Substitute space with `?`
	- `end = " "`: Substitute new line with ` `(space)
- `type()`: Type of the Parameter
- `len()`: Length of the Argument
- `int(number)`: Turns `number` into integer
- `float(number)`: Turns `number` into float
- `str(value)`: Turns `value` into string
- `bool(value)`: Turns `value` into boolean
- `input(value)`: Input `value` into function
- `round(number, ndigits = None)`: Round `number` to selected digits
- `abs(number)`: Return the absolute value of `number`
- `pow(number, exp)`: Power of `number` 
```python
#help() Example
help(len)p
```
```python
#type() Example
print(type(3.145))
print(type("str"))
```
```python
#len() Example
print(len("Hello"))
```
```python
#int() / float() Example
print(int(5.324))
print(float(3))
```
```python
#str() Example
str(3.41)
```
```python
#bool() Example
print(bool("abc"))
print(bool(0))
```
> `bool()` function returns True for most values, other than `False, None, 0, "",(), [],{}`
```python
#input() Example
temp = float(input("Enter your temperature: "))

#Solution
print("Your temperature is " + str(temp))
```
```python
#round() / abs() Example
print(round(5.14))
print(round(5.82))
print(abs(-2.41))
```
```python
#pow() Example
print(pow(2, 3))
print(2 ** 3)
```

#### More Functions (Import from Other Modules)
- `import <module_name>`: Import Module
	- `<module_name>.<function name>`: To use from the module
- `from <module_name> import *`: Import all functions from the module
	- `from <module_name> import <function_name>`: Import specific function from the module
- `dir <module_name>`: All functions in the module
```python
#import example
import math
import random

#All Functions List
dir(math)

#Output
print(dir(math))
```

```python
#Math SQRT Example_1
import math
result = math.sqrt(9)

print(result)
```
```python
#Math SQRT Example_2
from math import sqrt
result = sqrt(9)

print(result)
```
```python
#Math SQRT Example_3
from math import sqrt
result = sqrt(9)

print(result)
```



#### Review Questions
- `add(7, x = 6)`
> **Review**: Concept under python will not replace `x = 6` with `7`
