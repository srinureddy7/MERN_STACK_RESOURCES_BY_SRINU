# JavaScript Array Coding Questions

This repository contains various JavaScript coding questions based on array operations. Each question is solved using multiple approaches to provide a comprehensive understanding.

## Table of Contents

1. [Reverse an Array](#reverse-an-array)
2. [Sum of All Elements](#sum-of-all-elements)
3. [Find the Largest Number](#find-the-largest-number)
4. [Remove Duplicates](#remove-duplicates)
5. [Check if Array is Sorted](#check-if-array-is-sorted)
6. [Merge Two Arrays](#merge-two-arrays)
7. [Find Intersection of Two Arrays](#find-intersection-of-two-arrays)
8. [Rotate an Array](#rotate-an-array)
9. [Find the Index of an Element](#find-the-index-of-an-element)
10. [Flatten a Multi-dimensional Array](#flatten-a-multi-dimensional-array)
11. [Count Occurrences of an Element](#count-occurrences-of-an-element)
12. [Find All Pairs with a Given Sum](#find-all-pairs-with-a-given-sum)
13. [Remove a Specific Element](#remove-a-specific-element)
14. [Find the Second Largest Number](#find-the-second-largest-number)
15. [Chunk an Array](#chunk-an-array)
16. [Sort an Array of Objects](#sort-an-array-of-objects)
17. [Find Missing Number in an Array](#find-missing-number-in-an-array)
18. [Group Elements by Property](#group-elements-by-property)
19. [Remove Falsy Values](#remove-falsy-values)
20. [Partition an Array](#partition-an-array)

## Reverse an Array

### Approach 1: Using built-in `reverse` method

```javascript
function reverseArray(arr) {
  return arr.reverse();
}
```

### Approach 2: Using a loop

```javascript
function reverseArray(arr) {
  let newArr = [];
  for (let i = arr.length - 1; i >= 0; i--) {
    newArr.push(arr[i]);
  }
  return newArr;
}
```

### Approach 3: Using recursion

```javascript
function reverseArray(arr) {
  if (arr.length === 0) return [];
  return [arr.pop()].concat(reverseArray(arr));
}
```

## Sum of All Elements

### Approach 1: Using `reduce` method

```javascript
function sumArray(arr) {
  return arr.reduce((sum, num) => sum + num, 0);
}
```

### Approach 2: Using a loop

```javascript
function sumArray(arr) {
  let sum = 0;
  for (let num of arr) {
    sum += num;
  }
  return sum;
}
```

## Find the Largest Number

### Approach 1: Using `Math.max` and spread operator

```javascript
function findLargestNumber(arr) {
  return Math.max(...arr);
}
```

### Approach 2: Using a loop

```javascript
function findLargestNumber(arr) {
  let max = arr[0];
  for (let num of arr) {
    if (num > max) max = num;
  }
  return max;
}
```

## Remove Duplicates

### Approach 1: Using `Set`

```javascript
function removeDuplicates(arr) {
  return [...new Set(arr)];
}
```

### Approach 2: Using a loop and an object

```javascript
function removeDuplicates(arr) {
  let seen = {};
  let result = [];
  for (let num of arr) {
    if (!seen[num]) {
      seen[num] = true;
      result.push(num);
    }
  }
  return result;
}
```

## Check if Array is Sorted

### Approach 1: Using a loop

```javascript
function isSorted(arr) {
  for (let i = 1; i < arr.length; i++) {
    if (arr[i] < arr[i - 1]) {
      return false;
    }
  }
  return true;
}
```

## Merge Two Arrays

### Approach 1: Using concat

```javascript
function mergeArrays(arr1, arr2) {
  return arr1.concat(arr2);
}
```

### Approach 2: Using spread operator

```javascript
function mergeArrays(arr1, arr2) {
  return [...arr1, ...arr2];
}
```

## Find Intersection of Two Arrays

### Approach 1: Using filter and `includes`

```javascript
function findIntersection(arr1, arr2) {
  return arr1.filter((value) => arr2.includes(value));
}
```

### Approach 2: Using `Set`

```javascript
function findIntersection(arr1, arr2) {
  let set2 = new Set(arr2);
  return arr1.filter((value) => set2.has(value));
}
```

## Rotate an Array

### Approach 1: Using slicing

```javascript
function rotateArray(arr, k) {
  k = k % arr.length;
  return arr.slice(-k).concat(arr.slice(0, -k));
}
```

### Approach 2: Using loop

```javascript
function rotateArray(arr, k) {
  let result = arr.slice();
  k = k % arr.length;
  for (let i = 0; i < k; i++) {
    result.unshift(result.pop());
  }
  return result;
}
```

## Find the Index of an Element

### Approach 1: Using `indexOf`

```javascript
function findIndex(arr, element) {
  return arr.indexOf(element);
}
```

### Approach 2: Using a loop

```javascript
function findIndex(arr, element) {
  for (let i = 0; i < arr.length; i++) {
    if (arr[i] === element) {
      return i;
    }
  }
  return -1;
}
```

## Flatten a Multi-dimensional Array

### Approach 1: Using `flat`

```javascript
function flattenArray(arr) {
  return arr.flat(Infinity);
}
```

### Approach 2: Using recursion

```javascript
function flattenArray(arr) {
  let result = [];
  arr.forEach((item) => {
    if (Array.isArray(item)) {
      result = result.concat(flattenArray(item));
    } else {
      result.push(item);
    }
  });
  return result;
}
```

## Count Occurrences of an Element

### Approach 1: Using `reduce`

```javascript
function countOccurrences(arr, element) {
  return arr.reduce(
    (count, current) => (current === element ? count + 1 : count),
    0
  );
}
```

### Approach 2: Using a loop

```javascript
function countOccurrences(arr, element) {
  let count = 0;
  for (let num of arr) {
    if (num === element) count++;
  }
  return count;
}
```

## Find All Pairs with a Given Sum

### Approach 1: Using nested loops

```javascript
function findPairs(arr, sum) {
  let pairs = [];
  for (let i = 0; i < arr.length; i++) {
    for (let j = i + 1; j < arr.length; j++) {
      if (arr[i] + arr[j] === sum) {
        pairs.push([arr[i], arr[j]]);
      }
    }
  }
  return pairs;
}
```

### Approach 2: Using a set

```javascript
function findPairs(arr, sum) {
  let pairs = [];
  let seen = new Set();
  for (let num of arr) {
    let target = sum - num;
    if (seen.has(target)) {
      pairs.push([num, target]);
    }
    seen.add(num);
  }
  return pairs;
}
```

## Remove a Specific Element

### Approach 1: Using `filter`

```javascript
function removeElement(arr, element) {
  return arr.filter((item) => item !== element);
}
```

## Find the Second Largest Number

### Approach 1: Using a loop

```javascript
function secondLargest(arr) {
  let first = -Infinity,
    second = -Infinity;
  for (let num of arr) {
    if (num > first) {
      second = first;
      first = num;
    } else if (num > second && num !== first) {
      second = num;
    }
  }
  return second;
}
```

## Chunk an Array

### Approach 1: Using a loop

```javascript
function chunkArray(arr, size) {
  let result = [];
  for (let i = 0; i < arr.length; i += size) {
    result.push(arr.slice(i, i + size));
  }
  return result;
}
```

## Sort an Array of Objects

### Approach 1: Using sort method

```javascript
function sortArrayOfObjects(arr, key) {
  return arr.sort((a, b) => (a[key] > b[key] ? 1 : -1));
}
```

## Find Missing Number in an Array

### Approach 1: Using sum formula

```javascript
function findMissingNumber(arr) {
  let n = arr.length + 1;
  let expectedSum = (n * (n + 1)) / 2;
  let actualSum = arr.reduce((sum, num) => sum + num, 0);
  return expectedSum - actualSum;
}
```

## Group Elements by Property

### Approach 1: Using `reduce`

```javascript
function groupBy(arr, property) {
  return arr.reduce((acc, obj) => {
    let key = obj[property];
    if (!acc[key]) {
      acc[key] = [];
    }
    acc[key].push(obj);
    return acc;
  }, {});
}
```

## Remove Falsy Values

### Approach 1: Using `filter`

```javascript
function removeFalsyValues(arr) {
  return arr.filter(Boolean);
}
```

## Partition an Array

### Approach 1: Using a loop

```javascript
function partitionArray(arr, predicate) {
  let truthy = [];
  let falsy = [];
  for (let item of arr) {
    if (predicate(item)) {
      truthy.push(item);
    } else {
      falsy.push(item);
    }
  }
  return [truthy, falsy];
}
```
