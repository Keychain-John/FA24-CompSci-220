> **Topics**: Parts of Expressions (Operators, Literal Values, Variables); Naming Rules; Assignment Statements; Errors (Syntax, Runtime, Sematic)
> **Worksheet**: None

#### Variables
- **Literal Values**: Fixed Values
```python
10, 22.0, "Hello", True
```
- **Variables**: Variable Values
	- Made up w/. Letters, Numbers, Underscore
		- Start with Letters or Underscore
	- No python keywords
```python
#Variable Naming Examples
cs220
cs_220
_cs220
#Prohibted Variable Naming Examples
220class #Start with number
and #python keywords
pi3.14 #Period included
```

#### Assignment Statement
- **Length Function**
```python
#State
name = "Mike"

#Find length
name_len = len(name)

#Solution
print(name_len)
```
- **Shortcuts**
	- `+=`: `x = x + ?`
	- `-=`: `x = x - ?`
	- `*=`: `x = x * ?`
	- `/=`: `x = x / 7`
```python
#State
hours = 40
pay_rate = 10.50

#Paycheck Calculation
paycheck = hours * pay_rate

#Solution
print(paycheck)
```

```python
#State
student_age = 19

#Question: Create a variable called votable
#If younger than 18, False, otherwise, True

if student_age > 18:
	votable = True
else:
	votable = False

#Solution
print(votable)
```

```python
#State
principal = 1000
rate = 0.07
time = 30

#Amount Calculation
amount = principle * (1 + rate) ** time

#Solution
print(amount)
```

#### Errors
- **Syntax Error**: Non-sense
- **Runtime Error**: Run to encounter
- **Semantic Error:** Wrong answer
```python
#Syntax Error Example
5 = x
```
```python
#Runtime Error
x = 5 / 0
```
```python
#Semantic Error
square_area = square_side * 2
```

#### Extra Practices
```python
# Given the number of seconds, compute the number of hours, minutes, and seconds.
#  e.g. if seconds is 65, the correct output (with \n in-between) is 0 1 5
#  e.g. if seconds is 192, the correct output (with \n in-between) is 0 3 12
#  e.g. if seconds is 3739, the correct output (with \n in-between) is 1 2 19

#State
seconds = 3739

#Compute hours
hours = seconds // (60 * 60)

#Compute remainder seconds
seconds = seconds % (60 * 60)

#Compute minutes
minutes = seconds // 60

#Compute remainder seconds
seconds = seconds % 60

#Solution
print("If seconds is " + str(seconds) + ", the correct output is " + str(hours) + " hour(s) " + str(minutes) + " minute(s) " + str(seconds) + " second(s)")
```

```python
#State
player1_name = "Alice"
player2_name = "Bob"

player1_score = 10
player2_score = 8

#To visualize score, suppose name has maximum of 9 characters
print(player1_name + ": " + " " * (9 - len(player1_name))+ "|" * player1_score)
print(player2_name + ": " + " " * (9 - len(player2_name))+ "|" * player2_score)
```
#### Review Questions
```python
False = 100
```
> **Review**: Concept under **Variables**, in python, unable to assign values to `False` or other keywords