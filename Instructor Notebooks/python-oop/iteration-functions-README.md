---
title: Python 202
layout: post
weight: 10
hidden: true
---
​
**Course**: Data Science <br/>
**Mod**: 1 <br/>
**Topic**: Python 202 <br/>
**Amount of time**: 1.5 hours <br/>
**Author**: Alan Hong

Ported and reformated from the ds-lesson-starters repository. Original version [here](https://github.com/learn-co-curriculum/ds-lessons-starter/tree/master/lesson-plans-by-mod/Module-1/python-202-adv-loops-functions).  

# Teacher Notes

## Introduction

This lesson covers a lot of ground! The first portion of the lesson reviews iterating over collections and basic programming concepts. This portion may be appropriate to work through quickly or skip over for an advanced class. The next portion then covers writing functions in python.

## Learning Goals

 - Revisit what for loop does, using a dictionary
 - Use `break` to adjust loop activity
 - Use nested loops to navigate a nested dictionary
 - Write a robust function that will take any nested dictionary of items, costs, and print out your shopping list, stopping when the total cost gets to high, and telling you the average cost per item in your cart.


## Prerequisite Knowledge

Some introduction to basic python data types including strings, lists and dictionaries will be needed. Students should have read something about iterations and functions to be successful in this lesson.



## Materials

* Student version of this slide deck: Iteration Functions and Stats

## Learning Goals


 - Revisit what for loop does, using a dictionary
 - Use `break` to adjust loop activity
 - Use nested loops to navigate a nested dictionary
 - Write a robust function that will take any nested dictionary of items, costs, and print out your shopping list, stopping when the total cost gets to high, and telling you the average cost per item in your cart.



# **Scenario:**
Today we are going to build upon the for loops of yesterday. Who has ever got to the cash register at costco, or whole foods, seen the total and asked "how did I spend that much?". Today we have a grocery list of items and prices, but we do not have infinite money (unfortunately), so we need to have a program that will look at our grocery list and help us manage our shopping and cost.


Let's revisit what a for loop does. Here we have a list of items, and a separate list of costs. We are going to write a loop to print each item, it's cost, and the total of our grocery list.

```
items = ['cheese', 'whole milk', 'kefir', 'tofu four-pack', 'kale', 'oranges', 'ham', 'ben & jerry's']
cost = [2.79, 3.42, 4.50, 12.00, 2.75, 3.64, 25.00, 5.29]
```

![groc-cart](https://images.pexels.com/photos/1389103/pexels-photo-1389103.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=750&w=1260)

### For loops:
First, let's create a for-loop that prints each item in the list with "I need to buy: " item.


```python
#Your code here; create a for loop that prints each item in the list with a "I need to buy: ______"
```

## Teacher Notes

Sample solution:
```python
for item in items:
   print("I need to buy : ", item)
```   

(let them figure out how to make the for loop the first way, then show them the following:)
 - Let's make that a little nicer looking:

```
print("I need to buy: ")
for item in items:
   print(" - [ ] ", item)
```

Can also use the .format() method.

Okay, we want to work through a dictionary, so what's one way to convert those two lists to a dictionary?:


## Teacher Notes

Solution:

```
items_cost = dict(zip(items, cost))
print("I need to buy: ")
for key, value in items_cost.items():
  print("- [ ] ", key, ": for $", value)
```

Now add the total grocery bill at the end:


```python
#Your code here
```

## Teacher Notes

Potential solution:
    
```python
print("I need to buy: ")
total = 0
for key, value in items_cost.items():
  print("- [ ] ", key, ": for $", value)
  total = total + value
print("total cost: $", total)
```

1. Does this look reasonable? 
2. What if you only had $25 ?  

3. How can you build it out to stop adding items when the total is over $25?

### Introducing while loops

- What does a while loop look like in Python?

```python
i = 1
while i < 6:
  print(i)
  i += 1
```
- Explain step by step how the above code is working and what you expect to see (expect to see 1,2,3,4,5 as output) before you run it in the notebook
- What is `break` and `continue`?
- Are they different? How?

# Run the following code:

```python
i = 0
while i < 6:
  i += 1
  if i == 3:
    print("foo")
    continue
  print(i)
```

## Teacher Notes

- Go step by step how the above code is working.

# Now run this code:

```python
i = 0
while i < 6:
  i += 1
  if i == 3:
    print("foo")
    break
  print(i)
```


- Why is the output different?
- It stopped at `foo`, why?

## Teacher Notes

- We can also include breaks in for-loops.
- What would we use to stop the for loop if the total reached $25?

Sample solution:

```python
print("I need to buy: ")
total = 0
for key, value in items_cost.items():
  print("- [ ] ", key, ": for $", value)
  total = total + value
  if total >= 25:
    break
print("total cost: $", total)
```

- How could you adapt your script to stop the program if an item costs more than $10 ?
    * Hint: try using `continue` and `break` clauses

## Teacher Notes

sample solution

```python
print("I need to buy: ")
total = 0
for key, value in items_cost.items():
  print("- [ ] ", key, ": for $", value)
  if value >=10:
    print(key, " costs more than $10. Revise your list")
    print("Total cost below is before including ", key)
    break
  total = total + value
print("total cost: $", total)
```

### Nested Loops

- Now let's look at a little more complicated example using nested loops.
- Take a look at this code:

```python
list = [1,2,3,4,5]

for x in list:
  print('loop1:', x)
  for y in list:
    print('loop2---', y)
```
- What do you expect to see? Why?
- Break it down what the loop is doing at each step.

## Teacher Notes

- Change some variables in the above code to check for understanding from the group

# Here's a more complicated example, what is it doing?

```python
i = 2
while(i < 100):
   j = 2
   while(j <= (i/j)):
      if not(i%j): break
      j = j + 1
   if (j > i/j) : print i, " is prime"
   i = i + 1

print "Good bye!"
```

## Teacher Notes

First, checks if i is less then 100.
Then checks if j is less then i/j. Program terminates at this point.

Make some notes regarding poor indentation of the above code. **This is not an exemplar!**

# Back to Our Shopping Cart

- Here is a more robust shopping list of nested dictionaries:

```python
shopping_dict = {'Grocieries': {'ben & jerrys': 5.29, 'cheese': 2.79,'ham': 25.0, 'kale': 2.75,'kefir': 4.5,'oranges': 3.64,'tofu four-pack': 12.0,'whole milk': 3.42},
                 'House supplies': {'toilet paper pack': 16.50, 'clorox spray': 6.43, 'kleenex': 2.50,},
                 'Pet supplies': {'Taste of the Wild': 65.20, 'squeaky toy': 4.50, 'duck feet': 8.45}}
```
- Write the nested for loops to print out each grocery list with its total

## Teacher Notes

Sample solution:

May be also worth going over alternative solutions such as using the .keys() methods of dictionaries and then finding the relevant value from the dictionary, or attempting to use list comprehensions in some way.

```python
for category in shopping_dict:
    total = sum([price for item, price in category.items()])
    print(category, total)
```

## Teacher Notes

_Informal Assessment_:<br/>
"Quick check, how confident do we feel about loops and nested loops?"
- follow up with those students who do not feel confident

# Functions

- Why would we need to write functions?
- How do we write a function in python?

## Teacher Notes

Some Reasons:
- Separation of concerns (SoC), in computer science
- Modular code!
  - repeatable
  - doing things manually is the worst
  - standardization and human error reduction


See next slide for specific example. Go over the `def` clause and its syntax.

```python
def sayHello():
  print("Hello!")
```
- How can you execute this function?

```

## Teacher Notes

```
sayHello()
```
- Let's talk about arguments or parameters.    


* Let's say we want to make this function more dynamic and print out whatever we want!   
* How we do that?

## Teacher Notes

```python
def shout(phrase):
  print(phrase + "!!!")

shout("oh hai")
```

- What if we don't pass in an argument? What happens?
- Maybe we can establish a default value for the argument in case it isn't passed in.


## Teacher Notes

```python
def shout(phrase = "oh hai"):
  print(phrase + "!!!")

shout()
shout("bye")
```

- What if we wanted to run a function, take it's output and put it in to another function?

## Teacher Notes


```
def addOne(number):
  return number + 1

def timesFive(number):
  return number * 5

numberPlusOne = addOne(1)
answer = timesFive(numberPlusOne)
print(answer)
```

- What will the above code return?


## Teacher Notes

Adapt your shopping list nested for-loop to be wrapped in a function you could call on any shopping list of nested dictionaries. 

_Informal Assessment_:<br/>
"Quick check, how confident do we feel about functions and arguments?"
- follow up with those students who do not feel confident

- Adapt your function to do the following:
    - stop the nested loop if a grocery total goes over $30
    - print out the average cost of per item in your cart
    - print out the average cost per item in category
 

## Teacher Notes

 Answer:
 
 ```
grand_tot = 0
grand_count = 0
for cat in list(shopping_dict.keys()):
    total = 0
    count = len(shopping_dict[cat].values())
    grand_count = grand_count + count
    print(cat+": ")
    for key, value in shopping_dict[cat].items():
        print("- [ ] ", key, " $", value)
        total = total + value
    average = total/count
    grand_tot=grand_tot + total
    print("average cost per {a}: ${p:8.2f}".format(a=cat,p=average))
grand_av = grand_tot/grand_count
print("average cost per item: ${p:8.2f}".format(p=grand_av))
 ```
 
 
 Just for average cost per item in category:
 
 ```
 for cat in list(shopping_dict.keys()):
     total = 0
     count = len(shopping_dict[cat].values())
     print(cat+": ")
     for key, value in shopping_dict[cat].items():
        print("- [ ] ", key, " $", value)
        total = total + value
     average = total/count
     print("average cost per {a}: ${p:8.2f}".format(a=cat,p=average))   
```

**Step**: Reflection <br/>
**Time**: 10 min <br/>
Ask the class and discuss as a group:
- What's an application of one of these new tools that you can think of for your own work? 
- What did you all find challenging about this content?
- What did you all find surprising?
- What did you all enjoy?
