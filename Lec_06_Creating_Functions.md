> **Topics**: Blocks; Positional Arguments; Keyword Arguments; Default Arguments; Return
#### Functions
- `<func_name>`: Follow Naming Rules
- `(parameters)`: Empty or Comma-Separated
- `body_lines`: Intended lines
```python
def <func_name>(parameters):
	body_line1
	body_line2
```

#### Return vs. Print
- `return`:Send output from a function `def <func_name>` to the calling place `func_name(paramters)`
	- default `return = None`
	- Only first `return` will be executed
> When not assigning `return` value, `None` will be returned
- `print`: Display Output
```python
#Return Example (Only First Return will be executed)
def bad_return(x, y):
	return x + y
	return x - y #Will be skipped

print(bad_return(2, 3))
```

```python
#Define Function Good Example 1
def cube(num):
	return num ** 3

print(cube(5)) #5^3
print(cube(4) + cube(-3)) #4^3 + (-3)^3
print(cube(cube(2))) #(2^3)^3
```

```python
#Define Function Bad Example
def bad_cube(num):
	print(num ** 3)
   #returns None

x = bad_cube(5)

#Output
print(x) #Since nothing returned, X contains the value None
```
> `bad_cube` only prints value, but returns nothing, which assigns `x = None` in the end

```python
#Define Function Good Example 2
def is_between(lower, num, upper):
	return num > lower and num < upper

#Call Function 
print(is_between(5,8,13))
print(is_between(5,5,13))
print(is_between(100,cube(5),200))
```

```python
#Define Function Good Example 3
# get_grid(5, 3, "@") returns the string 
# @@@@@
# @@@@@
# @@@@@ 
def get_grid(width, height, symb):
    return (((symb * width) + '\n') * height)

#Call Function and Assign Value to my_grid
my_grid = get_grid(5, 3, "*");
 
#Output
print(my_grid)
```

```python
#Define Functions Good Example 4
#get_grid_with_title
#Define Function
def get_grid_with_title(width, height, symb, title='My Grid'):
    row = (symb * width) + '\n'
    grid = ((row) * height)
    return title + '\n' + grid

#Output
print(get_grid_with_title(7, 7, title='CS220 Grid', symb='&'))
```

#### Types of Arguments
- **Positional** (Priority)
- **Keyword**
- **Default**
```python
#Positional Example
def add3(x = 100, y = 100, z = 100):
	tot = x + y + z
	return tot

#Calls Function (Positional)
add3_result = add3(50, 50) #z will autofill z = 100

#Output
print(add3_result)
```
```python
#Keyword Example
def add3(x = 100, y = 100, z = 100):
	tot = x + y + z
	return tot

#Calls Function (Positional)
add3_result = add3(50, 50, 50)

#Output
print(add3_result)
```
```python
#Default Example
def add3(x = 100, y = 100, z = 100):
	tot = x + y + z
	return tot

#Calls Function (Positional)
add3_result = add3()

#Output
print(add3_result)
```
```python
#Mix Example
def add3(x = 100, y = 100, z = 100):
	tot = x + y + z
	return tot

#Calls Function (Positional)
add3_result = add3(30, z = 20, y = 10)

#Output
print(add3_result)
```

- **Bad Examples (Syntax Error)**
	- `add3(z = 5, 2, 7)`
		- Correct: `add3(2, 7, z = 5)`
	- `add3(x = 10 , y, z)` 
		- Positional needs to come first
		- Correct: `add3(y, z, x = 10)`
	- `add(5, 3, 10, x = 4)`
		- Multiple values for `x`

#### Fruitful Function vs. Void Function
- **Fruitful Function**: Returns Something
- **Void Function**: Returns Nothing
```python
#Fruitful Function Example
def good_add3(x, y, z):
	return(x + y + z)

#Calls Function
print(good_add3(10, 20, 30))
```

```python
#Void Function Example
def bad_add3(x, y, z):
	print(x + y + z)
   #return None

#Calls Function
print(bad_add3(10, 20, 30))
```

