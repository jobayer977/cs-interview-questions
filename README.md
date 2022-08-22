# Frequently Asked Angular Interview Questions 
 ### Resources 
- [Angular Documentations](https://angular.io/) 
 

 ## Table of Contents

- [1 What is Big O notation?](#what-is-big-o-notation)
- [2 What is meant by linear search?](#what-is-meant-by-linear-search)
- [3 what is o(n) time complexity](#what-is-on-time-complexity)
- [4 What is binary searching?](#what-is-binary-searching)
- [5 When should you not use binary search?](#when-should-you-not-use-binary-search)
<br/><br/><br/><br/>

1. ### What is Big O notation?

Big O Notation is a way to measure an algorithm's efficiency. It measures the time it takes to run your function as the input grows.

2. ### What is meant by linear search?

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

3. ### what is o(n) time complexity

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

4. ### What is binary searching?

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

5. ### When should you not use binary search?

In case the list of elements is not sorted, there's no way to use binary search because the median value of the list can be anywhere and when the list is split into two parts, the element that you were searching for could be cut off. This is why binary search is not useful.

