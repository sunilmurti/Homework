<h2>Data Bootcamp: Code Practice #2</h2>

<h5>1. Review. Does this code run without error? If so, what does it produce?
If not, explain why.</h5>

    x = [1, 2, 3]
    y = 'bootcamp'
    z=x+y

ERROR, because we cannot combine a string (bootcamp) and a list (1, 2, 3,)

<h5>2. Review. For the same x and y as the previous question: What function
tells us what type they are? What function tells us how many elements they contain? </h5>

    type();
    len()

<h5>3. What type is each expression? How can you tell?</h5>

```2``` - INT, no quotations 

```‘2’``` - STR, bound by quotations 

```2.0``` - FLOAT, has a decimal

```“2.0"``` - STR, bound by quotations 

```2>1``` - BOOL, utilizes a greater than sign to compare two integers

```'Itamar' > ‘Chase'``` - BOOL, compares two strings to each other 

```[1, 2]``` - LIST - bound by square brackets 

```(1, 2)``` - TUPLE - bound by rounded brackets/parenthesis 

```{1: 'one', 2: ‘two'}``` - DICT - a dictionary entry for two integers
(1 and 2) that correspond with two different strings (one and two).
Marked by the curly brackets.

<h5>4. What value does each of these comparisons have?</h5>

```1>=0```- True

```1 >= 1``` - True 

```1>1``` - False 

```1==1``` - True 

```1 == 1.0``` - True 

```'Spencer' == “Spencer”``` - True 

```2**3 > 3**2``` - False 

```1 >= 0 or 1 <= 2``` - True 

```1 >= 0 and 1 <= 2``` - True

<h5>5. Does this code run without error? If so, what does it produce?
If not, how would you fix it?</h5>

    if 2 > 1 
        print('Yes, 2 is still greater than 1')

ERROR, we have to add a : (colon) after “if 2>1”

    CORRECTION
    if 2 > 1 :
        print('Yes, 2 is still greater than 1')

<h5>6. What is the result of running this code? Why?</h5>

    if True: 
        print('on the one hand') 
    else: 
        print('but on the other hand’)
Python prints 'on the one hand'

<h5>What happens if we replace True with False in the first line?</h5>

    if False: 
        print('on the one hand') 
    else: 
        print('but on the other hand’)
Python prints 'but on the other hand'

<h5>What happens if we insert the word not after if in the first line</h5>

    if not False: 
        print('on the one hand') 
    else: 
        print('but on the other hand’)
Python prints 'on the one hand'



<h5>7. What is the result of running this code?</h5>

    cond = True 
    if cond: 
        x = “Chase" 
    else: 
        x = "Dave" 
    print(x) 

        Chase

Python prints <em>Chase</em>

<h5>8. Suppose we have two lists, x = [1, 2, 3, 4] and y = [’x’, ’y’, ’z’].
Adapt the code below to determine which has more elements:</h5>

    x = [1,2,3,4]
    y = ['x', 'y', 'z']

    if <insert expression>:
       print('x has more')
    else:
       print("y has at least as many")

The replacement expression is "len(x) > len(y)"

    if len(x) > len(y):
      print('x has more')
    else:
      print("y has at least as many")

    x has more

<h5>9. Explain in words what slicing does.</h5>
Slicing allows us to access or extract specific items from a list or string.

<h5>10. How would you extract (“slice”) the first element (the integer 1) from the list x below?</h5>


    x = [1, 2, 3, 4, 5]

    x[1]

<h5>The last element?</h5>

    x[1]

<h5>All but the last element?</h5>

    x[:-1]


<h5>11. Use slicing to extract each word from</h5>

    sentence = 'This is a sentence; please slice it.'

    sentence[0:4]
    sentence[5:7]
    sentence[8:9]
    sentence[10:18]
    sentence[20:26]
    sentence[27:32]
    sentence[33:35]

<h5>Consider the list

    x = [1, 2, "a", 'b', "fast", 'slow', 3, "Raghu", 'Liuren', 10]

<h5> (a) How would you slice out the first item? The last item?</h5>

    x[0]
    x[-1]

<h5> (b) How would you slice out the items from ’b’ to 3 inclusive?</h5>

    x[3:7]

<h5>13. Using the same list x, write a loop that prints every element on a new line.</h5>

    for item in x:
      print(item)

<h5>14. Challenging. Using the same list x, write a loop that prints every element of type str.</h5>

    for item in x:
      if isinstance(item, str):
        print(item)

    a
    b
    fast
    slow
    Raghu
    Liuren

<h5>15. Use Spyder’s help to find out what the range function does. How would you describe
range(3,12,2)? Verify by converting to a list with list(range(3,12,2)).

The first number sets the lower boundary (inclusive) and the second number sets
the upper boundary (exclusive) of the range. The third number denotes the steps between
each number. Therefore the output should be:

    list(range(3,12,2))

    [3,5,7,9,11]

<h5> 16. Challenging. Write a loop that sums the integers from zero to thirty that are multiples
of three: 3, 6, etc.

    Easy way without loop

    y = list(range(0,31,3))
    sum(y)

    165


    Difficult way with loop

    y = list(range(0,31))
    sum_of_int_three=0

    for item in y:
      if (item % 3 == 0):
        sum_of_int_three = sum_of_int_three+item

    print(sum_of_int_three)

    165
