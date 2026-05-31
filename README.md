# 📚 DSA Learning Guide — From Foundations to Mastery

> A structured roadmap for learning Data Structures & Algorithms, covering core topics, key algorithms, and problem-solving patterns.

---

## 🗺️ Learning Roadmap Overview

```
Phase 1: Foundations          (~2–3 weeks)
Phase 2: Core Data Structures (~3–4 weeks)
Phase 3: Core Algorithms      (~3–4 weeks)
Phase 4: Advanced Topics      (~4–6 weeks)
Phase 5: Problem Patterns     (ongoing)
```

---

## Phase 1: Foundations

### 1.1 Big-O Notation & Complexity Analysis

Understanding performance is the #1 skill before anything else.

| Complexity     | Name         | Example                       |
|----------------|--------------|-------------------------------|
| O(1)           | Constant     | Array index access            |
| O(log n)       | Logarithmic  | Binary search                 |
| O(n)           | Linear       | Loop through array            |
| O(n log n)     | Linearithmic | Merge sort, heap sort         |
| O(n²)          | Quadratic    | Nested loops, bubble sort     |
| O(2ⁿ)          | Exponential  | Recursive subsets             |
| O(n!)          | Factorial    | Permutations                  |

**Key concepts:**
- Time complexity vs Space complexity
- Best / Average / Worst case
- Amortized analysis (e.g., ArrayList resizing)
- Recursion and call stack depth

---

### 1.2 Core Java / Language Prerequisites (for Java devs)

- Arrays, Strings, StringBuilder
- Java Collections: `ArrayList`, `LinkedList`, `HashMap`, `HashSet`, `TreeMap`, `PriorityQueue`, `Deque`
- Comparable & Comparator
- Autoboxing, generics
- Recursion + base cases

---

## Phase 2: Core Data Structures

### 2.1 Arrays & Strings

**Topics:**
- Static vs dynamic arrays
- In-place manipulation
- Sliding window, two pointers
- Prefix sums, frequency maps
- String manipulation: anagram, palindrome, substring

