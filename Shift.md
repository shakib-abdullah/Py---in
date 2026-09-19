Learning python  in the best way swaping from javascript 



তোমার দেওয়া ৮টা topic-ই cover করব। তবে Python-এর কিছু জিনিস তোমার list-এর চেয়ে একটু আলাদা:

* `switch-case` → Python-এ `match-case`
* `do-while` → Python-এ নেই
* Array → মূলত `list`
* Object → `dict`
* `try-catch` → `try-except`
* Pointer → Python-এ C/C++-এর মতো explicit pointer নেই
* `===` → Python-এ নেই; `==` value comparison, `is` identity comparison

চলো **Python Crash Course — JavaScript/C++ developer-এর জন্য** হিসেবে শুরু করি।

---

# 0. প্রথমে Python-এর Mental Model

JavaScript:

```js
let name = "Shakib";
let age = 22;

console.log(name);
console.log(age);
```

Python:

```python
name = "Shakib"
age = 22

print(name)
print(age)
```

Python-এ সবচেয়ে noticeable ব্যাপার:

### `{}` দিয়ে block না

JavaScript:

```js
if (age >= 18) {
    console.log("Adult");
}
```

Python:

```python
if age >= 18:
    print("Adult")
```

এখানে `:` এর পরে **indentation** block তৈরি করে।

```python
if age >= 18:
    print("Adult")
    print("You can vote")
```

এখানে দুইটা `print`-ই `if`-এর ভিতরে।

---

# 1. Syntax & Basics

## Variable

JS:

```js
let name = "Shakib";
const age = 22;
```

Python:

```python
name = "Shakib"
age = 22
```

Python-এ সাধারণ variable declaration-এর জন্য `let`, `const` লাগে না।

```python
name = "Shakib"
name = "Rahim"
```

এটা valid।

---

# Data Types

Python-এর basic types:

```python
name = "Shakib"       # str
age = 22              # int
height = 5.8          # float
is_student = True     # bool
```

JS-এর সাথে:

| Python  | JavaScript           |
| ------- | -------------------- |
| `int`   | `number`             |
| `float` | `number`             |
| `str`   | `string`             |
| `bool`  | `boolean`            |
| `None`  | `null` / `undefined` |

একটা important difference:

Python:

```python
age = 22
print(type(age))
```

Output:

```text
<class 'int'>
```

JS:

```js
console.log(typeof age);
```

---

# Type Conversion

Python:

```python
age = "22"

age = int(age)

print(age + 5)
```

Output:

```text
27
```

JS:

```js
let age = "22";

age = Number(age);

console.log(age + 5);
```

আর:

```python
str(100)
float("3.14")
bool(1)
```

JS:

```js
String(100)
Number("3.14")
Boolean(1)
```

---

# Operators

## Arithmetic

```python
a = 10
b = 3

print(a + b)
print(a - b)
print(a * b)
print(a / b)
print(a // b)
print(a % b)
print(a ** b)
```

শেষ দুটো important:

```python
10 // 3
```

= `3`

এটা integer/floor division.

```python
2 ** 3
```

= `8`

JavaScript-এ:

```js
10 / 3
```

= `3.333...`

এবং power:

```js
2 ** 3
```

---

# Comparison

```python
a == b
a != b
a > b
a < b
a >= b
a <= b
```

JS-এর সাথে বড় difference:

JavaScript:

```js
5 === 5
```

Python:

```python
5 == 5
```

Python-এ `===` নেই।

---

# Logical Operators

Python:

```python
age >= 18 and age <= 30
```

JS:

```js
age >= 18 && age <= 30
```

Python:

```python
age < 18 or age > 60
```

JS:

```js
age < 18 || age > 60
```

Python:

```python
not is_student
```

JS:

```js
!isStudent
```

### মনে রাখবে

```text
Python       JS
and          &&
or           ||
not          !
```

---

# 2. Control Flow

## if / elif / else

JS:

