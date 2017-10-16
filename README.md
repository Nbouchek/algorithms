# Algorithms

## [1. Codidlity](https://codility.com/programmers/)
### Lesson 1 Iterations
* **[BinaryGap](https://github.com/Nbouchek/algorithms/wiki/BinaryGap)**: Find the longest sequence of zeros in a binary representation of an integer. 

<div class="begin-examples"></div>

<details><summary>   1. Solution in Java</summary>
<p>

```java
public int solution(int number) {
   int longestSequence = 0;
   int count = -1;
   int rightBit = 0;

   while (number > 0) {
      // get right most bit & shift right
      rightBit = number & 1;
      number = number >> 1;

      if (0 == rightBit && count >= 0) {
         count++;
      }

      if (1 == rightBit) {
         longestSequence = count > longestSequence ? count : longestSequence;
	 count = 0;
      }
   }

   return longestSequence;
}
```
</p></details>
<details><summary> 2. Solution in Python</summary>
<p>

```python
def solution(N):
    count = 0
    longest = 0
    found_one = False
 
    i = N    
         
    while i:
        if i & 1 == 1:
            if (found_one == False):
                found_one = True
            else:
                longest = max(longest,count)
            count = 0
        else:
            count += 1
        i >>= 1
    
    return longest
```
</p></details>

* **Complexity**

   | Time                 | Space               | Score |
   | -------------------- |:-------------------:| -----:|
   | **O(log(n))**        | **O(1)**            | 100%  |

### Lesson 2 Arrays
* OddOccurrencesInArray
* CyclicRotation

### Lesson 3 Time Complexity
* FrogJmp
* PermMissingElem
* TapeEquilibrium

### Lesson 4 Counting Elements
* PermCheck
* FrogRiverOne
* MissingInteger
* MaxCounters (respectable)

### Lesson 5 Prefix Sums
* CountDiv
* PassingCars
* GenomicRangeQuery (respectable)
* MinAvgTwoSlice (respectable)

### Lesson 6 Sorting
* Distinct
* Triangle
* MaxProductOfThree
* NumberOfDiscIntersections (respectable)

### Lesson 7 Stacks and Queues
* StoneWall
* Brackets
* Nesting
* Fish

### Lesson 8 Leader
* EquiLeader
* Dominator

### Lesson 9 Maximum slice problem
* MaxDoubleSliceSum
* MaxProfit
* MaxSliceSum

### Lesson 10 Prime and composite numbers
* MinPerimeterRectangle
* CountFactors
* Peaks (respectable)
* Flags (respectable)

### Lesson 11 Sieve of Eratosthenes
* CountSemiprimes
* CountNonDivisible (respectable)

### Lesson 12 Euclidean algorithm
* ChocolatesByNumbers
* CommonPrimeDivisors (respectable)

### Lesson 13 Fibonacci numbers
* Ladder (respectable)
* FibFrog (respectable)

### Lesson 14 Binary search algorithm
* MinMaxDivision
* NailingPlanks (respectable)

### Lesson 15 Caterpillar method
* AbsDistinct
* CountDistinctSlices
* CountTriangles
* MinAbsSumOfTwo (respectable)

###  Lesson 16 Greedy algorithmsMaxNonoverlappingSegments
* TieRopes

###  Lesson 17 Dynamic programming
* NumberSolitaire (respectable)
* MinAbsSum (ambitious)

***
 