**Key problems to practice:**
- Two Sum, Three Sum
- Longest Substring Without Repeating Characters
- Maximum Subarray (Kadane's)
- Product of Array Except Self
- Valid Palindrome, Reverse Words

---

### 2.2 Linked Lists

**Types:** Singly → Doubly → Circular

**Topics:**
- Node structure, pointer manipulation
- Fast & slow pointers (Floyd's algorithm)
- Reversal, merging, cycle detection

**Key problems:**
- Reverse a Linked List
- Detect & Remove Cycle
- Merge Two Sorted Lists
- Find Middle of Linked List
- LRU Cache (LinkedList + HashMap)

---

### 2.3 Stacks & Queues

**Stack:** LIFO — use for DFS, undo operations, expression parsing  
**Queue:** FIFO — use for BFS, scheduling  
**Deque:** Both ends — sliding window maximum

**Key problems:**
- Valid Parentheses
- Min Stack
- Daily Temperatures (monotonic stack)
- Implement Queue using Stacks
- Sliding Window Maximum

---

### 2.4 Hash Maps & Hash Sets

**Topics:**
- Hash function, collision handling (chaining, open addressing)
- O(1) average lookup, insert, delete
- Frequency counting, grouping

**Key problems:**
- Two Sum (HashMap solution)
- Group Anagrams
- Top K Frequent Elements
- Longest Consecutive Sequence
- Subarray Sum Equals K

---

### 2.5 Trees

**Types:**
- Binary Tree
- Binary Search Tree (BST)
- Balanced BST (AVL, Red-Black)
- N-ary Tree

**Traversals:**
```
         1
        / \
       2   3
      / \
     4   5

Inorder  (L-Root-R): 4 2 5 1 3  → sorted order for BST
Preorder (Root-L-R): 1 2 4 5 3  → copy/serialize tree
Postorder(L-R-Root): 4 5 2 3 1  → delete tree
Level order (BFS):   1 2 3 4 5
```

**Key problems:**
- Max Depth of Binary Tree
- Validate BST
- Lowest Common Ancestor
- Binary Tree Level Order Traversal
- Serialize and Deserialize Binary Tree
- Kth Smallest Element in BST

---

### 2.6 Heaps / Priority Queues

**Min-Heap:** Root is the smallest element  
**Max-Heap:** Root is the largest element

**Java:** `PriorityQueue<Integer>` (min-heap by default)

**Use cases:** Top-K problems, scheduling, Dijkstra's algorithm

**Key problems:**
- Kth Largest Element in an Array
- Find Median from Data Stream
- Merge K Sorted Lists
- Task Scheduler

---

### 2.7 Graphs

**Representations:**
- Adjacency List (most common)
- Adjacency Matrix
- Edge List

**Types:** Directed / Undirected, Weighted / Unweighted, Cyclic / Acyclic (DAG)

**Traversals:**
```
BFS — Level by level, uses Queue → shortest path (unweighted)
DFS — Deep first, uses Stack/Recursion → cycle detection, topological sort
```

**Key problems:**
- Number of Islands
- Clone Graph
- Course Schedule (topological sort)
- Pacific Atlantic Water Flow
- Word Ladder (BFS)
- Dijkstra's Shortest Path

---

### 2.8 Tries (Prefix Trees)

**Use case:** Autocomplete, spell check, prefix matching

```
Insert "cat", "car", "card":

       root
        |
        c
        |
        a
       / \
      t   r
          |
          d
```

**Key problems:**
- Implement Trie (Prefix Tree)
- Word Search II
- Design Search Autocomplete System

---

### 2.9 Segment Trees & Fenwick Trees (BIT)

**Use case:** Range queries + point updates in O(log n)

- Segment Tree: range sum, range min/max
- Fenwick Tree (BIT): prefix sum queries

**Key problems:**
- Range Sum Query (Mutable)
- Count of Smaller Numbers After Self

---

### 2.10 Disjoint Set Union (Union-Find)

**Use case:** Connected components, dynamic connectivity, Kruskal's MST

```java
int find(int x) {
    if (parent[x] != x) parent[x] = find(parent[x]); // path compression
    return parent[x];
}

void union(int x, int y) {
    int px = find(x), py = find(y);
    if (rank[px] < rank[py]) parent[px] = py;
    else if (rank[px] > rank[py]) parent[py] = px;
    else { parent[py] = px; rank[px]++; }
}
```

**Key problems:**
- Number of Connected Components
- Redundant Connection
- Accounts Merge

---

## Phase 3: Core Algorithms

### 3.1 Sorting Algorithms

| Algorithm      | Time (avg)   | Time (worst) | Space  | Stable |
|----------------|--------------|--------------|--------|--------|
| Bubble Sort    | O(n²)        | O(n²)        | O(1)   | ✅     |
| Selection Sort | O(n²)        | O(n²)        | O(1)   | ❌     |
| Insertion Sort | O(n²)        | O(n²)        | O(1)   | ✅     |
| Merge Sort     | O(n log n)   | O(n log n)   | O(n)   | ✅     |
| Quick Sort     | O(n log n)   | O(n²)        | O(log n)| ❌    |
| Heap Sort      | O(n log n)   | O(n log n)   | O(1)   | ❌     |
| Counting Sort  | O(n + k)     | O(n + k)     | O(k)   | ✅     |
| Radix Sort     | O(nk)        | O(nk)        | O(n+k) | ✅     |

> **Java `Arrays.sort()`** uses Dual-Pivot Quicksort for primitives and TimSort for objects.

---

### 3.2 Searching Algorithms

**Linear Search:** O(n)  
**Binary Search:** O(log n) — requires sorted array

```java
int binarySearch(int[] arr, int target) {
    int lo = 0, hi = arr.length - 1;
    while (lo <= hi) {
        int mid = lo + (hi - lo) / 2; // prevent overflow
        if (arr[mid] == target) return mid;
        else if (arr[mid] < target) lo = mid + 1;
        else hi = mid - 1;
    }
    return -1;
}
```

**Binary Search Variants:**
- Find first/last occurrence
- Search in rotated sorted array
- Find minimum in rotated array
- Binary search on answer (capacity, speed problems)

---

### 3.3 Recursion & Backtracking

**Recursion template:**
```
solve(problem):
    if base_case: return answer
    subproblem = reduce(problem)
    return combine(solve(subproblem))
```

**Backtracking template:**
```
backtrack(state, choices):
    if goal: record solution; return
    for each choice in choices:
        make choice
        backtrack(new state, remaining choices)
        undo choice  ← KEY STEP
```

**Key problems:**
- Subsets / Subsets II
- Permutations / Permutations II
- Combination Sum
- N-Queens
- Sudoku Solver
- Word Search

---

### 3.4 Divide & Conquer

Split → Solve subproblems → Merge

**Examples:** Merge Sort, Quick Sort, Binary Search, Closest Pair of Points

**Key problems:**
- Merge K Sorted Lists
- Find Kth Largest Element (QuickSelect)
- Maximum Subarray

---

### 3.5 Graph Algorithms

#### BFS (Breadth-First Search)
```
- Uses Queue
- Finds shortest path in unweighted graphs
- Level-order traversal
```

#### DFS (Depth-First Search)
```
- Uses Stack/Recursion
- Cycle detection
- Topological sort
- Connected components
```

#### Dijkstra's Algorithm
```
- Shortest path in weighted graphs (non-negative weights)
- Uses Min-Heap (Priority Queue)
- Time: O((V + E) log V)
```

#### Bellman-Ford
```
- Shortest path with negative weights
- Detects negative cycles
- Time: O(V × E)
```

#### Floyd-Warshall
```
- All-pairs shortest path
- Time: O(V³)
```

#### Topological Sort (Kahn's Algorithm / DFS)
```
- For Directed Acyclic Graphs (DAGs)
- Use case: Build systems, course prerequisites
```

#### Kruskal's & Prim's (MST)
```
- Kruskal: Sort edges, Union-Find
- Prim: Greedy, Priority Queue
- Minimum Spanning Tree
```

---

## Phase 4: Advanced Topics & Patterns

### 4.1 Dynamic Programming (DP)

> **The most important advanced topic for interviews.**

**Core idea:** Break problem into overlapping subproblems, store results to avoid recomputation.

**Two approaches:**
- **Top-Down (Memoization):** Recursion + cache
- **Bottom-Up (Tabulation):** Iterative, fill table

**DP Framework:**
1. Define the state — what does `dp[i]` represent?
2. Write the recurrence relation
3. Identify base cases
4. Determine iteration order

---

#### DP Subcategories

**1D DP:**
- Fibonacci, Climbing Stairs
- House Robber
- Jump Game
- Decode Ways

**2D DP:**
- Unique Paths
- Minimum Path Sum
- Longest Common Subsequence (LCS)
- Edit Distance
- Coin Change

**Knapsack Patterns:**
- 0/1 Knapsack
- Unbounded Knapsack (Coin Change)
- Subset Sum / Partition Equal Subset Sum

**String DP:**
- Longest Palindromic Subsequence
- Palindrome Partitioning
- Regular Expression Matching

**Interval DP:**
- Burst Balloons
- Matrix Chain Multiplication

**Tree DP:**
- House Robber III
- Binary Tree Maximum Path Sum

---

### 4.2 Greedy Algorithms

**Key idea:** Make locally optimal choice at each step.

**When to use greedy:**
- Problem has optimal substructure
- Local choice leads to global optimum
- Activity selection, interval scheduling

**Key problems:**
- Jump Game I & II
- Gas Station
- Task Scheduler
- Minimum Number of Arrows to Burst Balloons
- Interval Scheduling (Activity Selection)

---

### 4.3 Bit Manipulation

```java
n & (n-1)       // Remove lowest set bit
n & (-n)        // Isolate lowest set bit
n ^ n = 0       // XOR with itself = 0
n ^ 0 = n       // XOR with 0 = n
x >> 1          // Divide by 2
x << 1          // Multiply by 2
(x >> i) & 1    // Check ith bit
x | (1 << i)    // Set ith bit
x & ~(1 << i)   // Clear ith bit
```

**Key problems:**
- Single Number (XOR)
- Number of 1 Bits (Hamming Weight)
- Counting Bits
- Reverse Bits
- Missing Number
- Power of Two

---

### 4.4 Math & Number Theory

- GCD / LCM (Euclidean algorithm)
- Prime sieve (Sieve of Eratosthenes)
- Modular arithmetic (`(a + b) % mod`)
- Fast exponentiation (binary exponentiation)

---

## Phase 5: Problem-Solving Patterns

> Recognizing patterns is the key to solving unseen problems fast.

---

### Pattern 1: Sliding Window

**When:** Subarray/substring problems with a size constraint or condition.

**Types:**
- Fixed window size: sliding a window of k elements
- Variable window size: expand/shrink based on condition

**Template (Variable):**
```java
int left = 0, result = 0;
Map<Character, Integer> map = new HashMap<>();

for (int right = 0; right < s.length(); right++) {
    // Add right element to window
    map.merge(s.charAt(right), 1, Integer::sum);
    
    // Shrink window if invalid
    while (/* window is invalid */) {
        map.merge(s.charAt(left), -1, Integer::sum);
        if (map.get(s.charAt(left)) == 0) map.remove(s.charAt(left));
        left++;
    }
    result = Math.max(result, right - left + 1);
}
```

**Problems:** Longest Substring Without Repeating Characters, Minimum Window Substring, Fruit Into Baskets

---

### Pattern 2: Two Pointers

**When:** Sorted array/string; find pairs/triplets with condition.

```java
int left = 0, right = arr.length - 1;
while (left < right) {
    int sum = arr[left] + arr[right];
    if (sum == target) { /* found */ }
    else if (sum < target) left++;
    else right--;
}
```

**Problems:** Two Sum II, 3Sum, Container With Most Water, Trapping Rain Water

---

### Pattern 3: Fast & Slow Pointers

**When:** Linked list cycle detection; find middle.

```java
ListNode slow = head, fast = head;
while (fast != null && fast.next != null) {
    slow = slow.next;
    fast = fast.next.next;
}
// slow is at the middle
```

**Problems:** Linked List Cycle, Find Middle of List, Happy Number

---

### Pattern 4: Binary Search on Answer

**When:** "Minimize the maximum" or "maximize the minimum" type problems.

```java
int lo = minPossible, hi = maxPossible;
while (lo < hi) {
    int mid = lo + (hi - lo) / 2;
    if (canAchieve(mid)) hi = mid;      // or lo = mid + 1
    else lo = mid + 1;                   // depending on problem
}
return lo;
```

**Problems:** Koko Eating Bananas, Capacity to Ship Packages, Minimum Days to Make M Bouquets

---

### Pattern 5: BFS on Grid / Multi-Source BFS

**When:** Shortest distance in a grid; spread from multiple sources.

```java
Queue<int[]> queue = new LinkedList<>();
boolean[][] visited = new boolean[m][n];
int[][] dirs = {{0,1},{0,-1},{1,0},{-1,0}};

// Add all sources to queue
queue.offer(new int[]{r, c});
visited[r][c] = true;

while (!queue.isEmpty()) {
    int[] curr = queue.poll();
    for (int[] d : dirs) {
        int nr = curr[0] + d[0], nc = curr[1] + d[1];
        if (inBounds(nr, nc) && !visited[nr][nc]) {
            visited[nr][nc] = true;
            queue.offer(new int[]{nr, nc});
        }
    }
}
```

**Problems:** Rotting Oranges, 01 Matrix, Walls and Gates, Number of Islands

---

### Pattern 6: DFS / Backtracking on Grid

**When:** Path finding, region marking, flood fill.

```java
void dfs(char[][] grid, int r, int c) {
    if (r < 0 || r >= m || c < 0 || c >= n || grid[r][c] != '1') return;
    grid[r][c] = '0'; // mark visited
    dfs(grid, r+1, c); dfs(grid, r-1, c);
    dfs(grid, r, c+1); dfs(grid, r, c-1);
}
```

**Problems:** Number of Islands, Surrounded Regions, Pacific Atlantic Water Flow

---

### Pattern 7: Monotonic Stack

**When:** "Next greater element", "largest rectangle", spans.

```java
Deque<Integer> stack = new ArrayDeque<>();
for (int i = 0; i < nums.length; i++) {
    while (!stack.isEmpty() && nums[stack.peek()] < nums[i]) {
        int idx = stack.pop();
        result[idx] = nums[i]; // next greater element
    }
    stack.push(i);
}
```

**Problems:** Daily Temperatures, Largest Rectangle in Histogram, Trapping Rain Water, Next Greater Element

---

### Pattern 8: Top-K Elements (Heap)

**When:** Find k largest/smallest/frequent elements.

```java
// Min-heap of size k → keeps k largest
PriorityQueue<Integer> heap = new PriorityQueue<>();
for (int num : nums) {
    heap.offer(num);
    if (heap.size() > k) heap.poll(); // remove smallest
}
// heap contains k largest elements
```

**Problems:** Kth Largest Element, Top K Frequent Elements, K Closest Points to Origin

---

### Pattern 9: Merge Intervals

**When:** Overlapping interval problems.

```java
Arrays.sort(intervals, (a, b) -> a[0] - b[0]);
List<int[]> result = new ArrayList<>();
int[] curr = intervals[0];

for (int[] interval : intervals) {
    if (interval[0] <= curr[1]) {
        curr[1] = Math.max(curr[1], interval[1]); // merge
    } else {
        result.add(curr);
        curr = interval;
    }
}
result.add(curr);
```

**Problems:** Merge Intervals, Insert Interval, Non-Overlapping Intervals, Meeting Rooms

---

### Pattern 10: Tree Traversal Patterns

**Level Order (BFS):**
```java
Queue<TreeNode> q = new LinkedList<>();
q.offer(root);
while (!q.isEmpty()) {
    int size = q.size(); // process level by level
    for (int i = 0; i < size; i++) {
        TreeNode node = q.poll();
        if (node.left != null) q.offer(node.left);
        if (node.right != null) q.offer(node.right);
    }
}
```

**DFS with Return Value (Post-order):**
```java
int dfs(TreeNode node) {
    if (node == null) return 0;
    int left = dfs(node.left);
    int right = dfs(node.right);
    // use left/right to compute answer at this node
    return /* something based on left, right, node.val */;
}
```

---

### Pattern 11: Topological Sort

**When:** Dependency ordering, course schedule, build order.

**Kahn's Algorithm (BFS-based):**
```java
// 1. Build indegree array
// 2. Add all nodes with indegree 0 to queue
// 3. Process queue: decrement neighbors' indegree, add 0-indegree to queue
// 4. If result size != numNodes → cycle exists
```

---

### Pattern 12: Union-Find (Connected Components)

**When:** Dynamic connectivity, grouping, Kruskal's MST.

```java
int[] parent = new int[n];
int[] rank = new int[n];
Arrays.fill(parent, -1);

int find(int x) {
    if (parent[x] < 0) return x;
    return parent[x] = find(parent[x]);
}

boolean union(int x, int y) {
    int px = find(x), py = find(y);
    if (px == py) return false;
    if (rank[px] < rank[py]) { parent[px] = py; }
    else if (rank[px] > rank[py]) { parent[py] = px; }
    else { parent[py] = px; rank[px]++; }
    return true;
}
```

---

## 📅 Suggested Study Plan

### Week 1–2: Arrays, Strings, Complexity
- Big-O analysis
- Arrays, sliding window, two pointers
- 20–25 easy LeetCode problems

### Week 3–4: Linked Lists, Stacks, Queues, HashMaps
- Pointer manipulation, fast/slow pointers
- Monotonic stack, frequency maps
- 20–25 easy/medium problems

### Week 5–6: Trees & Graphs
- All traversal types
- BFS/DFS on grids
- 25–30 medium problems

### Week 7–8: Sorting, Binary Search, Heaps
- Sorting algorithms from scratch
- Binary search on answer
- Top-K pattern
- 20–25 medium problems

### Week 9–10: Backtracking & Greedy
- Subsets, permutations, combinations
- Interval scheduling
- 15–20 medium/hard problems

### Week 11–14: Dynamic Programming
- Start 1D → 2D → Knapsack → String DP
- 25–30 medium/hard problems

### Week 15+: Mock Interviews & Review
- Timed LeetCode contests
- Review weak areas
- System design introduction

---

## 🛠️ Recommended Resources

| Resource                     | Type         | Best For                          |
|------------------------------|--------------|-----------------------------------|
| LeetCode                     | Practice     | Interview prep, pattern drilling  |
| NeetCode.io                  | Video+Guide  | Curated roadmap with explanations |
| Blind 75 / Grind 75          | Problem list | Essential problem set             |
| "Algorithm Design" (Kleinberg)| Book        | Theory and proofs                 |
| "CLRS" (Introduction to Algo)| Book         | Deep academic reference           |
| Striver's A2Z DSA Sheet      | Sheet        | Comprehensive topic list          |
| Codeforces / AtCoder         | Competitive  | Advanced problem solving          |

---

## 🔑 Interview Tips

1. **Think out loud** — explain your approach before coding
2. **Start with brute force** — then optimize step by step
3. **Discuss trade-offs** — time vs space
4. **Handle edge cases** — empty input, single element, negatives, duplicates
5. **Know your Java collections API** — don't reinvent the wheel
6. **Practice complexity analysis** — always state your Big-O at the end
7. **Learn to recognize patterns** — most problems are variations of 15–20 patterns

---

*Last updated: 2026. Good luck on your DSA journey! 🚀*
