Questions
Question #1: Turning Strings to URLs
URLs cannot have spaces. Instead, all spaces in a string are replaced with %20. Write an algorithm that replaces all spaces in a string with %20.

You may not use the replace() method or regular expressions to solve this problem. Solve the problem with and without recursion.

Example
Input: "Jasmine Ann Jones"

Output: "Jasmine%20Ann%20Jones"

---------------------------------------------------------------------------------------------------------

function replaceSpace(string) {
  let arr = [];
  arr = string.split(' ');
  for (let i = 0; i < arr.length; i++) {
    let newArr = arr[i] = arr[i]+"%20"
  }
  return arr.join('').toString();
}
//yo .
-------------------------------------------------------------------------------------------------------




Question #2: Array Deduping
Write an algorithm that removes duplicates from an array. Do not use a function like filter() to solve this. Once you have solved the problem, demonstrate how it can be solved with filter(). Solve the problem with and without recursion.

Example
Input: [7, 9, "hi", 12, "hi" 7, 53]

Output: [7, 9, "hi", 12, 53]


-------------------------------------------------------------------------------------------------------

function noDuplicate(arr) {
  let output = [];
  for (let elem of arr) {
    if (!output.include(elem)) {
      output.push(elem)
    }
  } return output;
}

// does not work inside function but cannot figure it out, moving on to prompt 3
-------------------------------------------------------------------------------------------------------

Question #3: Compressing Strings
Write an algorithm that takes a string with repeated characters and compresses them, using a number to show how many times the repeated character has been compressed. For instance, aaa would be written as 3a. Solve the problem with and without recursion.

Example
Input: "aaabccdddda"

Output: "3ab2c4da"

----------------------------------------------------------------------------------------------------------

function compress(string) {
  let counter = 0;
  for (let i = 0; i < string; i++) {
    for (let j = 1; j < string; j++) {
      if (string[i] === string[j]) {
        counter++

        counter = 0;
      }
      else {
        string++
      }
    }
  }
  return string;
}

------------------------------------------------------------------------------------------------------------

Question #4: Checking for Uniqueness
Write an algorithm that determines whether all the elements in a string are unique. You may not convert the string into an array or use array methods to solve this problem. The algorithm should return a boolean.

Example
Input: "hello"

Output: false

Input: "copyright"

Output: true

------------------------------------------------------------------------------------------------------------

function stringIsUnique(str) {
  let isUnique = true;
  for (let i = 0; i < str.length; i++) {
    for (let j = i + 1; j < str.length; j++) {
      if (str.charAt(i) === str.charAt(j)) {
        isUnique = false;
      } 
    }
  }
  return isUnique;
}

const stringIsUnique = (str) => {
  let ifUnique = true;
  for (let i = 0; i < str.length; i++) {
    for (let j = i + 1; j < str.length; j++) {
      if (str.charAt(i) === str.charAt(j)) {
        ifUnique = false;
      } 
    }
  }
  return ifUnique;
}



------------------------------------------------------------------------------------------------------------

Question #5: Array Sorting
Write an algorithm that sorts an array without using the sort() method. There are many different sorting algorithms - take the time to read about the following:

Quick sort
Merge sort
Heap sort
Insertion sort
Bubble sort
Selection sort
You may implement any of the above algorithms (or your own) to solve the problem - as long as it doesn't use sort().

Example
Input: [9, 2, 7, 12]

Output: [2, 7, 9, 12]

------------------------------------------------------------------------------------

function arrSort(array) {
  let loops = 0;
  let swap = false;
  for (let i = 0; i < array.length - loops; i++) {
    if (array[i] > array[i + 1]) {
      let min = array[i + 1];
      array[i + 1] = array[i];
      array[i] = min;
      swap = true;
    }
  }
  loops++
  if (swap === true) {
    return arrSort(array, loops);
  } else {
    return array;
  }
}

---------------------------------------------------------------------------------