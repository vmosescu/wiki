# Complexity Theory (Big O Notation)
- time
- space
- other: network, graphics, hardware

- every case, best case, average case, worst case, expected case

Big O Notation
- worst case
- asymptotic bahaviour: problem size becomes large
1. if f(N) steps, then it is O(f(N)) -> O(N)
2. if f(N) steps followed by g(N) steps O(f(N)+g(N)) -> O(N+N) = O(2N)
3. if f(N) > g(N) for large N then O(f(N)+g(N)) = O(f(N))): O(N2 + N) = O(N2) ; O(C + f(N)) = O(f(N))
4. if g(N) steps for each of f(N) -> O(f(N)*g(N)): O(N*N) = O(N2)
5. ignore constant multiples: O(C*(N)) = O(f(N)) ; O(f(C*N)) = O(f(N)

O(Log N): divide a search space into 2 pieces at each step
O(2powerN) == O(2*2*....*2): 
O(N!): arangements of items

Log N < Sqrt N < N < N*N < 2*...*2 < N!

----------------------------------------------------------------------------------------------------------------------------------------------

# Numerical Algorithms

# Linked Lists
## Single Linked Lists
- add, remove
- sentinel for top: nuse mai trateaza in mod special inceputul listei
## Sorted Linked Lists
- add: find position, then add
- sentinel for end (infinite)
## Sorting Items
- empty sorted linked listei
- add each item to the listei
- Iterate over the list to pull the values in sorted order
best case (inversate): fiecare se introduce la inceputul listei; in final avem O(N)
worst case (sunt deja sortate): O(N*N)
expected case: fiecare se introduce la mijlocul listei: rezulta tot O(N*N)
## Doubly Linked Lists

# Arrays
## One-Dimensional Arrays
## Triangular Arrays: save more than half the space (increase time to access)
- Two dimensional Array with only a half
- transformata in one-dimensional trebuie tinut minte cati itemi sunt pe fiecare linie (+1 la fiecare linie)
- mapping rows and columns: algoritm care tine seama de chestia de mai sus: memoreaza o triangular array in one-dimensional araay
## Sparse Arrays
- tot matrice (pot exista doar cativa itemi pe linie/coloana si linii/coloane goale)
- linked list of a linked list
- daca exista LinkedList doar pt linii, atunci nu se poate traversa decat pe linii
- daca exista LinkedList si pe coloane atunci se poate traversa si pe coloane
- Cell: rowNumber, NextRow, ColumnNumber, NextColumn, Value

----------------------------------------------------------------------------------------------------------------------------------------------

# Stacks And Queues
## Stacks
- LIFO
- push, pop
- implementations: LinkedList, Array (initially allocate the array)
## Stack Algorithm
- reversing a stack
- Hanoi (3 stacks)
- item processing: until stack is empty
## Double Stack
- you should know that their combined number of items never exceeds a certain maximum amount
- e.g. divide a number of objects into two groups
## Queues
- FIFO
- Enque, Dequeue
- push, pull
- implementations: DoubleLinked Lists
- item processing: until queue isn't empty, pull
- Circular Queues: implemention Array: bottom, top
- Double-Ended Queues: Dequeue, Dequeue (DoubleLinked Lists)

----------------------------------------------------------------------------------------------------------------------------------------------

# Sorting
- O(N), O(N*N), O(N*LogN)=GOLD

## InsertionSort
- find the position  and insert
- SortedLinkedList
 - worst case (already sorted): 
	1+2+3+...+N = N*(N-1)/2 = 1/2(N*N - N) = O(N*N)
 - bast case (in reverse order)
	1+1+.....+1 = N = O(N)
 - random (il inserampe la jumatate)
	1/2 1 + 1/2 2 + 1/2 3 + .......+ 1/2 N = 1/2(1+2+...+N) = 1/4(N*N - N) = O(N*N)
- Array
 - 2 arrays
 - very hard to insert in the middle
 - 1+2+3+...N = O(N*N)
 - or one single array: push the item and inserted it where to belongs

## SelectionSort
- invers decat la insertions
- gaseste itemul ce trebuie inserat la acea pozitie (ex. min la poz 1, etc.)
- gaseste minimul in itemii ramasi si se insereaza la sfarsitul itemilor deja sortati
- for p=1 to N: find the smallest remaining item and insert the item in position p
- 2 LinkedLists: O(N*N)
- 2 arrays or single array
- another: stacks and queues

## QuickSort
Overview:
 - divide the items into 2 groups
 - call Quicksort for first group
 - call Quicksort for second group

Array based algoritm
- pick a divided number (e.g. first), divide in 2 groups (mai mici si mai mari) and put the number between them
- 2 arrays
- one array and use left, right positions

O(N*LogN) if picked item divide in 2 equals gropus
O(N*N) if picked item makes only one group (is the smallest)
another problem: duplicates

## HeapSort
### Heap
- complete binary tree
- every node's value is at least as big as the values of its children
- complete: 
    all of the leaf nodes are in the bottom two levels of the tree and 
	all of the leaves are pushed to the left
- If a complete binary tree contains n nodes, then it is order (log n) levels tall
- algoritm
  Add new value to the bottom
  Repeat
    compare the value to its parent
	if the parent is larger, you're done
	else swap the value with its parent
- add each node: O(Log N)
- add N nodes: (N*LogN)
### Sort
- Algorithm:
    Add all items to a heap
    Repeat until the heap is empty:
      remove the root
      move the last value to the root
      push the value down (swap with the greatest child) to fix the heap
- Repeat: one node: LogN - inaltimea tree -> n nodes: N*LogN
- add: N*LogN
- total N*LogN + N*Logn -> O(N*LogN)
### Array implementation
- childrens of node P:
  - 2*P + 1
  - 2*P + 2
  - grater than array, then there has no child there
- parent of node C:
  - (C-1) / 2 (round down)


## MergeSort
~ quicksort
- Algoritm:
  divide in 2 equals sized lists
  recursivly sort each list
  combine them
- O(N*LogN): always - does not depennd on initial sort or duplicates
- memoria poate fi mai mica pt ca poate lucra la un moment dat doar cu jumatate

## BubleSort
- O(N*Max(K))
- worst case: inverse order O(N*N)
- for very small arrays
- optimisation:
  - alternate scans up and down (down: un item se muta mai multe pozitii in jos; in sus se poate muta doar o singura pozitie)
  - nu se mai scaneaza cele deja ordonate
  
## CountingSort
- nu face comparatii intre itemi, deci sparge bariera O(N*LogN)
- daca range este limitat
- Algoritm
  se aloca un array de dimensiunea range (Max-Min) cu 0
  +1 de fiecare data cand apare nr respectiv
  se scot din acest array si se pun de cate ori apar
- O(M+N)

----------------------------------------------------------------------------------------------------------------------------------------------
# Searching

## Linear Search
for(i=0; i<N; i++)

## Binary Search
- if you have sorted data

## Interpolation Search
- sorted + the values are fairly evenly distributed

----------------------------------------------------------------------------------------------------------------------------------------------
# Hash Tables

## Hash Tables
~ dictionaries
- Need:
  - data structure
  - hash function
  - collision resolution policy
- fast insertion and retrieval, but
- needs extra space

## Chaining
- e.g. hash function: last digit = index of the array
- add a linked list for collisions: top is the first item
- bucket
- optimisations:
  - use sentinel
  - use sorted linked lists

## Open Addressing - Basic
- probe sequence
- follow probe seq until you find an empty spot; after N tries, give up -> resize

## Open Addressing - Linear Probing
P(i+1) = P(i) + C
- primary clustering problem: se formeaza clustere si nu e bine

## Open Addressing - Quadric Probing
P(i) = K + i*i
- secondary clustering problem: daca prima celula e ocupata se parcurge tot lantul (conform functiei) pana cand se gaseste prima libera

## Open Addressing - Basic Double Hashing
K = H1(key)
C = H2(key)

K + C
K + 2*C
K + 3*C
.....
- poate intra in loop si daca toate sunt ocupate atunci nu o putem pune

----------------------------------------------------------------------------------------------------------------------------------------------
# Recursion

## Recursion Basics
- Runtime (de cate ori se cheama pe ea insasi)
- Memory
- Depth
Stack and Heap Memory

## Fibonaci Numbers
T(N) = C + T(N-1) + T(N-2)
O(Fibonaci(N))
#Leaf nodes = #Internal nodes + 1
#Leaf nodes = Fibonaci(N)

## Tower Of Hanoi
Runtime: O(2->N) (=nodes)

## Korh Curves
- se rupe la jumatate si faci inca 2 (un fractal)
DrawSegment(level ,angle, distance)
  If (level = 0) Then
    Draw the line segment
  Else
    DrawSegment(level - 1, angle, distance / 3)
	DrawSegment(level - 1, angle - 60, distance / 3)
	DrawSegment(level - 1, angle + 60, distance / 3)
	DrawSegment(level - 1, angle, distance / 3)
  Enf If

O(4->N) nodes/runtimes

## Hilbert Curves
~ Korch
level 0 = -
           |
		  -
level N = 4 level (N-1) (with some 90 rotation) + conections between them
O(4->N) runtime / recursive calls

## Gaskets
alt fractal
remove pieces
- Sierpinksi Triangle
  split in 4 and remove the middle
O(3->N) runtime/nodes to draw
3 dimensions: piramid

Sierpinksi Carpet: divide a square in 9 and remove the middle
O(8->N)
3 dimensions: Menger Sponge
O(24->N)


## Removing Tail Recursion
problem: stack size
F(N) = F(N-1) + N
it works until 12,664 on average pc
solution: recursion remove
AddSmaller(N)
  result = 0
  While (N > 0)
    result = result + N
	N = N - 1
  Loop
  Return result

## Removing Recursion With Stacks
use stacks to remove recursion

## Fixing Fibonbaci
stop calculate duplicates
one solution: array with pre-computed values
O(N)
one plus: bottom up approach

## Selections
- subset of items in a set (Aranjamente/Combinari)

## Permutations
- an ordered subset of the items in a set (Aranjamente/Permutari)

----------------------------------------------------------------------------------------------------------------------------------------------
# Backtracking Algorithms

## Backtracking
- use trees
So the question is, how do you search this tree to find the best combination?
First, note that you actually don't need to build the tree: you use a recursive algorithm to search the tree without actually building it.
Use backtracking: examine partial solution.

## The Eight Queens
- algorithm with no optimisations
- optimisations:
  - board is illegal: add another 8*8 array with attacks board and do not try to put queen on this positions
  - on a column/row can be a single quuen

## The Knights Tour
- a lot of possibilities, event with backtracking: 7*7 board in over 1 hour
- you can use Heuristic: a rule that is useful but not guaranteed to produce a perfect result

----------------------------------------------------------------------------------------------------------------------------------------------
# Trees

## Tree Terms
- nodes and branches (links)
- Parent / Child
- Root Node
- Siblings
- Ancestor: any node above another node
- Lowest Common Ancestor: the first ancestor shared by 2 nodes
- Descendent: any node below another node
- Subtree: A node, its descendants, and their branches
- Leaf: a node with no children
- Internal node: a node with at least one child
- Level: the distance from a node to the Root (Root level = 0)
- Height: the longest distance from a node to a leaf
- Tree Height: the height of the root
- Node degree: children no.
- Tree degree: the largest node degree

- Binary tree
- Ordered tree
- Full Tree: 0 or 2 children
- Complete Tree: except last 2 bottom levels AND all leafs are to left
- Perfect Tree: arata frumos :)