```js
if (age >= 18) {
    console.log("Adult");
} else if (age >= 13) {
    console.log("Teenager");
} else {
    console.log("Child");
}
```

Python:

```python
if age >= 18:
    print("Adult")
elif age >= 13:
    print("Teenager")
else:
    print("Child")
```

Python-এ `else if` না।

হয়:

```python
elif
```

---

# Python-এর switch-case equivalent

Python 3.10+ এ:

```python
day = 2

match day:
    case 1:
        print("Monday")
    case 2:
        print("Tuesday")
    case 3:
        print("Wednesday")
    case _:
        print("Invalid")
```

JavaScript:

```js
switch(day) {
    case 1:
        console.log("Monday");
        break;

    case 2:
        console.log("Tuesday");
        break;

    default:
        console.log("Invalid");
}
```

Python-এর `match-case` অনেক cleaner।

---

# do-while?

Python-এ **do-while নেই**।

C++:

```cpp
do {
    cout << "Hello";
} while(condition);
```

Python-এ সাধারণত:

```python
while True:
    age = int(input("Age: "))

    if age >= 18:
        break
```

---

# for loop

JavaScript:

```js
for(let i = 0; i < 5; i++) {
    console.log(i);
}
```

Python:

```python
for i in range(5):
    print(i)
```

Output:

```text
0
1
2
3
4
```

### `range()`

```python
range(5)
```

মানে:

```text
0 1 2 3 4
```

```python
range(2, 6)
```

মানে:

```text
2 3 4 5
```

```python
range(2, 10, 2)
```

মানে:

```text
2 4 6 8
```

---

# while

JS:

```js
let i = 0;

while(i < 5) {
    console.log(i);
    i++;
}
```

Python:

```python
i = 0

while i < 5:
    print(i)
    i += 1
```

Python-এ `i++` নেই।

---

# 3. Data Structures

এটা Python-এর সবচেয়ে important অংশগুলোর একটা।

---

# List = JavaScript Array-এর মতো

JS:

```js
let fruits = ["apple", "banana", "mango"];
```

Python:

```python
fruits = ["apple", "banana", "mango"]
```

Access:

```python
print(fruits[0])
```

Output:

```text
apple
```

শেষ element:

Python:

```python
print(fruits[-1])
```

JS-এ traditionally:

```js
fruits[fruits.length - 1]
```

Modern JS-এ:

```js
fruits.at(-1)
```

Python এখানে বেশ convenient।

---

# List modify

```python
fruits.append("orange")
```

JS:

```js
fruits.push("orange")
```

Python:

```python
fruits.pop()
```

JS:

```js
fruits.pop()
```

Python:

```python
fruits.remove("banana")
```

JS-এ এর direct equivalent নেই; সাধারণত:

```js
fruits = fruits.filter(x => x !== "banana");
```

---

# Loop through List

Python:

```python
fruits = ["apple", "banana", "mango"]

for fruit in fruits:
    print(fruit)
```

JS:

```js
for (const fruit of fruits) {
    console.log(fruit);
}
```

Python-এর এটা খুব সুন্দর syntax:

```python
for fruit in fruits:
```

---

# Multidimensional List

JS:

```js
let matrix = [
    [1, 2, 3],
    [4, 5, 6]
];
```

Python:

```python
matrix = [
    [1, 2, 3],
    [4, 5, 6]
]
```

Access:

```python
print(matrix[0][1])
```

Output:

```text
2
```

Exactly JS-এর মতো।

---

# String

```python
name = "Shakib"
```

Access:

```python
print(name[0])
```

Output:

```text
S
```

Length:

```python
len(name)
```

JS:

```js
name.length
```

---

# String slicing

Python-এর অসাধারণ একটা feature:

```python
name = "Shakib"

print(name[0:3])
```

Output:

```text
Sha
```

Structure:

```text
[start : end]
```

`end` included না।

আর:

```python
print(name[:3])
print(name[2:])
print(name[:])
```

---

# Search

```python
name = "Shakib"

print("ak" in name)
```

Output:

```text
True
```

JS:

```js
name.includes("ak")
```

Python:

```python
"ak" in name
```

---

# String methods

```python
name.upper()
name.lower()
name.strip()
name.replace("S", "M")
```

JS:

```js
name.toUpperCase()
name.toLowerCase()
name.trim()
name.replace("S", "M")
```

---

# f-string — খুব important

Python-এ JS template literal-এর মতো:

JS:

```js
let name = "Shakib";
let age = 22;

console.log(`My name is ${name}, age ${age}`);
```

Python:

```python
name = "Shakib"
age = 22

print(f"My name is {name}, age {age}")
```

Python project-এ এটা প্রচুর ব্যবহার করবে।

---

# Dictionary = JS Object

JS:

```js
const user = {
    name: "Shakib",
    age: 22,
    isStudent: true
};
```

Python:

```python
user = {
    "name": "Shakib",
    "age": 22,
    "is_student": True
}
```

Access:

```python
print(user["name"])
```

JS:

```js
console.log(user.name);
```

অথবা:

```python
print(user.get("name"))
```

---

# Add / Update

```python
user["age"] = 23

user["city"] = "Dhaka"
```

JS:

```js
user.age = 23;
user.city = "Dhaka";
```

---

# Dictionary loop

```python
for key, value in user.items():
    print(key, value)
```

JS:

```js
for (const [key, value] of Object.entries(user)) {
    console.log(key, value);
}
```

---

# List of Dictionaries

Backend development-এ এটা খুব useful।

```python
users = [
    {
        "name": "Shakib",
        "age": 22
    },
    {
        "name": "Rahim",
        "age": 25
    }
]
```

তারপর:

```python
for user in users:
    print(user["name"])
```

এটা JSON data-এর মতোই দেখতে।

---

# 4. Functions

JS:

```js
function add(a, b) {
    return a + b;
}
```

Python:

```python
def add(a, b):
    return a + b
```

Call:

```python
result = add(10, 20)

print(result)
```

---

# Default Parameter

JS:

```js
function greet(name = "Guest") {
    console.log(`Hello ${name}`);
}
```

Python:

```python
def greet(name="Guest"):
    print(f"Hello {name}")
```

---

# Python Type Hint

তুমি যেহেতু TypeScript শিখছ, এটা interesting লাগবে।

Python:

```python
def add(a: int, b: int) -> int:
    return a + b
```

TypeScript:

```ts
function add(a: number, b: number): number {
    return a + b;
}
```

কিন্তু একটা important difference:

Python-এর type hint **TypeScript-এর মতো compile-time strict enforcement দেয় না**।

---

# Scope

```python
x = 10

def test():
    y = 20
    print(x)
    print(y)

test()
```

`x` global, `y` local।

JS-এর মতোই basic concept।

---

# Recursion

C++/JS-এর মতো:

```python
def countdown(n):
    if n == 0:
        return

    print(n)
    countdown(n - 1)

countdown(5)
```

Output:

```text
5
4
3
2
1
```

Conceptটা একই।

---

# 5. OOP

এখানে Python একটু আলাদা syntax ব্যবহার করে।

## Class

JS:

```js
class User {
    constructor(name, age) {
        this.name = name;
        this.age = age;
    }

    greet() {
        console.log(`Hello ${this.name}`);
    }
}
```

Python:

```python
class User:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def greet(self):
        print(f"Hello {self.name}")
```

Object:

```python
user1 = User("Shakib", 22)

user1.greet()
```

---

# `self` কী?

এটা beginner-দের সবচেয়ে confusing জিনিস।

Python:

```python
class User:
    def __init__(self, name):
        self.name = name
```

`self` roughly JavaScript-এর:

```js
this
```

এর equivalent।

অর্থাৎ:

```python
self.name
```

≈

```js
this.name
```

---

# Inheritance

Python:

```python
class Animal:
    def speak(self):
        print("Animal speaks")


class Dog(Animal):
    def bark(self):
        print("Dog barks")
```

