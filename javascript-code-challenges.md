# JavaScript Practice Exercises

Here are various JavaScript exercises and solutions to practice fundamental concepts.

## 1. Print all even numbers from 0 – 10

```javascript
for (let i = 0; i <= 10; i++) {
    if (i % 2 === 0) {
        console.log('number', i);
    }
}
```

## 2. Print a table containing multiplication tables
```javascript
for (let i=0;i<=10;i++){
    for (let j=1;j<=10;j++){
         let ml = i*j;
         console.table(ml);
    }
}
```
## 3. Create a length converter function

```javascript
function kmToMile(km){
    if(km>0){
        let convertedValue= km*0.6213712;
        console.log(convertedValue)
    }else{
      let a =  new Error('Enter valid value');
      console.log(a.message)
    }
}
```
kmToMile(1);

## 4. Calculate the sum of numbers within an array

solution:1
```javascript
let numberArr = [44,66,2,77,45,11];
let total = numberArr.reduce((prvVal,currentVal)=>prvVal+currentVal);
console.log('total',total);
```
solution:2
```javascript
    let numbers = [44,66,2,77,45,11];
    let totalSum =0;
    for(let i=0;i<=numbers.length-1;i++){
        if(numbers[i]>0){
            totalSum+=numbers[i];
        }
    }
    console.log(totalSum);
```

## 5. Create a function that reverses an array

solution:1
```javascript
let anArray=[2,8,4,2,4,1,99,22];
let result = anArray.reverse();
console.log(result);
```
solution:2
```javascript
let rev= [];
for(let i=anArray.length-1;i>=0;i--){
    rev.push(anArray[i]);
}
console.log(rev);
```
solution:3
```javascript
let rev= [];
for(let i=0;i<=anArray.length-1;i++){
    rev.unshift(anArray[i]);
}
console.log(rev);
```

## 6. Sort an array from lowest to highest
solution:1
```javascript
let anArray=[2,8,4,2,4,1,99,22];
let sortArr = anArray.sort((a,b)=>b-a);
console.log(sortArr);
```
solution:2
```javascript
function sortNumberArr(numArr = []) {
    let recordCount = numArr.length;
    let sortArr = numArr.slice(); 

    for (let i = 0; i < recordCount - 1; i++) {
        for (let j = 0; j < recordCount - i - 1; j++) {
            if (sortArr[j] > sortArr[j + 1]) {
                // Swap elements if they are in the wrong order
                [sortArr[j], sortArr[j + 1]] = [sortArr[j + 1], sortArr[j]];
            }
        }
    }

    return sortArr;
}

let checkArr = sortNumberArr([2, 8, 4, 2, 4, 1, 99, 22]);
console.log(checkArr);
```

## 7. Create a function that filters out negative numbers

solution:1
```javascript
function filterNegativeNumber(numArr=[]){
         return numArr.filter((item)=>item<0);
}

 let checkArr = filterNegativeNumber([2, -8, 4, -2, -4, 1, 99, 22]);
console.log(checkArr);
```
solution:2
```javascript
function filterNegativeNumber(numArr=[]){
    let totalCount = numArr.length;
    let negativeNum = [];
    for(let i=0; i<totalCount-1; i++){
        if(numArr[i]<0){
         negativeNum.push(numArr[i]);
        }
    }
    return negativeNum;
}

let checkArr = filterNegativeNumber([2, -8, 4, -2, -4, -1, 99, 22]);
console.log(checkArr);
```

## 8. Remove the spaces found in a string

```javascript
let context = 'hi hello world';
let strArr = context.split(' ');
let t_string='';
for(let i=0; i<=strArr.length-1; i++){
    t_string+=strArr[i];
}
console.log(t_string);
```


## 9. Return a Boolean if a number is divisible by 10
```javascript
function checkDivisible(num){
   if(num%10==0){
    return true;
   }else{
    return false;
   }
}

console.log(checkDivisible(440));
```
## 10. Return the number of vowels in a string
```javascript
function vowelsCount(string){
    string = string.toLowerCase();
   let stringArr = string.split('');
    let vowels = ['a','o','i','e','u'];
    let vowelCount = 0;
    for (let i = 0; i < stringArr.length-1; i++) {
        if(vowels.includes(stringArr[i])){
            vowelCount += 1;
        }
    }
    return vowelCount;
}

console.log(vowelsCount('vowelsCount'));
```

