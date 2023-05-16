---
date : "2023-05-10"
title : "#6 Two Toolbox"
slug : "6-toolbox"
time : "5h-30m"
summary : "I completed the Python fundamentals track, and streamed too"
---

I accidently fell asleep early and would’ve just missed today’s progress but woke up sometime around around 2am, I decided to stream and continue learning. Finished Python Toolbox for DataScience part 1 and 2. 

There were a lot of interesting challenges and I learned a lot about iteartors and generators, I have taken a few notes but It’s already 6:45am as the time of writing. I need to get some sleep. I have already pushed myself. Will process these notes and update this post later. 

---
<aside>
💡 Tuple use cases ??

</aside>

---

- Arguments vs Parameters
    - Arguments are passed into the function
    - Parameters are written in function header
- Docstrings
    - Used to describe the function
    - Placed immediately after the function declaration
    - Written between triple quotes `"""`
- Multiple values return by function → Use a tuple

Tweets country counter project.

- Read the tweets from `tweets.csv` file.
- Load into data frame df
- Create a dictionary to store the count
- Iterate and keep updating the count

```python
# Import pandas
import pandas as pd

# Import Twitter data as DataFrame: df
df = pd.read_csv('tweets.csv')

# Initialize an empty dictionary: langs_count
langs_count = {}

# Extract column from DataFrame: col
col = df['lang']

# Iterate over lang column in DataFrame
for entry in col:

    # If the language is in langs_count, add 1 
    if entry in langs_count.keys():
        langs_count[entry]+=1
    # Else add the language to langs_count, set the value to 1
    else:
        langs_count[entry]=1

# Print the populated dictionary
print(langs_count)
```

Name Scopes defines where certain objects are accessible 

- `Global` → Main body of script
- `Local` → Inside a function
- `Built-in` → Name in pre-defined built-in modules

Keywords to change scopes 

- `global` jumps to the global scope
- `nonlocal` jumps to the next parent scope
---
<aside>
💡 Tricky question related to Name Scopes

</aside>

---

What’s the deal with built-ins 

> *Here you're going to check out Python's built-in scope, which is really just a built-in module called `builtins`. However, to query `builtins`, you'll need to `import builtins` 'because the name builtins is not itself built in…No, I’m serious!'*
> 

Nested Function 

- Moves one level upper

---
<aside>
💡 Case for Nested functions

</aside>

---

Useful for higher order functions stuff

- The function `raise_val()` returns a function rather than returning a value.
- This function can be reused later
- This is closure in computer science

```python
def raise_val(n):
	"""Return the inner func"""
	def inner(x):
		"""Return x to power of n"""
		raised = x ** n
		return raised 
	
	return inner

square = raise_val(2)
cube = raise_val(3)
print(square(2)) # 4
print(cube(2))   # 8
```

LEGB rule, search starts with local and ends in built-in. 

- Local
- Enclosing function
- Global
- Built-in

Python closure, nested function remember the state of its enclosing scope when called.

---

Arbitary number of arguments can be passed in python with `*args` and similarly keyword arguments can be with `**kwargs.`

- args is a tuple
- kwargs is a dictionary

Lambda function 

```python
f = lambda x : x + "!!!"
`print(f) #<function **main**.<lambda>(x)>`
```

map function

```python
val = map(function, iterable)
```

reduce

```python
vals = [1,2,3,4,5]
result = reduce(lambda x,y : x+y, vals)
# calculates ((((1+2)+3)+4)+5).

# If initial is present, it is placed before the items
# of the sequence in the calculation, 
# and serves as a default when the sequence is empty.
```

---
<aside>
💡 Learn about the a

</aside>

---


TIL `repertoire` stock of skills 

---

Error Handling

```python
try : 
	# do this
except :
	# if error
	# do this instead
```


# Data Science Tool box 2

## Iter(ables)(ators)

Iterable : Object that has an associated iter() method 

- Iterable is an object that can return an iterator
- Lists, Strings, Dictionaries, File contents
- When using a for loop, under the hood an iterator is created.

Iterator : Produces next value with `next()`

- Iterator is an object that keeps state and produces the next value on being called `next()`
- After the last value has been passed, calling next will result `StopIteration` error.

Splat operator is used to unpack all values at once

```python
word = 'Data'
it = iter(word)
print(*it) # D a t a

