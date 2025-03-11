# Data Structures and Algorithms in Ruby

This tutorial covers the basic data structures and algorithms implemented in Ruby. It aims to provide an understanding of how different data structures work and how to implement some common algorithms using Ruby.

## Table of Contents

1. [Arrays](#arrays)
2. [Linked List](#linked-list)
3. [Stacks](#stacks)
4. [Queues](#queues)
5. [Sorting Algorithms](#sorting-algorithms)
6. [Searching Algorithms](#searching-algorithms)
7. [Complexity Analysis](#complexity-analysis)

---

### 1. Arrays (Type: Linear Data Structure)

Arrays are one of the simplest and most commonly used data structures. In Ruby, arrays are dynamic and can grow in size as needed.

#### Example:

```ruby
# Create an array
arr = [1, 2, 3, 4, 5]

# Access elements
puts arr[0] # Output: 1

# Add an element to the array
arr.push(6)
puts arr.inspect # Output: [1, 2, 3, 4, 5, 6]

# Remove the last element
arr.pop
puts arr.inspect # Output: [1, 2, 3, 4, 5]
```

## 2. Linked List (Type: Linear Data Structure)

A linked list is a linear collection of data elements where each element points to the next.

### Example (Singly Linked List):

```ruby
class Node
  attr_accessor :data, :next_node

  def initialize(data)
    @data = data
    @next_node = nil
  end
end

class LinkedList
  def initialize
    @head = nil
  end

  def add(data)
    new_node = Node.new(data)
    if @head.nil?
      @head = new_node
    else
      current = @head
      current = current.next_node while current.next_node
      current.next_node = new_node
    end
  end

  def display
    current = @head
    while current
      print "#{current.data} -> "
      current = current.next_node
    end
    puts "nil"
  end
end

# Usage
list = LinkedList.new
list.add(1)
list.add(2)
list.add(3)
list.display # Output: 1 -> 2 -> 3 -> nil
```

## 3. Stacks (Type: Linear Data Structure)

A stack is a collection of elements that follows the Last In, First Out (LIFO) principle.

### Example:

```ruby
class Stack
  def initialize
    @stack = []
  end

  def push(item)
    @stack.push(item)
  end

  def pop
    @stack.pop
  end

  def peek
    @stack[-1]
  end

  def is_empty?
    @stack.empty?
  end
end

# Usage
stack = Stack.new
stack.push(1)
stack.push(2)
stack.push(3)
puts stack.pop # Output: 3
puts stack.peek # Output: 2
```
## 4. Queues (Type: Linear Data Structure)
A queue is a collection that follows the First In, First Out (FIFO) principle.

### Example:
```ruby
class Queue
  def initialize
    @queue = []
  end

  def enqueue(item)
    @queue.push(item)
  end

  def dequeue
    @queue.shift
  end

  def front
    @queue[0]
  end

  def is_empty?
    @queue.empty?
  end
end

# Usage
queue = Queue.new
queue.enqueue(1)
queue.enqueue(2)
queue.enqueue(3)
puts queue.dequeue # Output: 1
puts queue.front # Output: 2
```
## 5. Sorting Algorithms (Type: Algorithm)
Sorting is the process of arranging elements in a certain order (e.g., ascending or descending).

## Bubble Sort Example:
```ruby
def bubble_sort(arr)
  n = arr.length
  for i in 0...(n-1)
    for j in 0...(n-i-1)
      if arr[j] > arr[j+1]
        arr[j], arr[j+1] = arr[j+1], arr[j]
      end
    end
  end
  arr
end

# Usage
arr = [5, 2, 9, 1, 5, 6]
puts bubble_sort(arr).inspect # Output: [1, 2, 5, 5, 6, 9]
```
## 6. Searching Algorithms (Type: Algorithm)
Searching is the process of finding an element in a collection.

### Linear Search Example:
```ruby
def linear_search(arr, target)
  arr.each_with_index do |element, index|
    return index if element == target
  end
  return -1 # Not found
end

# Usage
arr = [10, 20, 30, 40, 50]
puts linear_search(arr, 30) # Output: 2
puts linear_search(arr, 60) # Output: -1
```
## 7. Complexity Analysis (Type: Analysis)
Understanding the time and space complexity of algorithms is crucial.

- Time Complexity: Describes how the execution time grows with input size (e.g., O(n), O(log n), O(n^2)).
- Space Complexity: Describes how the memory usage grows with input size.
  
### Example: Bubble Sort Complexity
- Best Case: O(n) when the array is already sorted.
- Worst Case: O(n^2) when the array is sorted in reverse order.

  
