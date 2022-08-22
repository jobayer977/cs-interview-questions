# Frequently Asked DataStructure and Algorithms Interview Questions 
 ### Resources 
 

 ## Table of Contents

- [1 What is an Algorithm?](#what-is-an-algorithm)
- [2 What is Big O notation?](#what-is-big-o-notation)
- [3 What is meant by linear search?](#what-is-meant-by-linear-search)
- [4 what is o(n) time complexity](#what-is-on-time-complexity)
- [5 What will happen as n approaches infinity in BigO?](#what-will-happen-as-n-approaches-infinity-in-bigo)
- [6 What does space complexity mean?](#what-does-space-complexity-mean)
- [7 What is space complexity types?](#what-is-space-complexity-types)
- [8 What is the fastest big O?](#what-is-the-fastest-big-o)
- [9 What is binary searching?](#what-is-binary-searching)
- [10 When should you not use binary search?](#when-should-you-not-use-binary-search)
<br/><br/><br/><br/>

1. ### What is an Algorithm?

A set of instructions that can be executed to accomplish a specific task or to produce a result. A process durer for solving a problem is called an algorithm.

2. ### What is Big O notation?

Big O Notation is a way to measure an algorithm's efficiency. It measures the time it takes to run your function as the input grows.

3. ### What is meant by linear search?

A linear search is a simple search algorithm that looks at each element in the data set and checks if the element is the one you are looking for. Starting at the beginning of the data set. Once the item is found, the search ends.

```javascript
function linearSearch(arr, item) {
	for (let i = 0; i < arr.length; i++) {
		if (arr[i] === item) {
			return true
		}
	}
	return false
}

linearSearch([1, 2, 3, 4, 5], 3) // true
```

**Big O Notation**
The time complexity is O(n) because the algorithm has to look at each element in the data set.

4. ### what is o(n) time complexity

Linear time complexity O(n) means that the algorithms take proportionally longer to complete as the input grows.

Examples of linear time algorithms: Get the max/min value in an array.

```js
function getMax(arr) {
	let max = arr[0]
	for (let i = 1; i < arr.length; i++) {
		if (arr[i] > max) {
			max = arr[i]
		}
	}
	return max
}

function getMin(arr) {
	let min = arr[0]
	for (let i = 1; i < arr.length; i++) {
		if (arr[i] < min) {
			min = arr[i]
		}
	}
	return min
}

const arr = [1, 2, 3, 4, 5]

const max = getMax(arr)
const min = getMin(arr)
```

In the above example, the algorithm is O(n) because it has to loop through the array once to find the max and once to find the min value. The loop is dependent on the size of the array.

5. ### What will happen as n approaches infinity in BigO?

Big O notation is written in the form of O(n) where O stands for “order of magnitude” and n represents what we're comparing the complexity of a task against.

6. ### What does space complexity mean?

Space complexity is the amount of memory that an algorithm will use. Algorithms are run on a computer It need certain amount of memory space to run. The amount of memory used by an algorithm is called its space complexity.

**Example:**

```javascript
function factorial(n) {
	if (n === 0) {
		return 1
	}
	return n * factorial(n - 1)
}
```

The above algorithm will use O(n) space complexity. This is because it will use n amount of memory to store the result of the factorial function.

**Another Example:**

```javascript
function sum(n1, n2) {
	return n1 + n2
}
```

This algorithm will use O(1) space complexity. This is because it will use only one memory space to store the result of the sum function.

7. ### What is space complexity types?

Space complexity types are used to describe the amount of space required to store a given data structure.

### Space complexity types

- **O(1)**: Constant time complexity.
- **O(n)**: Linear time complexity.
- **O(log n)**: Logarithmic time complexity.

8. ### What is the fastest big O?

The fastest possible running time for any algorithm is O(1), commonly referred to as Constant Running Time. In this case, the algorithm always takes the same amount of time to execute, regardless of the input size.

**Example of Constant Running Time:**

```javascript
function constantRunningTime(n) {
	return n
}

constantRunningTime(1) // O(1)
```

The above algorithm is the fastest possible running time for any algorithm. It always takes the same amount of time to execute, regardless of the input size.

9. ### What is binary searching?

Binary search is a search algorithm that works by comparing the target value to the middle element of the data set. If the target value is less than the middle element, the algorithm repeats the process on the lower half of the data set. If the target value is greater than the middle element, the algorithm repeats the process on the upper half of the data set.

```javascript
function binarySearch(arr, item) {
	let low = 0
	let high = arr.length - 1

	while (low <= high) {
		const mid = Math.floor((low + high) / 2)
		const guess = arr[mid]

		if (guess === item) {
			return true
		}

		if (guess > item) {
			high = mid - 1
		} else {
			low = mid + 1
		}
	}

	return false
}

binarySearch([1, 2, 3, 4, 5], 3) // true
```

**Note:** The above algorithm is `O(log n)` because it has to divide the data set in half every time it loops.

10. ### When should you not use binary search?

In case the list of elements is not sorted, there's no way to use binary search because the median value of the list can be anywhere and when the list is split into two parts, the element that you were searching for could be cut off. This is why binary search is not useful.