print(*it) # Error 
```
---
<aside>
💡 How does the range function work

</aside>

---

Range function 

- doesn’t actually create a list
- instead created a range object with iterator

Enumerate 

- takes an iterable and return enumerate object that pairs up items with index
- `enumerate(iterable,start=5)` starts counting from 5

Zip 

- Takes arbitary number of iterables and returns iterator of tuples
- Use it with list to create a list of tuples

```python
val = [1,2,3]
wrd = ['one','two','three']

z1 = zip(val,wrd)
print(type(z1)) #zip

x,y = zip(*z1)
print(x) #(1,2,3)
print(y) #('one','two','three')
```

Chunksize

- when data is too big to store in memory
- use `chunk` argument in `.read_csv()` method of python

### Comprehension & Generators

List comprehension is made up of

- Iterable
- Iterator
- Output Expression

Code readability is a trade-off with one liners

Dictionary comprehension

- Use `{}` brackets instead of `[]`
- `key : val` syntax is to be used

```python
pos_neg = {num: -num for num in range(3)}
print(post_neg)
# {0: 0, 1: -1, 2: -2}
```

- `[ *output expression* for *iterator variable* in *iterable* if *predicate expression* ]`
- `[output1 expression if (condition1) else output2 for iterator in iterable]`

Generator object is created using `()` with the same syntax as list comprehension.

- Doesn’t store in the memory, doesn’t construct the list
- Object we can generate over to produce elements of list as required.

Lazy Evaluation 

- evaluation of expression is delayed until its value is needed

Generator Functions

- just like regular function but instead of returning a value it `yields` a result

```python
def num_seq(n):
	i = 0
	while i<n:
		yield i
		i+=1

res = num_seq(3)
print(type(res)) # <class 'generator'>

for item in result:
	print(item)

# 0
# 1
# 2

```

Range 

- works with generator behind the scenes
- So, does `.items()` of a dictionary

List comprehension // Generator

```python
a = [x for x in range(3)]
print(a) 
# 0
# 1
# 2

b = (x for x in range(3))
for val in b:
	print(val)
# 0
# 1
# 2
```

```python
lens = ((len) for person in people)

def lens(people):
	for person in people:
		yield(len(person))

```

---

---

- Use `df.head()` to print the head of a DataFrame

Project file 

- Process data and create a graph
- Load file chunk by chunk
- create new column for urban population values
- plotting the data

```python
# Define plot_pop()
def plot_pop(filename, country_code):

    # Initialize reader object: urb_pop_reader
    urb_pop_reader = pd.read_csv(filename, chunksize=1000)

    # Initialize empty DataFrame: data
    data = pd.DataFrame()
    
    # Iterate over each DataFrame chunk
    for df_urb_pop in urb_pop_reader:
        # Check out specific country: df_pop_ceb
        df_pop_ceb = df_urb_pop[df_urb_pop['CountryCode'] == country_code]

        # Zip DataFrame columns of interest: pops
        pops = zip(df_pop_ceb['Total Population'],
                    df_pop_ceb['Urban population (% of total)'])

        # Turn zip object into list: pops_list
        pops_list = list(pops)

        # Use list comprehension to create new DataFrame column 'Total Urban Population'
        df_pop_ceb['Total Urban Population'] = [int(tup[0] * tup[1] * 0.01) for tup in pops_list]
        
        # Concatenate DataFrame chunk to the end of data: data
        data = pd.concat([data, df_pop_ceb])

    # Plot urban population data
    data.plot(kind='scatter', x='Year', y='Total Urban Population')
    plt.show()

# Set the filename: fn
fn = 'ind_pop_data.csv'

# Call plot_pop for country code 'CEB'
plot_pop('ind_pop_data.csv','CEB')

# Call plot_pop for country code 'ARB'
plot_pop('ind_pop_data.csv','ARB')
```