function arraySum(arr) {
  if (arr.length === 0) {
    return 0;
  }
  return arr[0] + arraySum(arr.slice(1));
}

 ### 25 recursive functions that work with arrays in JavaScript:

Certainly! Here are 25 recursive functions that work with arrays in JavaScript:

1. **Recursive Array Sum:**
   ```javascript
   function arraySum(arr) {
     if (arr.length === 0) {
       return 0;
     }
     return arr[0] + arraySum(arr.slice(1));
   }
   ```

2. **Recursive Array Max:**
   ```javascript
   function arrayMax(arr) {
     if (arr.length === 1) {
       return arr[0];
     }
     const subMax = arrayMax(arr.slice(1));
     return arr[0] > subMax ? arr[0] : subMax;
   }
   ```

3. **Recursive Array Min:**
   ```javascript
   function arrayMin(arr) {
     if (arr.length === 1) {
       return arr[0];
     }
     const subMin = arrayMin(arr.slice(1));
     return arr[0] < subMin ? arr[0] : subMin;
   }
   ```

4. **Recursive Array Length:**
   ```javascript
   function arrayLength(arr) {
     if (arr.length === 0) {
       return 0;
     }
     return 1 + arrayLength(arr.slice(1));
   }
   ```

5. **Recursive Array Flattening:**
   ```javascript
   function flattenArray(arr) {
     let result = [];
     for (let i = 0; i < arr.length; i++) {
       if (Array.isArray(arr[i])) {
         result = result.concat(flattenArray(arr[i]));
       } else {
         result.push(arr[i]);
       }
     }
     return result;
   }
   ```

6. **Recursive Array Reverse:**
   ```javascript
   function reverseArray(arr) {
     if (arr.length === 0) {
       return [];
     }
     return [arr[arr.length - 1]].concat(reverseArray(arr.slice(0, arr.length - 1));
   }
   ```

7. **Recursive Array Filtering:**
   ```javascript
   function filterArray(arr, condition) {
     if (arr.length === 0) {
       return [];
     }
     const head = condition(arr[0]) ? [arr[0]] : [];
     return head.concat(filterArray(arr.slice(1), condition));
   }
   ```

8. **Recursive Array Mapping:**
   ```javascript
   function mapArray(arr, callback) {
     if (arr.length === 0) {
       return [];
     }
     return [callback(arr[0])].concat(mapArray(arr.slice(1), callback));
   }
   ```

9. **Recursive Array Intersection:**
   ```javascript
   function arrayIntersection(arr1, arr2) {
     if (arr1.length === 0 || arr2.length === 0) {
       return [];
     }
     if (arr2.includes(arr1[0])) {
       return [arr1[0]].concat(arrayIntersection(arr1.slice(1), arr2));
     }
     return arrayIntersection(arr1.slice(1), arr2);
   }
   ```

10. **Recursive Array Deep Copy:**
    ```javascript
    function deepCopyArray(arr) {
      if (!Array.isArray(arr)) {
        return arr;
      }
      return arr.map((item) => deepCopyArray(item));
    }
    ```

11. **Recursive Array Chunking:**
    ```javascript
    function chunkArray(arr, size) {
      if (arr.length === 0) {
        return [];
      }
      return [arr.slice(0, size)].concat(chunkArray(arr.slice(size), size));
    }
    ```

12. **Recursive Array Zip:**
    ```javascript
    function zipArrays(arr1, arr2) {
      if (arr1.length === 0 || arr2.length === 0) {
        return [];
      }
      return [[arr1[0], arr2[0]]].concat(zipArrays(arr1.slice(1), arr2.slice(1));
    }
    ```

13. **Recursive Array Rotation:**
    ```javascript
    function rotateArray(arr, steps) {
      if (steps === 0) {
        return arr;
      }
      const rotated = arr.slice(1).concat(arr[0]);
      return rotateArray(rotated, steps - 1);
    }
    ```

14. **Recursive Array Element Removal:**
    ```javascript
    function removeElementFromArray(arr, element) {
      if (arr.length === 0) {
        return [];
      }
      if (arr[0] === element) {
        return removeElementFromArray(arr.slice(1), element);
      }
      return [arr[0]].concat(removeElementFromArray(arr.slice(1), element));
    }
    ```

