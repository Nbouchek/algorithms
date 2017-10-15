## Main idea
Use the rightmost bit
## Java
```java
class BinaryGap {
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
}

public class BinaryGapDemo {
   public static void main(String[] args) {
      BinaryGap binaryGap = new BinaryGap();
      Integer integer = 657642;
      System.out.println("N = " + Integer.toBinaryString(integer) + ";\n Longest binaryGap = " + binaryGap.solution(integer));
   }
}
```

`
N = 10100000100011101010;`<br/>`Longest binaryGap = 5`

<a href="http://tpcg.io/b8qURQ" target="_blank">Here is a live Demo</a>


## Python

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

if __name__== "__main__":
    N = 657642
    print "N = " + "{0:b}".format(N) + "\nlongestGap = " + str(solution(N))
```
### Output
`
N = 10100000100011101010` <br/>
`longestGap = 5`

<a href="http://tpcg.io/QxK4V1" target="_blank">Here is a live Demo</a>

## Complexity

   | Time                 | Space               | Score |
   | -------------------- |:-------------------:| -----:|
   | **O(log(n))**        | **O(1)**            | 100%  |
