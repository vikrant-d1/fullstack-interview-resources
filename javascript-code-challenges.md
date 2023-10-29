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