15. **Recursive Array Insertion:**
    ```javascript
    function insertElementIntoArray(arr, element, index) {
      if (index === 0) {
        return [element].concat(arr);
      }
      return [arr[0]].concat(insertElementIntoArray(arr.slice(1), element, index - 1));
    }
    ```

16. **Recursive Array Unique Values:**
    ```javascript
    function uniqueArrayValues(arr) {
      if (arr.length === 0) {
        return [];
      }
      const tail = uniqueArrayValues(arr.slice(1));
      if (tail.includes(arr[0])) {
        return tail;
      }
      return [arr[0]].concat(tail);
    }
    ```

17. **Recursive Array Sort:**
    ```javascript
    function sortArray(arr) {
      if (arr.length <= 1) {
        return arr;
      }
      const pivot = arr[0];
      const left = arr.slice(1).filter(item => item <= pivot);
      const right = arr.slice(1).filter(item => item > pivot);
      return sortArray(left).concat([pivot], sortArray(right));
    }
    ```

18. **Recursive Array Shuffle:**
    ```javascript
    function shuffleArray(arr) {
      if (arr.length === 0) {
        return [];
      }
      const randomIndex = Math.floor(Math.random() * arr.length);
      const [item] = arr.splice(randomIndex, 1);
      return [item].concat(shuffleArray(arr

));
    }
    ```

19. **Recursive Array Binary Search:**
    ```javascript
    function binarySearch(arr, target, left = 0, right = arr.length - 1) {
      if (left > right) {
        return -1;
      }
      const mid = Math.floor((left + right) / 2);
      if (arr[mid] === target) {
        return mid;
      }
      if (arr[mid] > target) {
        return binarySearch(arr, target, left, mid - 1);
      }
      return binarySearch(arr, target, mid + 1, right);
    }
    ```

20. **Recursive Array Chunking (Fixed Size):**
    ```javascript
    function chunkArrayFixedSize(arr, size, result = []) {
      if (arr.length === 0) {
        return result;
      }
      return chunkArrayFixedSize(arr.slice(size), size, result.concat([arr.slice(0, size)]));
    }
    ```

21. **Recursive Array Splice:**
    ```javascript
    function spliceArray(arr, index, howMany, ...elements) {
      if (index === 0) {
        return elements.concat(arr.slice(howMany));
      }
      return [arr[0]].concat(spliceArray(arr.slice(1), index - 1, howMany, ...elements));
    }
    ```

22. **Recursive Array Deduplication:**
    ```javascript
    function deduplicateArray(arr, unique = []) {
      if (arr.length === 0) {
        return unique;
      }
      const [head, ...tail] = arr;
      if (!unique.includes(head)) {
        unique.push(head);
      }
      return deduplicateArray(tail, unique);
    }
    ```

23. **Recursive Array Palindrome Check:**
    ```javascript
    function isPalindromeArray(arr) {
      if (arr.length <= 1) {
        return true;
      }
      if (arr[0] !== arr[arr.length - 1]) {
        return false;
      }
      return isPalindromeArray(arr.slice(1, arr.length - 1));
    }
    ```

24. **Recursive Array Permutations:**
    ```javascript
    function permutationsArray(arr) {
      if (arr.length === 0) {
        return [[]];
      }
      const result = [];
      for (let i = 0; i < arr.length; i++) {
        const rest = arr.slice(0, i).concat(arr.slice(i + 1));
        const perms = permutationsArray(rest);
        for (const perm of perms) {
          result.push([arr[i], ...perm]);
        }
      }
      return result;
    }
    ```

25. **Recursive Array Unique Combinations:**
    ```javascript
    function uniqueCombinations(arr, length, index = 0, current = [], result = []) {
      if (current.length === length) {
        result.push(current);
        return;
      }
      if (index === arr.length) {
        return;
      }
      uniqueCombinations(arr, length, index + 1, [...current, arr[index]], result);
      uniqueCombinations(arr, length, index + 1, current, result);
      return result;
    }
    ```

### String


**1. Reverse a String:**

```javascript
function reverseString(str) {
  return str.split('').reverse().join('');
}

console.log(reverseString("Hello, World!")); // Output: "!dlroW ,olleH"
```

**2. Check for Palindrome:**

```javascript
function isPalindrome(str) {
  str = str.toLowerCase().replace(/[^a-zA-Z0-9]/g, '');
  const reversed = str.split('').reverse().join('');
  return str === reversed;
}

console.log(isPalindrome("A man, a plan, a canal, Panama")); // Output: true
```

