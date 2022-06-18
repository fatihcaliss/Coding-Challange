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
