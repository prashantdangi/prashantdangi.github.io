---

title: "Algorithms and Computer Networks"
categories: Computers Programming

---

# Fundamental Algorithms

## Recursion
Recursion is a problem-solving approach where a function calls itself to solve smaller instances of a problem. There are two primary methods to analyze recursive algorithms:

### Recursion Tree Method
The recursion tree method provides a visual representation of recursive calls, making it easier to:
- Analyze time complexity
- Understand the flow of recursive calls
- Calculate space complexity

### Master Method
A mathematical approach to analyze divide-and-conquer algorithms with recurrence relations of the form:
T(n) = aT(n/b) + f(n)

## Divide and Conquer
A problem-solving paradigm that breaks down complex problems into smaller, manageable subproblems.

### Key Applications:
1. **Multiplying Large Integers**
   - Breaking down large numbers into smaller chunks
   - Efficient multiplication of multi-digit numbers

2. **Karatsuba Algorithm**
   - Fast multiplication algorithm
   - Reduces time complexity from O(n²) to O(n^log₂3)

3. **Binary Search**
   - Efficient searching in sorted arrays
   - Time complexity: O(log n)

4. **Median of Two Sorted Arrays**
   - Finding the median of combined sorted arrays
   - Optimal solution achieves O(log(min(m,n)))

## Sorting Algorithms

### Merge Sort
- Divide and conquer approach
- Stable sorting algorithm
- Time complexity: O(n log n)

### Quick Sort
- Partition-based sorting
- Average case: O(n log n)
- Widely used in practice

### Bucket Sort
- Distribution-based sorting
- Ideal for uniformly distributed data
- Average case: O(n + k)

### Radix Sort
- Non-comparative integer sorting
- Sorts digits position by position
- Time complexity: O(d * (n + k))

## Greedy Algorithms
Making locally optimal choices at each step to find a global optimum.

### Notable Problems:
1. **Knapsack Problem**
   - Maximizing value while respecting weight constraints
   - Fractional vs 0/1 knapsack

2. **Activity Selection**
   - Scheduling maximum activities
   - Optimal substructure property

3. **Huffman Coding**
   - Data compression technique
   - Variable-length prefix coding

## Strassen Matrix Multiplication
- Efficient matrix multiplication algorithm
- Reduces complexity from O(n³) to O(n^2.807)
- Practical for very large matrices

# Computer Networks

## Why Study Computer Networks?

Networks have become fundamental to modern computing, enabling:
- File and application sharing
- Hardware resource sharing
- Client-server applications
- Voice over IP (VoIP)
- Distributed storage systems

### Network Fundamentals
A network is an interconnected collection of devices (nodes) that can:
- Send and receive data
- Share resources
- Communicate through defined protocols

### Communication Channels
The physical or logical connections between nodes that facilitate data transfer.

## Transmission Modes

### Simplex
- One-way communication
- Example: TV broadcasting

### Half-Duplex
- Two-way communication, but not simultaneous
- Example: Walkie-talkies

### Full-Duplex
- Simultaneous two-way communication
- Example: Phone calls

## Transmission Media

### Guided Media

#### Coaxial Cable
1. **Baseband**
   - Digital transmission
   - Single channel communication

2. **Broadband**
   - Analog transmission
   - Multiple channel support

#### Fiber Optics
- High-speed data transmission
- Immune to electromagnetic interference
- Long-distance communication

#### Twisted Pair
1. **Unshielded (UTP)**
   - Common in LANs
   - Cost-effective solution

2. **Shielded (STP)**
   - Better noise protection
   - Used in noisy environments 