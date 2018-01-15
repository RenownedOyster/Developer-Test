# Limesharp test

Fork this repo, commit changes after each task and send us the link to your repo (don't do a Pull Request, just send us the link).
We will get back to you shortly.
Languages accepted: Javascript or PHP.

### Task 1:

Make this work (repeat 3 times the contents of an array):

```javascript
repeat([1, 2, 3]); //[1,2,3,1,2,3,1,2,3]
```

Your solution:

###### if we type in our console your function and repeat([1,2,3]) then the result should be [1,2,3,1,2,3,1,2,3]

```javascript
function repeat(arr) {
  console.log(arr.concat(arr, arr));
}
```

### Task 2:

Make this work (no vowels, lowercase except the first letter):

```javascript
reformat("liMeSHArp DeveLoper TEST"); //Lmshrp dvlpr tst
```

Your solution:

###### if we type in our console your function and reformat("liMeSHArp DeveLoper TEST") then the result should be Lmshrp dvlpr tst

```javascript
function reformat(str) {
  let reformatted = str
    .replace(/[aeiou]/gi, "")
    .toLowerCase()
    .substr(1);
  let firstLetter = str[0].toUpperCase();

  console.log(firstLetter + reformatted);
}
```

### Task 3 (optional, for bonus points):

Make this work (without using any built in functions, only a `for` loop, return the next binary number in a string or as an array)

```javascript
next_binary_number([1, 0]); // [1,1]

// possible test cases:
// [1,0] => [1,1]
// [1,1] => [1,0,0]
// [1,1,0] => [1,1,1]
// .......
// [1,0,0,0,0,0,0,0,0,1] => [1,0,0,0,0,0,0,0,1,0]
```

Your solution:

###### if we type in our console your function and next_binary_number([1,0,0,0,0,0,0,0,0,1]) then the result should look like 1,0,0,0,0,0,0,0,1,0 (or as an array).

```javascript
// largestBinaryChecker checks whether the binary being counted contains all
// 1's (the largest count possible with n bits). If true, the result
// is n length in zeros prepended with a 1.

function next_binary_number(arr) {
  let nextBinary = arr;
  let largestBinaryChecker = true;
  let startOfNewBinary = [1];

  for (let i = arr.length - 1; i >= 0; i--) {
    startOfNewBinary[i + 1] = 0;

    if (largestBinaryChecker) {
      if (arr[i] === 0) {
        nextBinary[i] = 1;
        largestBinaryChecker = false;
      } else if (arr[i] === 1) {
        nextBinary[i] = 0;
      }
    }
  }
  largestBinaryChecker
    ? console.log(startOfNewBinary)
    : console.log(nextBinary);
}
```

###### If you get invited to the first interview read the What to expect.md file.