#### Worksheet
##### Question 1
```python
#What will be in parameters for each call?
def add(x, y):
	print(x) #for debugging
	print(y) #for debugging
	return x + y
```
- `add(3)`
	- Crash, 1 Arguments
	- `x = 3, y = ""`
		- `y` value is missing
- `add(3, 4)`
	- Not Crash, 2 Arguments
	- `x = 3, y = 4`
- `add(4, 3)`
	- Not Crash, 2 Arguments
	- `x = 4, y = 3`
- `add(3, 4, 5)`
	- Crash, 3 Arguments
	- `x = 3, y = 4`
		- `5` has no where to go
- `add(6 , y = 7)`
	- No Crash, 2 Arguments\
	- `x = 6, y = 7`
- `add(7, x = 6)`
	- Crash, 2 Arguments
	- `x = 7, y = ""`
		- python will not replace `x = 6` with `7`
- `add(7, 8, x = 9)`
	- Crash, 3 Arguments
		- python will not replace `x = 9` with `7`
	- `x = 7, y = 8`
- `add(x = 10, y = 11)`
	- No Crash, 2 Arguments
	- `x = 10, y = 11`
- `add(y = 10, x = 11)`
	- No Crash, 2 Arguments
	- `x = 11, y = 10`

##### Question 2
```python
#What will be in the parameters for each call?
def say(word, t = 1, end = ""):
	#add prints here to debug
	print(word * t + end)
```
- `say()`
	- Crash, 0 Argument
	- `word = "", t = 1, end = ""`
		- `word` value is missing
- `say("ha")`
	- No Crash, 1 Argument
	- `word = "ha", t = 1, end = ""`
- `say("ha", t = 2)`
	- No Crash, 2 Arguments
	- `word = "ha", t = 2, end = ""`
- `say("ha", end = "!")`
	- No Crash, 2 Arguments
	- `word = "ha", t = 2, end = "!"`
- `say(t = 2, word = "yo")`
	- No Crash, 2 Arguments
	- `word = "yo", t = 2, end = ""`
- `say("W", 3, "eb")`
	- No Crash, 3 Arguments
	- `word = "W", t = 3, end = "eb"`
- `say(t = 3)`
	- Crash, 1 Argument
	- `word = "", t = 3, end = ""`
		- `word` value is missing
- `say("W", end = ".", 3)`
	- Crash, 3 Arguments
	- `word = "W", t = "", end = "."`
		- `3` has no where to go
- `say("huh", 1, "?", "!")`
	- Crash, 4 Arguments
	- `word = "huh", t = 1, end = "?"`
		- `"!"` has no where to go

##### Question 3
```python
#What letters are printed, and in what order?
print("A") #Step1 Output: "A"

def foo(): #Step4 #Step7
	print("B") #Step5 Output: "B" #Step8 Output: "B"

print("C") #Step2 Output: "C"

foo() #Step3

print("D") #Step6 Output: "D" 

foo() #Step7

#Step 9
```

##### Question 4
```python
#What is printed, and in what order?
def func_c(): #Step8
	print("C") #Step9 Output: "C"

def func_b(): #Step5
	print("B1") #Step6 Output: "B1"
	func_c() #Step7
	print("B2") #Step10 Output: "B2"

def func_a(): #Step2
	print("A1") #Step3 Output: "A1"
	func_b() #Step4
	print("A2") #Step11 Output: "A2"

func_a() #Step1

#Step12
```

##### Question 5
```python
#What is printed, and in what order?
def f(): #Step3
	print("A") #Step4 Output: "A"
	return("B") #Step5 Assign x = "B"
	print("C") #Skipped, this line will never returned 

print("D") #Step1 Output: "D"

x = f() #Step2 Define x

print("E") #Step6 Output: "E"

print(x) #Step7 Output: "B"
#Step8
```

#### Review Questions
- Review **Worksheet Question 5** 