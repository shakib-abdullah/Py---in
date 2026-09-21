
## 🧪 Python Basic Clearance Test — 20 Questions



# 🏆 কীভাবে বুঝবে তোমার Basic Clear?

আমি এভাবে evaluate করব:

| Questions | তোমার Level                        |
| --------- | ---------------------------------- |
| 1–5       | Basic syntax/logic                 |
| 6–10      | Basic + data structures            |
| 11–15     | **Good Python foundation**         |
| 16–18     | **Strong basic programming**       |
| 19        | Python-specific concepts           |
| 20        | **Basic Python practically clear** |

### আমার suggestion

**২০টার সবগুলো একসাথে solve করার দরকার নেই।**

প্রথমে **1 → 5 → 10 → 15 → 20** এই পাঁচটা milestone হিসেবে করো।




### 🟢 Level 1 — Syntax + Logic

**1. Even / Odd**

User থেকে একটা integer নাও। Output করবে:

```text
Even
```

অথবা

```text
Odd
```

**Condition:** `if-else` এবং `%` ব্যবহার করবে।

---

**2. Grade Calculator**

একজন student-এর marks input নাও।

```text
80-100 → A+
70-79  → A
60-69  → B
50-59  → C
40-49  → D
<40    → F
```

Invalid marks যেমন `105` বা `-5` হলে `Invalid Marks` দেখাবে।

---

**3. 1 থেকে N পর্যন্ত**

User `N` দিলে:

```text
N = 10
```

output:

```text
1 2 3 4 5 6 7 8 9 10
```

তারপর একই program-এ:

* 1 থেকে N পর্যন্ত sum
* কতগুলো even
* কতগুলো odd

বের করো।

---

**4. Multiplication Table**

User একটা number দিলে তার multiplication table print করো।

যেমন:

```text
Enter: 7

7 x 1 = 7
7 x 2 = 14
...
7 x 10 = 70
```

---

### 🟡 Level 2 — List + String

Python-এর list indexing, slicing এবং mutation-এর ওপর official documentation-এও বিশেষভাবে জোর দেওয়া হয়েছে। ([Python documentation][3])

**5. List Statistics**

এই list:

```python
numbers = [12, 5, 8, 20, 3, 15, 7, 10]
```

কোনো built-in `max()` / `min()` / `sum()` ব্যবহার না করে বের করো:

```text
Largest = ?
Smallest = ?
Total = ?
Average = ?
```

---

**6. Even Numbers থেকে নতুন List**

```python
numbers = [3, 8, 11, 20, 7, 14, 2, 9, 6]
```

Output:

```python
[8, 20, 14, 2, 6]
```

প্রথমে normal `for` loop দিয়ে করো।

তারপর পারলে **list comprehension** দিয়ে দ্বিতীয়বার করো।

List comprehension Python-এর standard data-structure toolkit-এর অংশ। ([Python documentation][2])

---

**7. Duplicate Remove**

```python
numbers = [1, 2, 3, 2, 4, 1, 5, 3, 6]
```

Output:

```python
[1, 2, 3, 4, 5, 6]
```

**শর্ত:** নতুন list তৈরি করে loop দিয়ে solve করো। শুধু `set()` দিয়ে shortcut নিও না।

---

**8. String Analysis**

User একটা string input দেবে:

```text
Hello Python World
```

তোমাকে বের করতে হবে:

```text
Total characters: ?
Total vowels: ?
Total consonants: ?
Total spaces: ?
```

Case-insensitive হতে হবে।

---

**9. Reverse String**

```text
Input: Python
Output: nohtyP
```

প্রথমে loop দিয়ে করার চেষ্টা করো।

তারপর Python slicing ব্যবহার করে one-liner করার চেষ্টা করো।

---

### 🟠 Level 3 — Dictionary

Python-এর dictionary এবং `.items()` দিয়ে key-value iteration official tutorial-এর core data-structure material-এর অংশ। ([Python documentation][4])

**10. Student Dictionary**

এই data:

```python
student = {
    "name": "Shakib",
    "math": 85,
    "english": 72,
    "python": 91
}
```

Program এমন output করবে:

```text
Name: Shakib
Math: 85
English: 72
Python: 91
Average: 82.67
Highest Subject: Python
```

---

**11. Word Frequency Counter**

Input:

```text
python is easy and python is powerful
```

Output-এর concept:

```python
{
    "python": 2,
    "is": 2,
    "easy": 1,
    "and": 1,
    "powerful": 1
}
```

অর্থাৎ **প্রতিটি word কতবার এসেছে** সেটা dictionary-তে রাখবে।

এই problemটা basic `dict + string + loop` একসাথে test করবে।

---

**12. Product Inventory**

```python
products = {
    "laptop": 5,
    "mouse": 12,
    "keyboard": 3,
    "monitor": 0
}
```

Program:

1. কোন product-এর stock `0` সেটা দেখাবে।
2. সবচেয়ে বেশি stock কোন product-এ সেটা দেখাবে।
3. মোট stock কত সেটা দেখাবে।

---

### 🔵 Level 4 — Functions

Established Python function exercises-এ maximum, list sum, multiplication, string reversal-এর মতো problems commonly used হয়। ([w3resource][5])

**13. Function দিয়ে তিনটার Maximum**

Function:

```python
find_max(a, b, c)
```