এখন:

```python
dog = Dog()

dog.speak()
dog.bark()
```

Dog `Animal` থেকে `speak()` পেয়েছে।

JS:

```js
class Animal {
    speak() {
        console.log("Animal speaks");
    }
}

class Dog extends Animal {
    bark() {
        console.log("Dog barks");
    }
}
```

---

# Polymorphism

Python:

```python
class Dog:
    def speak(self):
        print("Woof")


class Cat:
    def speak(self):
        print("Meow")


animals = [Dog(), Cat()]

for animal in animals:
    animal.speak()
```

Output:

```text
Woof
Meow
```

একই method:

```python
speak()
```

কিন্তু object অনুযায়ী behaviour আলাদা।

---

# Encapsulation

Python-এ:

```python
class BankAccount:
    def __init__(self):
        self.__balance = 0

    def deposit(self, amount):
        self.__balance += amount

    def get_balance(self):
        return self.__balance
```

`__balance` name mangling-এর মাধ্যমে বাইরে direct access কঠিন করে।

তবে Python-এর encapsulation Java/C++/TypeScript-এর `private` ধারণার মতো strict নয়।

---

# Abstraction

Python-এ `abc` module ব্যবহার করা যায়:

```python
from abc import ABC, abstractmethod

class Animal(ABC):

    @abstractmethod
    def speak(self):
        pass
```

তারপর child class-কে `speak()` implement করতে হবে।

---

# 6. Error Handling

JavaScript:

```js
try {
    riskyCode();
} catch(error) {
    console.log(error);
}
```

Python:

```python
try:
    x = 10 / 0
except:
    print("Something went wrong")
```

কিন্তু ভালো practice:

```python
try:
    x = 10 / 0

except ZeroDivisionError:
    print("Cannot divide by zero")
```

---

# Multiple exceptions

```python
try:
    age = int(input("Enter age: "))

except ValueError:
    print("Please enter a number")
```

Python-এর:

```python
except
```

≈ JS-এর:

```js
catch
```

---

# finally

```python
try:
    print("Working")

except Exception:
    print("Error")

finally:
    print("Finished")
```

JS-এও:

```js
try {

} catch(error) {

} finally {

}
```

---

# 7. File I/O

এটা Python-এ খুব easy।

## Write

```python
file = open("data.txt", "w")

file.write("Hello Python")

file.close()
```

Read:

```python
file = open("data.txt", "r")

data = file.read()

print(data)

file.close()
```

কিন্তু modern Python-এ better:

```python
with open("data.txt", "w") as file:
    file.write("Hello Python")
```

Read:

```python
with open("data.txt", "r") as file:
    data = file.read()

print(data)
```

`with` automatically file close করে।

---

# JSON

Backend/API কাজের জন্য এটা খুব important।

```python
import json

user = {
    "name": "Shakib",
    "age": 22
}

with open("user.json", "w") as file:
    json.dump(user, file)
```

Read:

```python
with open("user.json", "r") as file:
    user = json.load(file)

print(user["name"])
```

তুমি যেহেতু Node/Express জানো, এটা খুব familiar লাগবে।

---

# 8. Memory Management / Pointer

এখানে **C/C++ এবং Python-এর সবচেয়ে বড় পার্থক্যগুলোর একটি**।

C++:

```cpp
int x = 10;

int* ptr = &x;
```

এখানে তুমি memory address নিয়ে কাজ করতে পারো।

Python-এ সাধারণত:

```python
x = 10
y = x
```

Python নিজে memory management করে।

তুমি সাধারণ application development-এ এমন লিখবে না:

```text
memory address → pointer → malloc → free
```

C++:

```cpp
int* arr = new int[10];

delete[] arr;
```

Python:

```python
arr = [0] * 10
```

Python-এর garbage collector / memory management system unused objects-এর memory automatically manage করে।

তাই Python শেখার সময় **C/C++ pointer deeply শেখার দরকার নেই** যদি তোমার immediate goal Python backend/AI/automation হয়।

