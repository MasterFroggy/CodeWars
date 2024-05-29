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