তৈরি করো।

Example:

```text
find_max(10, 25, 17)
→ 25
```

**শর্ত:** `max()` ব্যবহার করবে না।

---

**14. Prime Number Function**

Function:

```python
is_prime(n)
```

এটা `True` বা `False` return করবে।

```text
is_prime(7) → True
is_prime(10) → False
is_prime(2) → True
is_prime(1) → False
```

---

**15. Factorial**

Function:

```python
factorial(n)
```

Example:

```text
factorial(5) → 120
factorial(0) → 1
```

প্রথমে loop দিয়ে।

তারপর চাইলে recursion দিয়ে দ্বিতীয় version বানাও।

---

### 🔴 Level 5 — একটু Real Programming

**16. Student Management Mini Program**

একটা list of dictionaries:

```python
students = [
    {"name": "Rahim", "marks": 78},
    {"name": "Karim", "marks": 91},
    {"name": "Sakib", "marks": 65},
    {"name": "Nabil", "marks": 88}
]
```

Program থেকে বের করবে:

```text
Average marks
Highest marks student
Lowest marks student
Passed students
Failed students
```

এখানে **list + dict + loop + condition** একসাথে লাগবে।

---

**17. Number Guessing Game**

Program একটা random number generate করবে `1–100` এর মধ্যে।

User guess করবে।

Program বলবে:

```text
Too high
```

অথবা:

```text
Too low
```

অথবা:

```text
Correct!
```

Correct না হওয়া পর্যন্ত চলবে।

Bonus:

```text
Attempts: 7
```

দেখাবে।

এখানে `while`, `if`, variable, input এবং module ব্যবহার হবে।

---

**18. Simple ATM**

একটা starting balance:

```python
balance = 10000
```

Menu:

```text
1. Check Balance
2. Deposit
3. Withdraw
4. Exit
```

User যতক্ষণ `Exit` না দেয় ততক্ষণ program চলবে।

Rules:

* Withdraw > balance → `Insufficient Balance`
* Deposit negative → `Invalid Amount`
* Invalid menu → `Invalid Option`

এটা পারলে basic control flow বেশ ভালোভাবে বোঝা হয়েছে ধরে নিতে পারবে।

---

### 🟣 Level 6 — Python-Specific Thinking

**19. List থেকে Dictionary বানাও**

Input:

```python
names = ["Rahim", "Karim", "Nabil"]
marks = [75, 88, 92]
```

Output:

```python
{
    "Rahim": 75,
    "Karim": 88,
    "Nabil": 92
}
```

এখানে চেষ্টা করো:

**Version 1:** normal loop

**Version 2:** `zip()` ব্যবহার করে।

Python-এর official tutorial-এ `zip()` একাধিক sequence একসাথে iterate করার standard technique হিসেবে দেখানো হয়েছে। ([Python documentation][4])

---

**20. 🔥 Final Challenge — Expense Tracker**

এটা তোমার **final basic-clearance test**।

এই ধরনের data ধরো:

```python
expenses = [
    {"title": "Lunch", "amount": 120},
    {"title": "Bus", "amount": 50},
    {"title": "Book", "amount": 300},
    {"title": "Coffee", "amount": 100},
    {"title": "Bus", "amount": 50}
]
```

Program-এর মাধ্যমে বের করবে:

```text
Total Expense: 620
Highest Expense: Book - 300
Lowest Expense: Bus - 50
Average Expense: 124
```

তারপর user নতুন expense add করতে পারবে:

```text
Enter title: Internet
Enter amount: 500
```

এবং সেটা list-এর মধ্যে dictionary হিসেবে add হবে।

শেষে পুরো expense list print করবে।

---



আর এগুলো আমি হুবহু কোনো এক source থেকে copy করিনি; official Python concepts এবং W3Resource-এর established exercise categories/problem patterns থেকে diagnostic set হিসেবে সাজিয়েছি। W3Resource-এ হাজার হাজার Python practice problem আছে, যার মধ্যে basics, control flow, lists, dictionaries, functions, exceptions, OOP—সব আলাদা করে covered। ([w3resource][6])

[Python Official Tutorial](https://docs.python.org/3/tutorial/?utm_source=chatgpt.com) · [W3Resource Python Exercises](https://www.w3resource.com/python-exercises/?utm_source=chatgpt.com)

[1]: https://docs.python.org/bn-in/3.12/tutorial/index.html?utm_source=chatgpt.com "The Python Tutorial — Python 3.12.14 documentation"
[2]: https://docs.python.org/3.13/tutorial/?utm_source=chatgpt.com "The Python Tutorial — Python 3.13.15 documentation"
[3]: https://docs.python.org/bn-in/3.14/tutorial/introduction.html?utm_source=chatgpt.com "3. An Informal Introduction to Python — Python 3.14.7 documentation"
[4]: https://docs.python.org/bn-in/3.10/tutorial/datastructures.html?utm_source=chatgpt.com "5. Data Structures — Python 3.10.21 documentation"
[5]: https://www.w3resource.com/python-exercises/python-functions-exercises.php?utm_source=chatgpt.com "Python functions - Exercises, Practice, Solution - w3resource"
[6]: https://www.w3resource.com/python-exercises/?utm_source=chatgpt.com "Python Exercises, Practice, Solution - w3resource"
