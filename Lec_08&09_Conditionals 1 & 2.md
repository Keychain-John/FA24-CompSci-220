> **Topics:**

#### if, elif, else, nested Statements
- **if Statement Syntax**
```python
#if Stmt. Form
if condition:
	#if True, code to run
```

```python
#if stmt. Example
#Determine a word is short or not: short if <= 5 characters, long if else
#State
word = "hello"

#Word Length
word_length = len(word)

#if Stmt.
if word_length <= 5:
	print("Word is short")
if word_length > 5
	print("Word is long")
```

- **if-else Statement Syntax**
```python
#if-else Stmt. Form
if condition:
	#if True, code to run
else:
	#if False, code to run
```

```python
#if-else stmt. Example
#State
word = "hello"
word_length = len(word)

#if-else stmt.
if word_length <= 5:
	print("Word is short")
else:
	print("Word is long")
```

-  **if-elif Statement Syntax**
```python
#if-elif Stmt. Form
if condition1:
	#Code Block
elif condition2:
	#Code Block

...

else: conditionN: #Final else portion is optional
	#Code BlockN
```

- **Nested if-else Statement**
```python
#if-elif Nested Stmt. Form
if condition1:
	if condition1_1:
		#if True, code to run
	elif condition1_2:
		#if True, code to run
	else:
		#if condition1_1 or condition1_2 False, code to run
else: 
	if condition2_1:
		#if True, code to run
	elif condition2_2:
		#if True, code to run
```

```python
#if-elif Nested Example
def fix(moves, should):
    if moves:
        if should:
            return "good"
        else:
            return "duct tape"
    else:
        if should:
            return "WD-40"
        else:
            return "good"

#Output
print(fix(moves=True, should=False))
print(fix(moves=False, should=False))
print(fix(moves=True, should=True))
print(fix(moves=False, should=True))
```

#### Refactoring
- Improve / Rewrite parts of program
- Easier to understand code & execution
- Sometimes code runs faster
- **Notice**
	- Not Changing Program's Behavior
	- Program should be more readable

```python
#Refactor if-elif Nested Example, more readable
def fix_refactor(moves, should):
    if moves and should:
        return "good"
    elif moves and not should:
        return "duct tape"
    elif not moves and should:
        return "WD-40"
    else:
        return "good"

#Output
print(fix_refactor(moves=True, should=False))
print(fix_refactor(moves=False, should=True))
```
#### Practice Question
```python
#Age Categorizer
def categorize_age(age):
    if age < 0: #Always begin with the extreme situation possible
        return "N/A"
    elif age <= 1:
        return "Baby"
    elif age <= 4:
        return "Toddler"
    elif age <= 17:
        return "Child"
    elif age <= 64:
        return "Adult"
    elif age <= 125:
        return "Senior"
    elif age > 125:
        return "N/A"

#Output
print(categorize_age(-2))
print(categorize_age(100))
```

```python
#Letter Grade
def calculator_letter_grade(percentage):
	if percentage >= 93:
		return("A")
	elif percentage >= 88:
		return("AB")
	elif percentage >= 80:
		return("B")
	elif percentage >= 75:
		return("BC")
	elif percentage >= 70:
		return("C")
	elif percentage >= 60:
		return("D")
	else:
		return("F")

#Output:
print(calculator_letter_grade(90))
print(calculator_letter_grade(70))
```

```python
#Date Printer
#Month Converter
def month_to_str(month): # fruitful function!
    if month == 1:
        return "Jan"
    elif month == 2:
        return "Feb"
    elif month == 3:
        return "Mar"
    elif month == 4:
        return "Apr"
    elif month == 5:
        return "May"
    elif month == 6:
        return "Jun"
    elif month == 7:
        return "Jul"
    elif month == 8:
        return "Aug"
    elif month == 9:
        return "Sep"
    elif month == 10:
        return "Oct"
    elif month == 11:
        return "Nov"
    elif month == 12:
        return "Dec"
    else:
        return "N/A"

#Day Converter
def day_to_str(day):
    last_digit = day % 10
    if day == 11 or day == 12 or day == 13:
	    return str(day)
    elif last_digit == 1:
        return str(day) + "st"
    elif last_digit == 2:
        return str(day) + "nd"
    elif last_digit == 3:
        return str(day) + "rd"
    else: 
        return str(day) + "th"

def year_to_str(year):
    if year < 2000:
        return str(year)
    else:
        last_two = str(year % 100)
        if len(last_two) < 2:
            last_two = '0' + last_two
        return "'" + last_two

def format_date(year = 2021, month = 1, day = 1): #Puts up all conditions
    return month_to_str(month) + " " + day_to_str(day) + " of " + year_to_str(year)
    
print(format_date())
print(format_date(2007))
print(format_date(day = 23, year = 2006, month = 9))
print(format_date(2022, 2, 11))
print(format_date(1997, 10, 22))
print(format_date(1497, 6, 8))
```

```python
#Team Chears - Boo or Yay
team = "Gophers"

print(team == "Gophers" or team == "Hawkeyes" or team == "Bulldogs")
if team == "Gophers" or team == "Hawkeyes" or team == "Spartans":  
    print ("boo!!")
else:
    print("yay!!")
```
> Remember every `comparison` needs to add `variable` in front

```python
#Boolean Question
#x and y
def g(x,y):
    if x: #Check if x = True (with Value) or x = False  (without Value)
        if y: #Same as x
            return True #True, True
        else:
            return False #True, False
    else:
        return False #False, True or False, True
```
