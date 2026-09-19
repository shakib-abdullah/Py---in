
---

## ১. String (স্ট্রিং মেথড ও ফাংশন)

টেক্সট বা স্ট্রিং প্রসেসিংয়ের জন্য এই ফাংশন ও মেথডগুলো সবচেয়ে বেশি ব্যবহৃত হয়:

```python
text = "hello World"

# len(): স্ট্রিংয়ের দৈর্ঘ্য বা মোট ক্যারেক্টার সংখ্যা দেয়
print(len(text))              # Output: 11

# upper() & lower(): সব অক্ষর বড় বা ছোট হাতের করে
print(text.upper())           # Output: HELLO WORLD
print(text.lower())           # Output: hello world

# capitalize() & title(): প্রথম অক্ষর বা প্রতি শব্দের প্রথম অক্ষর বড় হাতের করে
print(text.capitalize())      # Output: Hello world
print(text.title())           # Output: Hello World

# strip(): লেখার শুরুতে বা শেষে থাকা অতিরিক্ত খালি জায়গা (Whitespace) মুছে ফেলে
text_with_spaces = "   python   "
print(text_with_spaces.strip()) # Output: "python"

# replace(): নির্দিষ্ট কোনো শব্দ বা অক্ষর বদলে নতুন শব্দ বসায়
print(text.replace("World", "Python")) # Output: hello Python

# split(): নির্দিষ্ট অক্ষরের ওপর ভিত্তি করে স্ট্রিং ভেঙে লিস্ট বানিয়ে ফেলে
data = "apple,banana,orange"
print(data.split(","))        # Output: ['apple', 'banana', 'orange']

# join(): লিস্টের এলিমেন্টগুলোকে জোড়া দিয়ে স্ট্রিং বানায়
words = ['Hello', 'World']
print(" ".join(words))        # Output: Hello World

# find(): নির্দিষ্ট শব্দ কত নম্বর ইনডেক্সে আছে তা বের করে (না পেলে -1 দেয়)
print(text.find("World"))     # Output: 6

# count(): কোনো অক্ষর বা শব্দ কতবার আছে তা গুনে দেয়
print(text.count("l"))        # Output: 3

# startswith() & endswith(): টেক্সটটি নির্দিষ্ট শব্দ দিয়ে শুরু/শেষ হয়েছে কিনা (True/False)
print(text.startswith("hello")) # Output: True
print(text.endswith("World"))   # Output: True

# isdigit() & isalpha(): টেক্সটটি শুধু সংখ্যা নাকি শুধু অক্ষর তা যাচাই করে
print("12345".isdigit())      # Output: True
print("Python".isalpha())     # Output: True

```

---

## ২. List (লিস্ট মেথড ও ফাংশন)

পাইথনে অ্যারে হিসেবে সাধারণত লিস্ট ব্যবহার করা হয়। ডাটা যোগ, বিয়োগ ও সাজানোর জন্য নিচের ফাংশনগুলো দরকার হয়:

```python
nums = [10, 5, 20, 15]

# len(): লিস্টে মোট কয়টি উপাদান আছে তা দেয়
print(len(nums))              # Output: 4

# append(): লিস্টের একদম শেষে নতুন এলিমেন্ট যোগ করে
nums.append(25)
print(nums)                   # Output: [10, 5, 20, 15, 25]

# insert(): নির্দিষ্ট ইনডেক্স নম্বরে উপাদান বসায়
nums.insert(1, 99)
print(nums)                   # Output: [10, 99, 5, 20, 15, 25]

# extend(): একটি লিস্টের শেষে আরেকটি লিস্টের উপাদানসমূহ যুক্ত করে
nums.extend([30, 40])
print(nums)                   # Output: [10, 99, 5, 20, 15, 25, 30, 40]

# remove(): নির্দিষ্ট ভ্যালুটির প্রথমবার পাওয়া আইটেমটি মুছে ফেলে
nums.remove(99)
print(nums)                   # Output: [10, 5, 20, 15, 25, 30, 40]

# pop(): ইনডেক্স ধরে আইটেম মুছে দেয় এবং মুছে ফেলা ভ্যালুটি রিটার্ন করে (ফাঁকা রাখলে শেষেরটা কাটে)
removed = nums.pop(0)
print(removed)                # Output: 10

# index(): কোনো ভ্যালু কত নম্বর ইনডেক্সে আছে তা বের করে
print(nums.index(20))         # Output: 2

# count(): লিস্টে কোনো ভ্যালু মোট কতবার আছে তা গুনে
print(nums.count(15))         # Output: 1

# sort(): মূল লিস্টটিকে ছোট থেকে বড় ক্রমানুসারে সাজায়
nums.sort()
print(nums)                   # Output: [5, 15, 20, 25, 30, 40]

# reverse(): লিস্টের সব এলিমেন্টের পজিশন উল্টে দেয়
nums.reverse()
print(nums)                   # Output: [40, 30, 25, 20, 15, 5]

# clear(): লিস্টের সব উপাদান মুছে খালি করে ফেলে
temp = [1, 2, 3]
temp.clear()
print(temp)                   # Output: []

```

---

## ৩. Dictionary (ডিকশনারি মেথড ও ফাংশন)