## Binary Tree Properties
B = N - 1
Perfect binary tree
  N = 2->(H+1) - 1 for 
  H = Log2(N+1) - 1
  L = 2->H (leaf nodes)
  I = 2->H - 1 (internal nodes)

## Traversals - Preorder
recursive calls for each child
Preorder(node)
  Visit node
  Preorder(node.LeftChild)
  Preorder(node.RightChild)

## Traversals - Postorder
Postorder(node)
  Postorder(node.LeftChild)
  Postorder(node.RightChild)
  Visit node

## Traversals - Inorder
InorderT(node)
  InorderT(node.LeftChild)
  Visit node
  InorderT(node.RightChild)

## Traversals - Breadth-First
by levels
using queues
Algorithm
  create a queue
  add the root to the queue
  as long as the queus insn't empty:
    dequeue a node
	visit that node
	add that node's children to the queue

## Building Sorted Trees
Left < Parent < Right
Finding: O(LogN)
Adding: 

## Editing Sorted Trees
Removing: 

----------------------------------------------------------------------------------------------------------------------------------------------
# Balanced Trees

## Why do you need balanced trees?
add sorted items in a tree: unballanced tree (very skinny)
Finding:  O(LogN) -> O(N)
Adding:   O(LogN) -> O(N)
Removing: O(LogN) -> O(N)

