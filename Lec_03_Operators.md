>**Topics**: Values & Types; Escape Characters; Operator & Expressions; Math Operators; String Operators; Comparison Operators; Boolean Operators; Order of Operations; Comments
>**Worksheet**: [Worksheet_Sep09](https://git.doit.wisc.edu/cdis/cs/courses/cs220/cs220-lecture-material/-/blob/main/Common/03_Operators/Python%20Operators%20Exercises%20(Solution).pdf)(Review Questions In-notes

#### Python Execution Orders (Left to Right)
- **Mathematical**
	- `**`: Exponents
	- *+x, -x*: Signs
	- `*, /, //, %`: Multiply / Divide
	- `+, -`: Add / Subtract
- **Comparison**
	- `==, !=, <, <=, >, >=`: Comparison
- **Logic**
	- `not, and, or`: Boolean
#### Values and Data Types
- **Value**: Info used by a program
	- All values have associated Data Type
	- Use `type()` function to look up
- **Basic Data Type**
	- **int**: Numbers w/o. decimal point
		- E.g.: 7, -12, 52314
	- **float**: Numbers w/. decimal point
		- E.g.: 7.231, -42.314
	- **str**: Surrounded by quotation marks
		- E.g.: "Hello", "27", "Bob"
	- **bool**: True or False
- **Escape Characters**
	- `\n`: Newline
	- `\t`: Tab
	- `\'`: Literal single quotation mark
	- `\"`: Literal double quotation mark
	- `\\`: Literal slash
```python
#Escape Characters Examples_1
print("Mary said, \"Hi.\"")
print("What does\tthis do \nif I type it in.")
```
```python
#Escape Characters Examples_2
print("Mary said, \'Hello John. How are you?\'\nJohn said, \"I am doing fine. Thank you for asking.\"")
```
#### Operators
- **Operator Basics**
	- **Operator**: Math / String / Comparison / Logical
	- Operand: Data Value that Operator operates on
		- **Unary Operators**: Single Operand
		- **Binary Operators**: Two Operands
	- **Expression**: Combine of **Operator(s)** & **Operand(s)**
- **Math Operators**
	- `+`: Add
	- `-`: Subtract
	- `*`: Multiply
	- `/`: Float Division
	- `//`: Floor Division (Divide then round down to nearest whole number)
		- If one Operand is `float`, it will return `float`
	- `%`: Modulus (Returns remainder from a division operation)
	- `**`: Power Operation
```python
#Expressions_Examples
print(4 / 2)
print(5 / 2)
print(4 // 2)
print(5 // 2)
print(4.0 / 2)
print(4.0 // 2)
print(5.0 / 2)
print(5.0 // 2)
print(-5.0 // 2)
print(-(5.0 // 2))
print(0 % 3)
print(1 % 3)
print(2 % 3)
print(3 % 3)
print(4 % 3)
print(5 % 3)
print(6.1 % 3)
print(2 ** 3)
print(3 ** 4)
```
>`-5.0 // 2 = -3`: `-5.0 / 2 = -2.5`, round down to `-3`
>`a % b` when `a < b`, returns `a`
>`6.1 % 3` returns `0.09999999999999964`, which pretty much `0.1`
>When calculating `a ** b ** c`, prior `a ** (b ** c)`
```python
#Modulus % Examples
#Code1: Largest value of M % 4?
print(3)
#Code2: Smallest value of M % 4?
print(0)
#Code3: M % 2. If M is even / odd?
print("If even, M = 0; If odd, M = 1")
#Code4: What does modding by 10 tell about original number? (E.g.: 745 % 10)
print("The digit in the ones-place")
#Code5: Detect each digit of 1234
num_1 = (1234 // 1000) % 10
num_2 = (1234 // 100) % 10
num_3 = (1234 // 10) % 10
num_4 = 1234 % 10
print(num_1, ", ", num_2, ", ", num_3, ", ", num_4)
```
- **String Operators**
	- `+`: Concatenation
	- `*`: Replication
```python
#String Operators Examples
print("hello" + "goodbye")
print("3" + "4")
print(10 * "X")
print(-5 * "X")
print(True + False)
print(False * 8)
```
> `True = 1`, `False = 0`
> `"str" * "str"` will return `TypeError`
> `-# * "str"` will return `Empty Str`
- **Comparison Operators**
	- `==` Equal to
	- `!=` Not Equal to
	- `<` Lesser than
	- `<=` Lesser than Equal to
	- `>` Greater than
	- `>=` Greater than Equal to
```python
#Comparison Operators Examples
print(2 + 3 < 7)
print(2 + 3 <= 5)
print(-3 > -5)
print(3 != 3)
print(3 == 3)
print(3 == 3.0)
print("Apple" < "Bubble")
print("apple" < "Bubble")
print("Hello" < "Hi")
print(type(2 + 3) == type(8))
print("9000" < "11000")
```
>`print("9000" < "11000")`, when comparing `str`, python will compare the left-most digit. In this case, `"9" > "1"`
>`print("Hello" < "Hi")`, when comparing `str`, if the left-most digit / letter are the same, it will compare the one to its right. In this case, `"e" < "i"`.
- **Boolean Operators (Logical)**
	- `and`: Both `Boolean` be `True`
	- `or`: One of the `Boolean` be `True`
	- `not`: Flip `Boolean`
```python
#Boolean Operators Examples
print(not False)
print(False and True)
print(True or False)
print(not True or True)
print(not (True or True))
print(2 and 6 > 1)
print(6 > 1 and 2)
```
>`True or False`: At lest one `boolean` is correct, indeed it is `True`
>`print(2 and 6 > 1)`: python evaluate expressions from left to right, and returns the last evaluated returns. When facing `(8 / 0) > 0 and 2 < 4`, python will return `error` since the first evaluated operands returns `error`, and python will not move on

- **Comments**
	- `#`

### Review Questions
```python
2 ** 3 ** 2
```
>**Review:** Concept under **Math Operators**, when calculating `a ** b ** c`, prior calculate `a ** (b ** c)`

```python
2 % 3
```
>**Review**: Concept under **Math Operators**, `a % b` when `a < b`, returns `a`

```python
type(5 // 1.2)
```
> **Review**: Concept under **Math Operators**, even `//` returns the nearest whole number. If one operand is `float`, it will return `float` as result.

```python
-5 * "X"
```
> **Review**: Concept under **String Operators**, when using `-# * "str"`, python will return `Empty String`

```python
print("Hello" < "Hi")
```
>**Review:** Concept under **Comparison Operators**, python will compare left-most character / digit, if it is the same, it will compare the second character / digit

```python
0 + 0 == 1 and 1 / 0 == -100
```
```python
1 / 0 == -100 and 0 + 0 == 1
```
>**Review**: Concept under **Comparison Operators**, python reads from **left to right**, once the First Operands fails in `and` statement, it will ignore the Second Operands.

```python
print(6 > 1 and 2)
print(6 > 1 and 6 > 2)
print(2 and 6 > 1)
```
>**Review**: Concept under **Boolean Operators**
>- `print 6 > 1 and 2`, `6 > 1` returns `True`, python moves on check Second Operand. In this case, Second Operand = `2`, non-zero number consider `True`, and python returns the last evaluated operand.
>- `print 6 > 1 and 6 > 2`, both operators are `True`
>- `print 2 and 6 > 1`, `2`, non-zero number consider `True`, python moves on check Second Operand. In this case, Second Operand = `6 > 1`, returns `True`, and python returns the last evaluated operand.