**3. Count Vowels and Consonants:**

```javascript
function countVowelsAndConsonants(str) {
  const vowels = str.match(/[aeiou]/gi) || [];
  const consonants = str.match(/[^aeiou]/gi) || [];
  return { vowels: vowels.length, consonants: consonants.length };
}

const result = countVowelsAndConsonants("Hello, World!");
console.log(result); // Output: { vowels: 3, consonants: 7 }
```

**4. Remove Duplicates:**

```javascript
function removeDuplicates(str) {
  return [...new Set(str)].join('');
}

console.log(removeDuplicates("banana")); // Output: "ban"
```

**5. String Capitalization:**

```javascript
function capitalizeWords(str) {
  return str.replace(/\b\w/g, char => char.toUpperCase());
}

console.log(capitalizeWords("hello world")); // Output: "Hello World"
```

**6. String Compression:**

```javascript
function compressString(str) {
  let compressed = '';
  let count = 1;
  for (let i = 0; i < str.length; i++) {
    if (str[i] === str[i + 1]) {
      count++;
    } else {
      compressed += str[i] + count;
      count = 1;
    }
  }
  return compressed.length < str.length ? compressed : str;
}

console.log(compressString("aaabb")); // Output: "a3b2"
```



// solution 1
```javascript
let arree = [3,4,[4,5],[[3]],[[[[[4]]]]],3,5];

const arrFlatArr = (arr)=>{
     let flattenArr = [];
      for(let i=0; i<arr.length; i++){
     if(Array.isArray(arr[i])){
    flattenArr= flattenArr.concat(arrFlatArr(arr[i]))
     
     }else{
     flattenArr.push(arr[i]); 
     }
       }
     return flattenArr;
}

console.log('check data',arrFlatArr(arree));
```
// solution 2
```javascript
let Input = [{"name":"Aima","grade":"A"},{"name":"Arjun","grade":"A+"},{"name":"Iram","grade":"B+"},{"name":"Zia","grade":"C"},{"name":"Reah","grade":"B"},{"name":"Karan","grade":"A"},{"name":"Mithum","grade":"B"},{"name":"Ankur","grade":"B+"}]

 function sortObj(arr){
    if(arr.length>0){
   return arr.sort((a,b)=>{
      let aObj = a.grade.toUpperCase();
      let bObj = b.grade.toUpperCase();
      if(aObj>bObj){
        return -1;
      }else if(aObj<bObj){
        return 1;
      }else{
        return 0;
      }
    })
  }
 }
 console.log(sortObj(Input));
```


// solution 3
```javascript
let a = 'JavaScript is awesome';
let b = a.split(' ');
let reversString = '';

for(let i=b.length-1; i>=0; i--){
console.log(b[i])
   reversString+= b[i]+' ';
}

console.log('string', reversString);
```



// solution 4
### word aslo revese
```javascript
let a = 'JavaScript is awesome';
let b = a.split(' ');
for(let i=b.length-1; i>=0; i--){
console.log(b[i])
   let letterLenth =b[i].split('');
   let reverseword = '';
    for(let j=b[i].length-1; i>=0; j--){
    reverseword =letterLenth[j];
    }
   reversString+= reverseword+' ';
}

console.log('word reverse', reversString);
```

// solution 5
```javascript
const findPair = (arr, target) => {
  const seenValues = new Set();

  for (let i = 0; i < arr.length; i++) {
    const complement = target - arr[i];
    if (seenValues.has(complement)) {
      return [arr[i], complement];
    }
    seenValues.add(arr[i]);
  }

  return "No pair [1, 9] found.";
};

const a = [2, 3, 4, 3, 3, 2, 4, 9, 1, 2, 5, 5];
const result = findPair(a, 10); // Looking for the pair [1, 9] which sums to 10
console.log(result);
```

### All word upper case first letter capital
```javascript
const transformName = (name:string) => {
    let updated = name.toLowerCase();
    let allWords = updated.split(' ');
    let updatedName = [];
    for (let i = 0; i < allWords.length; i++) {
      let firstLetter = allWords[i].substring(0, 1);
      let restOfWord = allWords[i].substring(1);
      let fullWord = firstLetter.toUpperCase() + restOfWord;
      updatedName.push(fullWord);
    }
    return updatedName.join(' ');
  }
```