## B-Trees - Basics
nodes = buckets
tree of order k:
  buckets hold at least K values
  buckets hold at most 2*K values
  a bucket with M values has (M + 1) branches
  all leaves are at the same level
used in databases to store indexes for large tables

## B-Trees - Adding
hard logic/work when you have to re-arrange the tree (all siblings are (almoust) full)
When you're adding a new value to a full bucket, you could not bother trying to redistribute values with siblings and just split the bucket.
Of course, now you have two buckets with the fewest allowed number of items. 
So you'll have problems if you want to move an item from one of them. 
As long as you add items more often than you remove them, it may be worth the trade-off. 

## B-Trees - Removing
same problems as for adding when you have to re-arrange buckets

----------------------------------------------------------------------------------------------------------------------------------------------
# Decision Trees

## Definitions
Partition problem: Goal: divide a set of values into 2 equal subsets
From a lot of possibilities there are only few possibilities
you can optimize the algorithm

## Exhaustive Search
search through all possibilities
use recursion

## Branch and Bound
evaluate if a partial solution has any chance to solve the problem

## Heuristics
An algorithm that is likely to give a good result but that isn't guaranteed to produce the best result possible.
You can add other optimizations.
(random) swap
hill climbing

----------------------------------------------------------------------------------------------------------------------------------------------
# Network Algorithms

## Network Terminology
Graphs
## Network Classes
## Depth-First Traversal
## Breadth-First Traversal
## Spanning Trees
minimal spanning tree = spanning tree with the smallest possible total cost
- prim's algorithm
- kruskal's algorithm
## Shortest Paths

----------------------------------------------------------------------------------------------------------------------------------------------





