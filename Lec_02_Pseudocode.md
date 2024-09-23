> **Topics**: Pseudocode(Algorithm); Control Flow (Order Execution) & Exceptions; State; Parameter; Argument
> Worksheet: [Worksheet_Sep06](https://git.doit.wisc.edu/cdis/cs/courses/cs220/cs220-lecture-material/-/tree/main/f23/Common_to_all_lectures/02_Pseudocode/lec-02-worksheet-solution.pdf)(All Questions In-notes)

- **Pseudocode (Algorithm)**: Step-by-step instructions to solve a problem
	- **Control Flow (General Case)**: In order, sequential execution
	- Exceptions
		- Conditionals (OR)
		- Loops (Repetition)
		- Functions (Mini Programs)
	- **State**: List of Var. and their Values\
- **Parameter**: Special Variable
- **Argument**: Value gets into a parameter

#### Worksheet
**E.g.1: General Algorithm**
```python
#State
X = 10

#Code1: Add 1 to "X"
X = X + 1

#Code2: Add 2 to "X"
X = X + 2

#Code3: Double the value of X
X = 2 * X

#Solution
print(X)
```

**E.g.2: Inefficient Example**
```python
#State
In = 4
Out = 0

#Code1: Put 1 as "Out" Value
Out = 1

#Code2: Multiply the "Out" Value by "In" Value
Out = Out1 * In

#Code3: Multiply the "Out" Value by "In" Value
Out = Out * In

#Code5: Multiply the "Out" Value by "In" Value
Out = Out * In

#Solution
print(Out)
```

**E.g.3: Concatenation** 
```python
#State
first = "Ada"
last = "Lovelace"
msg = "Hello"

#Code1: Add the "first" value to "msg"
msg = msg + first

#Code2: Add the "last" value to "msg"
msg = msg + last

#Solution
print(msg)
```
>No space between "HelloAdaLovelace"

**E.g.3 Concatenation with Space**
```python
#State
first = "Ada"
last = "Lovelace"
msg = "Hello"

#Code:
msg = msg + " " + first + " " + last

#Solution
print(msg)
```

**E.g.4: Conditional**
```python
#State
X = -4
Abs = 0

#Code1: If the "X" value is negative, continue to Code2, otherwise skip to Code3
#Since "X" < 0, continue to Code2
if X < 0:

#Code2: Mutiply the "X" value by -1, and put back to "X"
	X = X * -1

#Code3: Copy the "X" value to Abs
Abs = X

#Solution
print(Abs)
``` 

**E.g.5 Conditional**
```python
#State
age = 150
msg = "success"

#Code1: If value in "age" is less than 0, continute to Code2, otherwise skip to Code3
#Code2: Put "too young" in "msg"
#Code3: If the "age" value > 125, continue to Code4, otherwise skip Code4 and finish
#Code4: Put "too old" in "msg"
if age <0:
	msg = "too young"
else:
	if age > 125:
		msg = "too old"

#Solution
print(msg)
```

**E.g.6 Loop**
```python
#State
N = 4
total = 0
answer = 0

#Code1: Put 1 in "total"
total = 1

#Code2: If "N" = 1, skip to Code6, otherwise continue to Code3
while N != 1:

#Code3: Mutiply the "total" value by "N" value, and put the result back in "total"
	total = total * N

#Code4: Decrease the value in "N" by 1
	N = N - 1

#Code5: Go to Code2
#looping

#Code6: Copy the "total" value to "answer"
answer = total

print(answer)
```
> Same as $4!$ in math

**E.g.7 Function**
```python
#State
num1 = 4
num2 = 5

#Function with two arguments
#Define function
def add_numbers(num1, num2):
	sum = num1 + num2
	#Print function solution
	print("Sum: ", sum)

add_numbers(5, 4)
```

**E.g.8 Lists**
```python
#State
items = [9, 1, 3, 5, 7]
sorted_items = []
output = 0

#Code1: If there are no empty box next to "sorted", skip to Code4, otherwise continue to Code2
#Code2: Write the smallest number (Not crossed off yet) in "sorted_items". Cross off the number.
#Code3: Back to Code1
#Code4: Find the number in the middle of sorted, and write it in "output"

#Conditional Statement
while len(items) > 0: #When there are number left in items_list
	smallest = min(items) #Find the smallest item
	sorted_items.append(smallest) #Add to sorted_items
	items.remove(smallest) #Crossoff from original list

middle_index = len(sorted_items) // 2
output = sorted_items[middle_index]

#Solution
print(output)
```

**E.g.9 Dictionary** 
```python
#State
scores = {
		  "alice": 175,
		  "bob": 199,
		  "cathy": 213,
		  "david": 180
}
board = {
		 "player1": "alice",
		 "player2": "bob",
		 "score1": 0,
		 "score2": 199
}
winner = ""

#Code1: Find the number in "scores" next to "player1", put in "score1"
board["score1"] = scores[board["player1"]]

#Code2: Find the number in "scores" next to "player2", put in "score2"
board["score2"] = scores[board["player2"]]

#Code3: Put "tie" in "winner" box
#Code4: If the value in "score1" > "score2", continute Code5, otherwise skip to Code6
#Code5: Copy the value in "player1" to "winner"
#Code6: If the "score2" value > "score1", continue to Code7. Otherwise, skip to Code7 and just finish
#Code7: Copy the "player2" value to "winner"

if board["score1"] == board["score2"]:
	winner = "tie"
else:
	if board["score1"] > board["score2"]:
		winner = board["player1"]
	elif board["score2"] > board["score1"]:
		winner = board["player2"]

#Solution
print("Winner: ", winner)
```