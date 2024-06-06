<details>
<summary>Sum of Digits / Digital Root</summary>

    Digital root is the recursive sum of all the digits in a number.
    
    Given n, take the sum of the digits of n. If that value has more than one digit,
    continue reducing in this way until a single-digit number is produced. The input will be a non-negative integer.

> Examples<br>
>     16  -->  1 + 6 = 7 <br>
>    942  -->  9 + 4 + 2 = 15  -->  1 + 5 = 6<br>
> 132189  -->  1 + 3 + 2 + 1 + 8 + 9 = 24  -->  2 + 4 = 6<br>
> 493193  -->  4 + 9 + 3 + 1 + 9 + 3 = 29  -->  2 + 9 = 11  -->  1 + 1 = 2

***Solution:***
```python
def digital_root(n):
    s=str(n)
    l = len(s)
    if l >1:
        return digital_root(sum(int(each)for each in s))
    return n
```
</details>

---

<details>
<summary>Duplicate Encoder</summary>
   
    The goal of this exercise is to convert a string to a new string where each character
    in the new string is "(" if that character appears only once in the original string,
    or ")" if that character appears more than once in the original string. Ignore
    capitalization when determining if a character is a duplicate.


> Examples<br>
> "din"      =>  "((("<br>
> "recede"   =>  "()()()"<br>
> "Success"  =>  ")())())"<br>
> "(( @"     =>  "))(("

***Solution:***
```python
def duplicate_encode(word):
    word = word.lower()
    new_word=''
    for letter in word:
        count=0
        for l in word:
            if l == letter:
                count+=1
        if count >1:
            new_word += ')'
        else:
            new_word += '('
    return new_word
```
</details>

---

<details>
<summary>Your order, please</summary>
   
    Your task is to sort a given string. Each word in the string will contain a single number.
    This number is the position the word should have in the result.

    Note: Numbers can be from 1 to 9. So 1 will be the first word (not 0).

    If the input string is empty, return an empty string. The words in the input String will only contain valid consecutive numbers.

> Examples<br>
> "is2 Thi1s T4est 3a"  -->  "Thi1s is2 3a T4est"<br>
> "4of Fo1r pe6ople g3ood th5e the2"  -->  "Fo1r the2 g3ood 4of th5e pe6ople"<br>
> ""  -->  ""

***Solution:***
```python
def order(sentence):
    if sentence == '':
        return ''
    sentence = sentence.split()
    new_sentence= ['~' for word in sentence]
    for word in sentence:
        print(word)
        for letter in word:
            try:
                new_sentence[int(letter)-1]=word
            except:
                continue
    new_sentence = ' '.join(each for each in new_sentence)
    return new_sentence
```
</details>

---

<details>
<summary>Build a pile of Cubes</summary>
   
Your task is to construct a building which will be a pile of n cubes.
The cube at the bottom will have a volume of n<sup>3</sup>, the cube above will have volume of (n-1)<sup>3</sup> and so on until the top which will have a volume of 1<sup>3</sup>

You are given the total volume m of the building. Being given m can you find the number n of cubes you will have to build?

The parameter of the function findNB (find_nb, fin-nb, findNB, ...) will be an integer m and you have to return the integer n such as n<sup>3</sup> + (n-1)<sup>3</sup> + (n-2)<sup>3</sup> + ... + 1<sup>3</sup> = m if such a n exists or -1 if there is no such n.

> Examples<br>
> findNb(1071225) --> 45<br>
> findNb(91716553919377) --> -1

***Solution:***
```python
def find_nb(mass):
    count = 0
    m=0
    while m<mass:
        count += 1
        m += count**3
        if m>mass:
            return -1
    return count
```
</details>

---

<details>
<summary>Pete, the baker</summary>
   
    Pete likes to bake some cakes. He has some recipes and ingredients. Unfortunately he is not good in maths. Can you help him to find out, how many cakes he could bake considering his recipes?

    Write a function cakes(), which takes the recipe (object) and the available ingredients (also an object) and returns the maximum number of cakes Pete can bake (integer). For simplicity there are no units for the amounts (e.g. 1 lb of flour or 200 g of sugar are simply 1 or 200). Ingredients that are not present in the objects, can be considered as 0.

```python
Examples:

# must return 2
cakes({flour: 500, sugar: 200, eggs: 1}, {flour: 1200, sugar: 1200, eggs: 5, milk: 200})<br>
# must return 0
cakes({apples: 3, flour: 300, sugar: 150, milk: 100, oil: 100}, {sugar: 500, flour: 2000, milk: 2000})
```

***Solution:***
```python
def cakes(recipe, available):
    amount  = []
    for each in recipe:
        if each not in available:
            return 0
        amount.append(available[each]//recipe[each])
    return min(amount)
```
</details>

---

<details>
<summary>Human Readable Time</summary>
   
    Write a function, which takes a non-negative integer (seconds) as input and returns the time in a human-readable format (HH:MM:SS)

    HH = hours, padded to 2 digits, range: 00 - 99
    MM = minutes, padded to 2 digits, range: 00 - 59
    SS = seconds, padded to 2 digits, range: 00 - 59
    The maximum time never exceeds 359999 (99:59:59)

    You can find some examples in the test fixtures.



> Examples<br>
> test.assert_equals(make_readable(0), "00:00:00")<br>
        test.assert_equals(make_readable(59), "00:00:59")<br>
        test.assert_equals(make_readable(60), "00:01:00")<br>
        test.assert_equals(make_readable(3599), "00:59:59")<br>

***Solution:***
```python
def make_readable(seconds):
    hours = seconds // 3600
    seconds -= hours * 3600
    minutes = seconds // 60
    seconds -= minutes * 60
    h=''
    m=''
    s=''
    if hours <10:
        h=0
    if minutes <10:
        m=0
    if seconds <10:
        s=0
    return (f'{h}{hours}:{m}{minutes}:{s}{seconds}')
```
</details>

---
<!--
<details>
<summary>Placeholder</summary>
   
    asdf
    asdf

> Examples<br>
> asdf<br>
> asdf<br>
> asdf<br>

***Solution:***
```python
asdf
asdf
asdf
```
</details>

---
<!--
<details>
<summary>Placeholder</summary>
   
    asdf
    asdf

> Examples<br>
> asdf<br>
> asdf<br>
> asdf<br>

***Solution:***
```python
asdf
asdf
asdf
```
</details>

---
-->