তবে reference concept বুঝতে হবে।

---

# Python Reference Concept

```python
a = [1, 2, 3]
b = a

b.append(4)

print(a)
```

Output:

```text
[1, 2, 3, 4]
```

কারণ `a` এবং `b` একই list object-কে reference করছে।

C++-এর pointer/reference concept-এর সাথে mental connection করতে পারো, যদিও Python implementation আলাদা।

---

# সবচেয়ে Important Python Cheat Sheet

তোমার JavaScript knowledge থেকে Python-এ এভাবে map করো:

| JavaScript         | Python                |   |      |
| ------------------ | --------------------- | - | ---- |
| `let x = 10`       | `x = 10`              |   |      |
| `const x = 10`     | `x = 10`              |   |      |
| `console.log()`    | `print()`             |   |      |
| `typeof x`         | `type(x)`             |   |      |
| `number`           | `int`, `float`        |   |      |
| `string`           | `str`                 |   |      |
| `boolean`          | `bool`                |   |      |
| `null`             | `None`                |   |      |
| `true`             | `True`                |   |      |
| `false`            | `False`               |   |      |
| `&&`               | `and`                 |   |      |
| `                  |                       | ` | `or` |
| `!`                | `not`                 |   |      |
| `===`              | `==`                  |   |      |
| `Array`            | `list`                |   |      |
| `Object`           | `dict`                |   |      |
| `.push()`          | `.append()`           |   |      |
| `.length`          | `len()`               |   |      |
| `.includes()`      | `in`                  |   |      |
| `function`         | `def`                 |   |      |
| `this`             | `self`                |   |      |
| `class`            | `class`               |   |      |
| `extends`          | `class Child(Parent)` |   |      |
| `try/catch`        | `try/except`          |   |      |
| `finally`          | `finally`             |   |      |
| `JSON.parse()`     | `json.loads()`        |   |      |
| `JSON.stringify()` | `json.dumps()`        |   |      |
| `switch`           | `match`               |   |      |
| `do while`         | নেই                   |   |      |

---

# এখন তোমার জন্য Fast Learning Order

তোমার ক্ষেত্রে আমি **এই order-এ শিখতে বলব**, কারণ তুমি already JS/C++ জানো:

### Phase 1 — 1 দিন

```text
Variables
Data Types
Operators
if/elif/else
for
while
range()
```

### Phase 2 — 1–2 দিন

```text
list
tuple
set
dict
string
slicing
list/dict methods
```

### Phase 3 — 1 দিন

```text
functions
parameters
return
scope
lambda
list comprehension
```

### Phase 4 — 1 দিন

```text
OOP
class
__init__
self
inheritance
polymorphism
```

### Phase 5 — 1 দিন

```text
try/except
file I/O
JSON
modules
import
pip
virtual environment
```

### তারপর

তখন আর "Python syntax শেখা" নিয়ে পড়ে থাকবে না।

**Project দিয়ে Python শেখা শুরু করবে।**

যেমন:

```text
Python
   ↓
Requests
   ↓
JSON/API
   ↓
FastAPI
   ↓
Database
   ↓
Authentication
   ↓
AI/ML integration
```

তোমার existing JavaScript/Next.js background থাকার কারণে **Python syntax-এর জন্য মাসখানেক লাগার কথা না**। তোমার মূল কাজ হবে নতুন syntax-এর সাথে পরিচিত হওয়া এবং Python-এর idiomatic features—বিশেষ করে `list/dict`, slicing, comprehensions, exceptions, modules—আয়ত্ত করা।

**পরের ধাপে আমরা এটাকে আরও practical করি:** আমি তোমাকে একদম **Lesson 1 → Exercise → তুমি code লিখবে → আমি correction করব → Lesson 2** এইভাবে Python শেখাতে পারি। প্রথম lesson-এ শুধু **variable + data type + operator + if/else + loop** নিয়ে JS বনাম Python comparison করে ১০–১৫টা ছোট problem করব।
