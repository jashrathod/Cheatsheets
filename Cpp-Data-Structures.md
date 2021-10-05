# C++ Data Structures

We can use ```#include<bits/stdc++.h>``` to include all the libraries present in STL.

## Table of contents

1. [Linked list](#linked-list)
2. [Trees](#trees)
3. [Vector](#vector)
4. [Stack](#stack)
5. [Queue](#queue)
6. [Priority Queue](#priority-queue)
7. [Pair](#pair)
8. [Set and Unordered set](#set)
9. [Map and Unordered map](#map)
10. [Memset](#memset)
11. [INT_MAX and INT_MIN](#intmax-intmin)

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

// Initialize a queue
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
priority_queue<int> pq(arr, arr + arr.size());

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

## <a name="set"></a>Set and Unordered set

For unordered set, replace ```set``` with ```unordered_set```.

```cpp
// Header file
#include <set>

// Initialize a set
set<int> s; 

// Initialize a set using array elements
set<int> s(arr, arr + arr.size());

// add elements to set
s.insert(val);

// Check if value exist in set
if(s.find(val) != s.end())
    cout << "Element found";

// Initialize iterator
set<int> :: iterator it;

// Looping through the set
for(it = s.begin(); it != s.end(); ++it)
{
    cout << *it <<endl;
}

// Delete element from a set
s.erase(s.begin() + 3); // delete 3rd element
s.erase(s.find(val)); // delete using a value
s.erase(it); // delete using iterator
```

## <a name="map"></a>Map and Unordered map

For unordered map, replace ```map``` with ```unordered_map```.

```cpp
// Header file
#include <map>

// Initialize a map
map<int, int> mp; 

// add key-value pairs to map
mp[key] = value;

// Check if key-value exist in map
if(mp.find(key) != mp.end())
    cout << "Value at " << key << " is " << mp[key];

// Beginning and ending elements of a map
mp.begin();
mp.end();

// Initialize iterator
map<int, int> :: iterator it;

// Looping through the map
for(it = mp.begin(); it != mp.end(); ++it)
{
    cout << "Key = " << it->first << endl;
    cout << "Value = " << it->second << endl;
}

// Delete element from a set
mp.erase(mp.begin() + 3); // delete 3rd element
mp.erase(mp.find(key)); // delete using a value
mp.erase(it); // delete using iterator
```

## <a name="memset"></a>Memset

```cpp
// Setting the value of all elements of arr as val; arr can be a 2D array also
memset(arr, val, sizeof(arr));
```

## <a name="intmax-intmin"></a>INT_MAX and INT_MIN 

```cpp
// Header file
#include <limits>

// Values of INT_MAX and INT_MIN
// INT_MAX = 2^31 - 1
// INT_MIN = - 2^31

// Usage
int var = INT_MAX;
```
