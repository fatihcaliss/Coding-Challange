<div align="center">
  <img height="60" src="https://img.icons8.com/color/344/javascript.png">
  <h1>JavaScript Questions</h1> </div>
  <h2>I am adding Js questions and solutions which I solved before. Stay coding.. </h2> </div><hr><hr>

<p>1. You live in the city of Cartesia where all roads are laid out in a perfect grid. You arrived ten minutes too early to an appointment, so you decided to take the opportunity to go for a short walk. The city provides its citizens with a Walk Generating App on their phones -- everytime you press the button it sends you an array of one-letter strings representing directions to walk (eg. ['n', 's', 'w', 'e']). You always walk only a single block for each letter (direction) and you know it takes you one minute to traverse one city block, so create a function that will return true if the walk the app gives you will take you exactly ten minutes (you don't want to be early or late!) and will, of course, return you to your starting point. Return false otherwise.</p>

samples:
isValidWalk(['n','s','n','s','n','s','n','s','n','s']) => true <br>
isValidWalk(['w']) => false  <br>
isValidWalk(['n','n','n','s','n','s','n','s','n','s']) => false  <br>
isValidWalk(['w','e','w','e','w','e','w','e','w','e','w','e']) => false  <br>
[Question Link](https://www.codewars.com/kata/54da539698b8a2ad76000228/solutions/javascript)
## Solution:

```javascript
function isValidWalk(arr) {
    if (arr.length == 10) {
        let vertical = arr.filter(e => e == "n").length == arr.filter(e => e == "s").length;
        let horizontal = arr.filter(e => e == "w").length == arr.filter(e => e == "e").length;
        return vertical && horizontal
    }else return false;
}
```
<hr>

<p>2.This is an interview question asked by Uber.

Given an array of integers, return a new array such that each element at index i of the new array is the product of all the numbers in the original array except the one at i.</p>

For example,<br>
if our input was [1, 2, 3, 4, 5], the expected output would be [120, 60, 40, 30, 24]. <br>
If our input was [3, 2, 1], the expected output would be [2, 3, 6].  <br>

## Solution:

```javascript
function solution(arr) {
let sum = 1;
for(let i = 1; i <= x.length; i++){  
    sum *= i;
}return x.map((a) => sum/a);
}
```
<hr>
<p>3.Given n, take the sum of the digits of n. If that value has more than one digit, continue reducing in this way until a single-digit number is produced. The input will be a non-negative integer.</p>

For example,<br>
16  -->  1 + 6 = 7<br>
942  -->  9 + 4 + 2 = 15  -->  1 + 5 = 6<br>
132189  -->  1 + 3 + 2 + 1 + 8 + 9 = 24  -->  2 + 4 = 6<br>
493193  -->  4 + 9 + 3 + 1 + 9 + 3 = 29  -->  2 + 9 = 11  -->  1 + 1 = 2<br>

## Solution:

```javascript
function convert(num) {
    let x = String(num).split("").map((e) => Number(e)).reduce((a,b)=> a + b);
    if(String(x).length == 1){
        return x;
    }
    else{
        convert(x)
    }
}
convert(493193);
```
<hr>
<p>4.Write an algorithm that takes an array and moves all of the zeros to the end, preserving the order of the other elements.</p>

For example,<br>
moveZeros([false,1,0,1,2,0,1,3,"a"]), returns[false,1,1,2,1,3,"a",0,0]<br>
[Question Link](https://www.codewars.com/kata/52597aa56021e91c93000cb0/solutions/javascript)

## Solution:

```javascript
function zeroEnd(arr) {
    return arr.filter(e => e !== 0).concat(arr.filter(e => e === 0))
}
zeroEnd([false, 1, 0, 1, 2, 0, 1, 3, "a"]);
```
<hr>
<p>5.Write a function that takes an integer as input, and returns the number of bits that are equal to one in the binary representation of that number. You can guarantee that input is non-negative.</p>

For example,<br>
The binary representation of 1234 is 10011010010, so the function should return 5 in this case<br>
[Question Link](https://www.codewars.com/kata/526571aae218b8ee490006f4/train/javascript)

## Solution:

```javascript
var countBits = function (n) {
  return +n.toString(2).split("").reduce((a, b) => +a + +b)
}
countBits(0); // returns 0, countBits(4) returns 1, countBits(4) retuns 3.
```
<hr>
<p>6.The goal of this exercise is to convert a string to a new string where each character in the new string is "(" if that character appears only once in the original string, or ")" if that character appears more than once in the original string. Ignore capitalization when determining if a character is a duplicate.</p>

For example,<br>
"din"      =>  "(((" <br>
"recede"   =>  "()()()" <br>
"Success"  =>  ")())())" <br>
"(( @"     =>  "))(("  <br>

[Question Link](https://www.codewars.com/kata/54b42f9314d9229fd6000d9c/solutions/javascript)

## Solution-1:

```javascript
function duplicateEncode(word){
    return word.toLowerCase().split('').map((a,b,c) => c.indexOf(a) == c.lastIndexOf(a) ? '(' : ')').join('')
}
```
## Solution-2:
```javascript
function duplicateEncode(word){
    let arr = word.split("");
    let obj = {};
    for(let i = 0; i < arr.length; i++){
        if(Object.keys(obj).includes(arr[i].toLowerCase())){
            obj[(arr[i].toLowerCase())] += 1; 
        }else{
            obj[(arr[i].toLowerCase())] = 1;
        }   
    }
    for(let i = 0; i<arr.length; i++){
        if( obj[(arr[i].toLowerCase())] === 1){
            arr[i] = "(";
        }else{
            arr[i] = ")";
        }
    }
    return arr.join("")
}
```
<hr>
<p>7.Your goal in this kata is to implement a difference function, which subtracts one list from another and returns the result.It should remove all values from list a, which are present in list b keeping their order.</p>

For example,<br>
arrayDiff([1,2],[1]) == [2]<br>
<p>If a value is present in b, all of its occurrences must be removed from the other:</p>
arrayDiff([1,2,2,2,3],[2]) == [1,3]<br>

[Question Link](https://www.codewars.com/kata/523f5d21c841566fde000009/solutions/javascript)

## Solution:

```javascript
function arrayDiff(a, b) {
    return a.filter((e => !b.includes(e)))
};
```
<hr>
<p>8.Oh no!
The new zookeeper has lost track of how many animals are in the zoo because the last person to do the count thought it would be funny to do it in binary.

Write a function that can help the zookeper convert the binary count.<br>
Input will be an object where key:value-pairs will represent an animal and a binary number.<br>
Output should be an integer that equals the sum of all the animals in the zoo.</p>


[Question Link](https://www.codewars.com/kata/5a1d91698ba9145199000141/train/javascript)

## Solution:

```javascript
function countTheAnimals(animals) {
   return Object.values(animals).map(e=> parseInt(e,2)).reduce((a,b)=> a+b);
}
```
<hr>
<p>9.In this Kata, you will be given an array of strings and your task is to remove all consecutive duplicate letters from each string in the array.</p>

For example:<br>

dup(["abracadabra","allottee","assessee"]) = ["abracadabra","alote","asese"].<br>

dup(["kelless","keenness"]) = ["keles","kenes"].<br>

Strings will be lowercase only, no spaces. See test cases for more examples.<br>


[Question Link](https://www.codewars.com/kata/59f08f89a5e129c543000069/train/javascript)

## Solution:

```javascript
function dup(s) {
    return s.map(e => e.split("").filter((e,i,arr) => arr[i] != arr[i+1]).join(""))
};
```
<hr>
