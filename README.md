# Swift Algorithms Cheatsheet

Transitioning to Swift from languages like Python, C++, or Java might feel cumbersome due to some peculiarities like string indexing. 
This cheatsheet is designed to save you time and make Swift a more familiar environment for algorithmic challenges.

While Swift may not have as rich an algorithmic API as Java or C++, it often shows commendable performance.

## Queue Operations
In Swift, for efficient queue implementations, use the `Deque` module from the [Swift Collections](https://github.com/apple/swift-collections). `Deque` offers high-performance, double-ended queue operations, significantly outperforming the built-in `Array` for tasks that require frequent insertions and deletions at both ends due to its optimized memory management.

```swift
import Collections

var queue = Deque<Int>()
queue.append(10)   // Enqueue at the back
queue.prepend(5)   // Enqueue at the front
let front = queue.popFirst() // Dequeue from the front
let back = queue.popLast()  // Dequeue from the back
```

## String Manipulation
Direct access to indices in a `String` can be inefficient because of Swift's encoding-independent design. To facilitate easier index-based operations, convert the `String` to an `Array` of characters:

```swift
let string = "Hello, Swift"
let characters = Array(string)

let firstChar = characters[0]  // Accessing the first character
let lastChar = characters[characters.count - 1]  // Accessing the last character
```

This approach significantly enhances performance for algorithms requiring character-by-character manipulation.

## Sorting in Swift
Swift's `sort()` method utilizes IntroSort, a hybrid algorithm that combines quicksort, heapsort, and insertion sort to maintain optimal performance across various datasets.

- **Time Complexity**: \(O(N \log N)\) — Applies uniformly to average and worst-case scenarios.
- **Space Complexity for `sort()`:** \(O(\log N)\) — Stack space used during recursive calls.

For non-in-place sorting using the `sorted()` method:

- **Space Complexity for `sorted()`:** \(O(N)\) — Additional space is required as a new array is created.

```swift
var numbers = [4, 2, 5, 3, 1]
numbers.sort()  // In-place sorting
print(numbers)  // Outputs: [1, 2, 3, 4, 5]

let sortedNumbers = numbers.sorted()  // Returns a new sorted array, using extra space
print(sortedNumbers)  // Outputs: [1, 2, 3, 4, 5]
```

## Further Tips
- **Sorting**: Utilize Swift’s `sort()` for efficient in-place sorting.
- **Dictionaries**: Employ dictionaries for rapid lookups and managing unique elements.
- **Higher-order Functions**: Take advantage of Swift's higher-order functions like `map`, `filter`, and `reduce` to craft more concise and readable code.

This cheatsheet aims to bridge the gap between Swift and other programming languages, making it easier for you to implement algorithmic solutions efficiently in Swift.
