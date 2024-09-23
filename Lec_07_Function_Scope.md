> **Topics:** Local vs. Global; Argument Passing; Frames; Stack Diagrams
#### Definitions
- **Scope**: Area of the variable is recognized and used
	- **Global**: Anywhere and shared, keep it as a constant
		- Able to use in Function
	- **Local**: Only in function defined
	- **Notice:** 
		- **Irrelevant whether argument (outside) and parameter (inside) the same name**
		- **Arguments are "Pass by Value", change parameter (inside) not affect argument (outside)**
		- **Unable to see variables of other function invocations, even called**
```python
#Unable to see variables of other function invocations, even called
def function_a():
	x = 5
	function_b()
	print(x) #Will not access function_b() variable (x = 10)

def function_b():
	x = 10
	print(x)

function_a()
```
- **Call Stacks**
	- Stores Info about Active Functions (Variables)
	- When Function called, New Frame (Block of Memory 虚拟内存) created.
		- Frame holds Local Variables & Track Execution
		- Discards after Function Completed
> **在没有 Global Scope 相同 Variable 前提条件下，Local Scope return `value` 可以为该 Variable 赋值。在该 Variable 已有 Global Scope 的前提条件下，Local Scope return `value` 无法 overwrite 该 Global 赋值 (在 Function 中已标明 Global 情况除外)**
> **`Return` Value 只有在 `x = f()` 赋值类才会影响全局**

```python
#Local Scope Example
x = 4 #Global Scope

def f(): #Step3
	x = 1 #Step4 x = 1 (Local, exists within the function)
	return x #Step5 x = 1 (Local, will be discarded after function execution)

print(x) #Step1 Global Scope Output: 4
print(f()) #Step2 Output: 1 (Local x = 1 returned by the Function)
print(x) #Step6 Global Scope Output: 4 (Global x remains unchanged)
```

```python
#Variable from Local to Global Scope Example 1
x = 4 #Global Scope

def f(): #Step2
	x = 1 #Step3 x = 1 (Local)
	return x #Step4 x = 1 (returned to Global Scope, but does not modify the global x directly)

x = f() #Step1 Assign Function return value to Global Variable x

print(x) #Step5 x = f() = 1 Output: 1
print(f()) #Step6 Output: 1 (Local, x = 1 returned by the Function)
print(x) #Step7 Output: 1 (Global, x remains 1 after Step 1)
```

```python
#Variable from Local to Global Scope Example 2
x = 4 #Global Scope

def f(): #Step3
	global x #Step4 Declare this is a Global Scope (Modify Global x inside the function)
	x = 1 #Step5 x = 1 (Global, stated in Step4)
	return x #Step6 return Global x = 1

print(x) #Step1 Globe Scope Output: 4
print(f()) #Step2 Output: 1 (Modifies Global x)
print(x) #Step7 (Global, x remains 1 by the function)
```

```python
def f(): #Step2
	x = 1 #Step3 x = 1 (local)
	print(x) #Step4 Output: 1

def g(): #Step6
	y = 2 #Step7 y = 2 (local)
	print(y) #Step8 Output: 2

def h(): #Step10
	z = 3 #Step11 z = 3 (local)
	print(z) #Step12 Output 3

f() #Step1
g() #Step5
h() #Step9
```

#### Errors
##### #1 Variables not Defined
```python
def set_a():
	a = 100 #Local Scope
   #return None

print(a) #Function not even called
```
> `NameError: name "a" is not defined`:  `a` is only defined in `Local Scope`

To Correct:
```python
def set_a():
	a = 100 #Local Scope
	return a #returned to Global Scope, but does not modify the global x directly

result = set_a() #Assigned Function return value to Global Variable a = 100
print(result) #Ouput: 100
```
##### #2 Variables Discarded after Function
```python
def set_b():
	b = 100 #Local Scope
   #return None
   
set_b() #Local Scope
print(b) #"b" is discarded after set_b()
```
>`NameError: name "x" is not defined`: `b` is only defined in `Local Scope`, discarded after `set_b()`

To correct:
```python
def set_b():
	b = 100 #Local Scope
	return b #returned to Global Scope, but does not modify the global x directly
   
result = set_b() #Assigned Function return value to Global Variable b = 100
print(result) #Output: 100
```
##### #3 Variables not Saved
```python
def count():
	x = 1
	x += 1
	print(x)
   #return None

count()
count()
count()
```
> `x = 1` is `Local Scope`, only exists in `count()`, `x` value gets discarded after `count()`

To Correct:
```python
x = 1 #Initialize x = 1 (global), if not, [x += 1] will crush since x is not defined

def count():
	global x #Access the Global x
	x += 1
	return x #returned to Global Scope, but does not modify the global x directly

print(count()) #Output 1 + 1 = 2
print(count()) #Output 2 + 1 = 3
print(count()) #Output 3 + 1 = 4
```

##### #4 Variables not Set / Pass
```python
def display_x(): #Function display_x() unable to find x, x is a Local Scope in Function main()
	print(x)
	
def main():
	x = 100
	display_x()
	
main()
```
> Function display_x() unable to find `x` value,  since `x` value only exists in Function `main()`

To Correct:
```python
def display_x(x): #Function take x = 100 from display_x(x)
	print(x) #Output: 100

def main():
	x = 100
	display_x(x) #Pass x = 100 to Function Display_x()

main()
```

##### #5 Use Global Scope inside Function
```python
msg = 'hello' # global, outside any func

def greeting():
    print(msg)

print('before: ' + msg)
greeting()
print('after: ' + msg)
```
> Same as #3 Correct Version

##### #6 Local Scope in Function not pass to Global Scope
```python
msg = 'hello'

def greeting():
    msg = 'welcome!'
    print('greeting: ' + msg)

print('before: ' + msg)
greeting()
print('after: ' + msg)
```
> `msg` in `greeting()` will not be saved

##### #7 Assignment Order Incorrect
```python
msg = 'hello'

def greeting():
    print('greeting: ' + msg)
    msg = 'welcome!'

print('before: ' + msg)
greeting()
print('after: ' + msg)
```
> Local Variable referred before Assignment

To Correct:
> Refer to #6 Local Scope in Function not pass to Global Scope

##### #8 Use Global Declaration
```python
msg = 'hello' #Initialize msg (global)

def greeting():
    global msg #Declare msg here will be change in Global Scope
    print('greeting: ' + msg) #Output current msg "hello"
    msg = 'welcome!' #Reassign msg = "welcome!" (global)

print('before: ' + msg) #Output: "hello"
greeting() #Output: "hello", but msg (global) changed from hello to "welcome!" after output
print('after: ' + msg) #Output: "welcome!"
```

##### #9 Passed by Value, Reassignment does not change Argument Outside
```python
def f(x):
    x = 'B'
    print('inside: ' + x)

val = 'A'
print('before: ' + val)
f(val)
print('after: ' + val)
```

##### #10 Irrelevant whether Argument (Outside) & Parameter (Inside) have Same Variable Name
```python
x = 'A'

def f(x):
    x = 'B'
    print('inside: ' + x)

print('before: ' + x)
f(x)
print('after: ' + x)
```