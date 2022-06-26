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
