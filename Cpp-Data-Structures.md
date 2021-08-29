# C++ Data Structures

## Table of contents

1. [Linked list](#linked-list)
2. [Trees](#trees)
3. [Vector](#vector)
4. [Stack](#stack)
5. [Queue](#queue)
6. [Priority Queue](#priority-queue)
7. [Pair](#pair)

## <a name="linked-list"></a>Linked list

```cpp
// Node Structure
struct Node {
  int data;
  struct Node* next;
};

// Creating new node
Node *n = new Node;
n->data = x;
n->next = n2;
```

## <a name="trees"></a>Trees

```cpp
// Tree node structure
struct TreeNode {
  int data;
  struct TreeNode* left;
  struct TreeNode* right;
};
```

## <a name="vector"></a>Vector

```cpp
// Vector header file
#include <vector>

// Initialize a vector
vector<int> v(4, -25); // 4 = number of elements; -25 = value of each elements

// Add elements to back of a vector
v.push_back(val);

// Delete elements from a vector
v.erase(v.begin() + 3); // delete 3rd element
v.erase(v.begin() + 10, v.begin() + 15); // delete elements from 10th through 15th position
v.pop_back(); // delete last element
```

## <a name="stack"></a>Stack

```cpp
// Stacks header file
#include <stack>

// Initialize a stack
stack<int> s;

// Check if stack is empty or not (returns boolean value)
s.empty();
  
// Get size of stack
s.size();

// Push on top of a stack
s.push(val);

// Pop from top of stack
s.pop();

// Value at top of stack
val = s.top();
```

## <a name="queue"></a>Queue

```cpp
// Queue header file
#include <queue>

// Initialize a stack
queue<int> q;

// Check if queue is empty or not (returns boolean value)
q.empty();
  
// Get size of queue
q.size();

// Push to the back of a queue
q.push(val);

// Pop from the front of queue
q.pop();

// Get reference to first element
int val = q.front();
  
// Get reference to last element
int val = q.back();
```

## <a name="priority-queue"></a>Priority queue

```cpp
// Header file
#include <queue>

// Initialize a priority queue
priority_queue<int> pq; // maxheap
priority_queue<int, vector<int>, greater<int>> pq; // minheap

// Initialize a priority queue using array elements
priority_queue<int> pq(arr, arr + arr_size);

// Push an elements in a priority queue
pq.push(val);

// Pop from a priority queue
pq.pop();

// Value at top of a priority queue
val = pq.top();
```

## <a name="pair"></a>Pair

```cpp
// Header file
#include <utility>

// Initialize a pair
pair<int, char> p(1, 'a');

// Create pair using make_pair()
pair<int, int> p = make_pair(val1, val2);

// Access elements of a pair
val1 = p.first;
val2 = p.second;
```