Key-Value পেয়ার নিয়ে কাজ করার জন্য ডিকশনারির মেথডগুলো ব্যবহৃত হয়:

```python
student = {"name": "Shakib", "age": 22, "dept": "CSE"}

# keys(): ডিকশনারির সব Key গুলোর লিস্ট দেয়
print(student.keys())         # Output: dict_keys(['name', 'age', 'dept'])

# values(): ডিকশনারির সব Value গুলোর লিস্ট দেয়
print(student.values())       # Output: dict_values(['Shakib', 22, 'CSE'])

# items(): Key ও Value দুটিকে একসাথে pair হিসেবে দেয়
print(student.items())        # Output: dict_items([('name', 'Shakib'), ...])

# get(): কোনো Key এর ভ্যালু নিরাপদে রিটার্ন করে (Key না থাকলে এরর না দিয়ে None দেয়)
print(student.get("age"))     # Output: 22

# update(): নতুন Key-Value যুক্ত বা আপডেট করে
student.update({"cgpa": 3.80, "age": 23})
print(student)                # Output: {'name': 'Shakib', 'age': 23, 'dept': 'CSE', 'cgpa': 3.8}

# pop(): নির্দিষ্ট Key এর জোড়াটি মুছে ভ্যালুটি রিটার্ন করে
age = student.pop("age")
print(age)                    # Output: 23

# popitem(): ডিকশনারির একদম শেষের Key-Value জোড়াটি মুছে দেয়
last_item = student.popitem()
print(last_item)              # Output: ('cgpa', 3.8)

```

---

## ৪. Tuple (টিউটপল মেথড)

টিউটপলের ডাটা পরিবর্তন করা যায় না (Immutable)। তাই এর মেথড মাত্র ২টি:

```python
tup = (10, 20, 30, 20, 40)

# count(): নির্দিষ্ট উপাদানটি কতবার আছে তা গণনা করে
print(tup.count(20))          # Output: 2

# index(): নির্দিষ্ট উপাদানের ইনডেক্স কত তা বের করে
print(tup.index(30))          # Output: 2

```

---

## ৫. Set (সেট মেথড)

অদ্বিতীয় (Unique) ভ্যালুর কালেকশন প্রসেস করার জন্য সেটের মেথডগুলো ব্যবহার করা হয়:

```python
s1 = {1, 2, 3, 4}
s2 = {3, 4, 5, 6}

# add(): সেটে নতুন এলিমেন্ট যোগ করে
s1.add(10)
print(s1)                     # Output: {1, 2, 3, 4, 10}

# remove(): সেট থেকে আইটেম মুছে ফেলে (না থাকলে KeyError দেয়)
s1.remove(10)

# discard(): সেট থেকে আইটেম মুছে ফেলে (না থাকলেও এরর দেয় না)
s1.discard(99)

# union(): দুটি সেটের সব ইউনিক এলিমেন্ট একসাথে করে
print(s1.union(s2))           # Output: {1, 2, 3, 4, 5, 6}

# intersection(): দুটি সেটের কমন এলিমেন্টগুলো দেয়
print(s1.intersection(s2))    # Output: {3, 4}

# difference(): প্রথম সেটে আছে কিন্তু দ্বিতীয় সেটে নেই এমন এলিমেন্ট দেয়
print(s1.difference(s2))      # Output: {1, 2}

```

---

## ৬. Global Built-in Functions (সাধারণ গাণিতিক ও ইউনিভার্সাল ফাংশন)

যেকোনো ডাটা টাইপের ওপর সরাসরি প্রয়োগ করার জন্য পাইথনে কিছু গ্লোবাল ফাংশন আছে:

```python
numbers = [12, 45, 2, 99, 23]

# max() & min(): সবচেয়ে বড় ও ছোট সংখ্যা খুঁজে বের করে
print(max(numbers))           # Output: 99
print(min(numbers))           # Output: 2

# sum(): তালিকার সব সংখ্যার যোগফল নির্ণয় করে
print(sum(numbers))           # Output: 181

# abs(): পরম মান (Absolute Value) দেয় (ঋণাত্মককে ধনাত্মক করে)
print(abs(-15))               # Output: 15

# round(): দশমিক সংখ্যাকে কাছাকাছি পূর্ণসংখ্যায় রাউন্ড করে
print(round(3.756, 2))        # Output: 3.76 (২ দশমিক স্থান পর্যন্ত)

# sorted(): অরিজিনাল ডাটা না বদলে নতুন সাজানো লিস্ট দেয়
print(sorted(numbers))        # Output: [2, 12, 23, 45, 99]

# range(): নির্দিষ্ট রেঞ্জের মধ্যে সংখ্যা জেনারেট করে (লুপে ব্যবহৃত হয়)
print(list(range(1, 5)))      # Output: [1, 2, 3, 4]

# type(): যেকোনো ভ্যারিয়েবলের ডাটা টাইপ চেক করে
print(type(numbers))          # Output: <class 'list'>

# input() & print(): ইনপুট নেওয়া ও আউটপুট দেখানোর জন্য
# name = input("Enter name: ")
print("Hello World")          # Output: Hello World

```