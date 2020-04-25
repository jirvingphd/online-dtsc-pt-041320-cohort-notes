---
title: Python Fundamentals
layout: post
weight: 10
hidden: true
---
​
**Course**: Data Science <br/>
**Mod**: 1 <br/>
**Topic**: Python Fundamentals <br/>
**Amount of time**: 1.5 hours <br/>
**Author**: Alan Hong
​
***
​
## Lesson Summary:
​
#### Topic:
Python Fundamentals
#### Learn.co material:
- None
#### Prerequisite knowledge/ Prework:
- How to start Jupyter Notebook
#### SWBATs:
- Make use of assigning variables
- Classify and explain integers, float, strings, boolean, list, dictionary, and tuple
- Identify the comparators and boolean operators
- Make use of a `list`: indexing, ranges, appending
- Make use of a `dict`: identifying, creating, navigating
- Apply a for loop to lists and dictionaries

#### Misconceptions:
- (Note to former web devs like me lol): A Python `dictionary` might be similar to a JS `object` but its not. In Python, a dictionary has no indexing.
- A `tuple` is a completely new data type and is similar to a read-only `list`
- Indentations matter in Python! Especially when writing loops and conditions.
- lists and dicts are useless - gimme the data frames!
- this is really scary

#### Materials
- Filled Jupyter Notebook for you to refer to as you lecture
- If you want to give the students more practice, use this: https://www.codewars.com/kata/find-the-odd-int/train/python

***

## Lesson Outline:

**Step**: Learning Variable Types and Assigning Variables <br/>
**Time**: 20 min

_Goal/Scenario and Demonstrate:_<br/>
Let's say we are trying to come up with a list of ingredients for a bento box (lunch box) we want to create!

- Demonstrate correct and incorrect variable assignments to different types.

Variable types and things of note:
- What is a variable? (Variables are nothing but reserved memory locations to store values. This means that when you create a variable you reserve some space in memory.)
- How do we assign a variable?
```
ingredient = "rice"
```
- Why is this important? (We can assign it once and then reuse it as many times as we wish!)

- Let's make more robust varialbes:

```
main = "rice"
protein = "salmon"
ozofprotien = 4.5
number_of_sides = 3
side1 = 'seaweed'
side2 = 'tempura'
side2 =  'turnip pickle'
```

If we use the function `type()` on `main` what do we get?
Try using `type()` on the rest of the variables in our bento box.
What types do we see? Any difference between `int` and `float`

- int; float; str; list; dict

- So we assigned them one at a time, you can assign multiple variables at a time like this:
```
a, b, c = 1, 2, "Luke"
print(a)
print(b)
print(c)
```


_Informal Assessment_:<br/>
"Quick check, how confident do we feel about moving on from variable types and variable assignment? Give me yay, nay or a maybe."
- follow up with those students who do not feel confident

**Step**: Comparators, Booleans and Decision Making <br/>
**Time**: 20 min

_Demonstrate_:<br/>
- https://www.tutorialspoint.com/python3/python_decision_making.htm
- comparators are:
```
==
!=
>
<
<=
>=
```
- Decision Making is like this:
```
if (protein == 'salmon'):
  print("I love salmon!")
```
```
#will I like this bento box?
if (main == 'rice'):
  print("no carbs, please!")
elif(ozofprotein >= 2.5):
  print("too much!")
else:
  print("I have no problems with this order")
```

- Have them update the final output of the if/else statement to set greatbento to True/False depending on ingredients. 
- note that True/False are reserved words

**Step**: Using Lists: Indexing, ranges, appending <br/>
**Time**: 10 min

_Demonstrate_: <br/>

- If we want to store all of the ingredients in one item type, we can use - a LIST!
- Ask the class: How can we identify a list? "Square brackets."

