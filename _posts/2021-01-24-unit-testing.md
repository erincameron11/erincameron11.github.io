---
title: 'JavaScript Unit Testing'
date: 2021-01-24
permalink: /posts/2021/01/unit-testing/
tags:
  - JavaScript
  - unit testing
  - npm
---

Unit testing a simple JavaScript function.

## Objective:
The objective of the project was to write unit tests for the below JavaScript function: 

```
var fizzBuzz = function( test ){
  if ( test % 3 === 0 ){
    return 'Fizz';
  } else if (test % 5 === 0 ){
    return 'Buzz';
  }
  return '';
}
```


## Tech Stack:
The application uses the following technologies:
* JavaScript
* bash
* Jest - testing framework for JavaScript


## Installation & Dependencies:
1. Clone the `github.com/erincameron11/health-information` github repo in your terminal
2. Navigate to the folder `unit-test`
3. Install npm using the command: `npm install`
  * If you do not have npm installed, first download nodejs: https://nodejs.org/en/download/. To check if you have it installed type command `node -v`
4. Install jest to perform the unit tests locally: `npm install --save-dev jest` in your terminal


## Run:
5. To run the test locally, perform the command: `npm test` in your terminal


## Output:
Once the tests have been run in the terminal, the output will look something like below:
![Unit Test Results](https://raw.githubusercontent.com/erincameron11/erincameron11.github.io/master/images/unit-test.png)

### Problem Breakdown
To simplify the problem, I first deconstructed the function into pseudocode/plain english to understand the logic:   
`if test is a multiple of 3, return Fizz`   
`if test is not a multiple of 3, but is a multiple of 5, return Buzz`   
`if test is not a multiple of 3 or 5, return empty string`   

### Unit Tests
I then wrote the following unit tests to test the fizzBuzz function:


Testing an input of 3, expected result 'Fizz':
```
test('test = 3; output should be Fizz', () => {
  const result = fizzBuzz(3);
  expect(result).toBe("Fizz");
});
```


Testing an input of 5, expected result 'Buzz': 
```
test('test = 5; output should be Buzz', () => {
  const result = fizzBuzz(5);
  expect(result).toBe("Buzz");
});
```


Testing an input of string, expected result empty string:
```
test('test = "Hello"; output should be empty string', () => {
  const result = fizzBuzz("Hello");
  expect(result).toBe("");
});
```  


Testing an input of a different data structure (array), expected result empty string:
```
test('test = [1, 2, 3, 4]; output should be empty string', () => {
  `const result = fizzBuzz([1, 2, 3, 4]);
  `expect(result).toBe("");
`});
```


Testing an input of a different data structure (array with different index values), expected result empty string:
```
test('test = [3, 30, 15, 9]; output should be empty string', () => {
  const result = fizzBuzz([3, 30, 15, 9]);
 expect(result).toBe("");
});
```


Testing an input of 30 (multiple of both 3 and 5), expected result 'Fizz':
```
test('test = 30; output should be Fizz', () => {
  const result = fizzBuzz(30);
  expect(result).toBe("Fizz");
});
```


Testing an input of 1.2, expected result empty string:
```
test('test = 1.2; output should be empty string', () => {
  const result = fizzBuzz(1.2);
  expect(result).toBe("");
});
```


Testing an input of 0, expected result 'Fizz':
```
test('test = 0; output should be Fizz', () => {
  const result = fizzBuzz(0);
  expect(result).toBe("Fizz");
});
```


## Conclusion
The function passes all 8 proposed unit tests.

The original fizzBuzz function could be enhanced by accounting for results that are true for both "Fizz" and "Buzz". For example:

```
var fizzBuzz = function( test ){
  if ( test % 3 === 0 &&  test % 5 === 0 ){
    return 'FizzBuzz';
  } else if ( test % 3 === 0 ){
    return 'Fizz';
  } else if (test % 5 === 0 ){
    return 'Buzz';
  }
    return '';
}
```