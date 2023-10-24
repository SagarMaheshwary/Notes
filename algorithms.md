# ALGORITHMS

- An algorithm is a set of well-defined instructions to solve a particular problem.
- One problem can be solve in many ways using different algorithms. Every algorithm comes with it's own tradeoffs when it come to performance.
- We evaluate the performance of an algorithm in terms of it's input size.

### BIG O NOTATION

- When writing algorithms we are only interested in worst case scenerio so we use big O notation to calculate time and space complexity of an algorithm.
- #### Time Complexity
  - Amount of time taken by an algorithm to run.
  - **O(1)** Constant time complexity
  - **O(n)** Linear time complexity, as the input size increases, the time to execute the algorithm will also increase.
  - **O(logn)** Logarithmic time complexity, input size reduces by half on every iteration.
  - **O(n!)** Factorial - An algorithm is said to have a factorial time complexity when it grows in a factorial way based on the size of the input data.
- ### Space Complexity
  - Amount of memory taken by an algorithm to run.
  - **O(1)** Constant - memory does not increase when the inpute size increases.
  - **O(n)** Linear - memory usage increases as the input size increases.
  - **O(logn)** Logarithmic - memory usage grows but not at the same rate as the input size.

### MATH

Below are a few math skills that are important for learning and implementing algorithms.

- Combination (basically learning to calculate Big O of multiple code operations in a program)
- Logarithm (General understanding and learning to calculate logn time complexity)
- Factorial
- Exponentials
- Modulus

### Search Algorithms

#### Linear Search

- Linear search, also known as sequential search, is a straightforward and simple searching algorithm used to find a specific element in a list. It works by checking each element in the list sequentially until the desired element is found or the end of the list is reached.

```typescript
//O(n)

function findIndex(array: number[], target: number): number {
  for (let i = 0; i < array.length; i++) {
    if (array[i] === target) {
      return i;
    }
  }

  return -1;
}
```

#### Binary Search

- Binary search is an efficient search algorithm used to find a specific element in a sorted array or list. It works by repeatedly dividing the search range in half, reducing the number of elements to be searched with each iteration.
- Note: Only works on sorted arrays

```typescript
//O(logn)
function findIndex(arr: number[], target: number): number {
  let leftIndex = 0;
  let rightIndex = arr.length - 1;

  while (leftIndex <= rightIndex) {
    let middleIndex = Math.floor((leftIndex + rightIndex) / 2);

    if (arr[middleIndex] === target) {
      return middleIndex;
    }

    if (arr[middleIndex] > target) {
      rightIndex = middleIndex - 1;
    } else {
      leftIndex = middleIndex + 1;
    }
  }

  return -1;
}
```

### Sorting Algorithms

#### Bubble Sort

- Bubble sort is a simple sorting algorithm that repeatedly steps through the list to be sorted, compares adjacent elements, and swaps them if they are in the wrong order. The algorithm gets its name from the way smaller elements "bubble" to the top of the list during each pass.

```typescript
//O(n^2)
function bubbleSort(arr: number[]): number[] {
  for (let i = 0; i < arr.length; i++) {
    for (let j = 1; j < arr.length; j++) {
      if (arr[j - 1] < arr[j]) {
        const temp = arr[j - 1];

        arr[j - 1] = arr[j];
        arr[j] = temp;
      }
    }
  }

  return arr;
}
```

#### Insertion Sort

- Insertion sort is a simple sorting algorithm that builds the final sorted array one element at a time. It is a comparison-based sorting algorithm that is efficient for small datasets but becomes less practical for larger datasets. The basic idea behind insertion sort is to divide the input array into two subarrays: the sorted subarray and the unsorted subarray. The algorithm repeatedly takes the first unsorted element and places it in its correct position within the sorted subarray.

```typescript
//O(n^2)
function insertionSort(arr: number[]): number[] {
  for (let i = 1; i < arr.length; i++) {
    for (let j = i; j > 0; j--) {
      if (arr[j - 1] >= arr[j]) {
        break;
      }

      const temp = arr[j - 1];

      arr[j - 1] = arr[j];
      arr[j] = temp;
    }
  }

  return arr;
}
```

#### Selection Sort

#### Merge Sort

#### Quick Sort

#### Radix Sort

#### Heap Sort

#### Bucket Sort