```
bento_box_list = ["rice", "chicken teriyaki", "tempura", "soy sauce", "ginger", "seaweed"]
bento_box_list[2]

Output: tempura

numbers[0:2]

Output: ["rice", "chicken teriyaki"]
```
- to append to a list:
```
bento_box_list = ["rice", "chicken teriyaki", "tempura", "soy sauce", "ginger", "seaweed"]
bento_box_list.append("wasabi")
print(bento_box_list)

Output: ["rice", "chicken teriyaki", "tempura", "soy sauce", "ginger", "seaweed", "wasabi"]
```
- Have them convert it to list and also - have it pring a whole sentence using .`join`
_Informal assessment_:<br/>
"What about lists? How do we all feel about lists? Give me yay, nay or a maybe."
- follow up with those students who do not feel confident

**Step**: Dictionaries: Identifying, creating <br/>
**Time**: 10 min

_Demonstration_: <br/>
- Ask the class: How can we identify a dictionary? "Key value pairs." "Curly brackets."
- a Python dictionary is "unindexed"; this means you cannot do `my_dict[0]` to get the first element in a dictionary
- To create a dictionary:
```
bento_box_dict = {'ingredient1': 'rice', 'ingredient2': 'unagi', 'ingredient3': 'miso soup'}
```
- To get an element in the dictionary:
```
print(bento_box_dict['ingredient2'])
```

Let's put it all together!
```
group_lunch = [
    {'ingredient1': 'rice', 'ingredient2': 'unagi', 'ingredient3': 'miso soup'},
    {'ingredient1': 'seaweed', 'ingredient2': 'tempura', 'ingredient3': 'miso soup'},
    {'ingredient1': 'hamburger', 'ingredient2': 'french fries', 'ingredient3': 'milkshake'}
]
```

_Informal assessment_:<br/>
"How do we all feel about Python dictionaries? Give me yay, nay or a maybe."
- follow up with those students who do not feel confident

**Step**: Loops with Lists and Dictionaries <br/>
**Time**: 20 min

_Demonstration_: <br/>
- Ask students to write out step by step instructions on how we would fold our clothes!

```
For items in basket:
   fold each item
```
you start with the first item, end when it is empty

so for our example with a list:

```
for items in bento_box_list:
   print(items)
```
_Apply_ :
Print a different list and name "item" something else

_Demonstrate_ :

-  looping through dictionaries is a bit more complex:
- Let's write a program to simulate these instructions and actions!
```
fold_clothes = [
  "remove from dryer",
  "lay piece of clothing flat",
  "fold piece of clothing in half"
]

for action in fold_clothes:
  print(action)
```
- Ask: How can we loop thru this dictionary and get all the keys?
```
fold_clothes_dict = {
  'action1': 'remove from dryer',
  'action2': 'lay piece of clothing flat',
  'action3': 'fold piece of clothing in half'
}

for action in fold_clothes_dict:
  print(action)
```
- Ask: Now how do we get all the values with a loop?
```
for action in fold_clothes_dict:
  print(fold_clothes_dict[action])
```

_Application:_ </br>

write a loop to print first ingredient in everyone's bento order.

```
group_lunch = [
    {'ingredient1': 'rice', 'ingredient2': 'unagi', 'ingredient3': 'miso soup'},
    {'ingredient1': 'seaweed', 'ingredient2': 'tempura', 'ingredient3': 'miso soup'},
    {'ingredient1': 'hamburger', 'ingredient2': 'french fries', 'ingredient3': 'milkshake'}
]
```

_Informal assessment_:<br/>
"How do we all feel about looping in Python? Give me yay, nay or a maybe."
- follow up with those students who do not feel confident

**Step**: Assessment <br/>
**Time**: 10 min <br/>
- Construct a dictionary and loop over it to print out each key and each value with the assistance of the class
- Let it be class driven as you ask students what to do next

**Step**: Reflection <br/>
**Time**: _if you have time remaining_ <br/>
Ask the class and discuss as a group:
- What did you all find challenging about this content?
- What did you all find surprising?
- What did you all enjoy?
