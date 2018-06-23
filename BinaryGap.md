## Main idea
Use the rightmost bit
## Java
```java
/**                                                                                                                                                             
 *                                                                                                                                                              
 */                                                                                                                                                             
package com.nacer.train2excel.iterations;                                                                                                                       
                                                                                                                                                                
/**                                                                                                                                                             
 * @author Nacer                                                                                                                                                
 *                                                                                                                                                              
 */                                                                                                                                                             
public class BinaryGap {                                                                                                                                        
	/**                                                                                                                                                         
	 * @param args                                                                                                                                              
	 *            A binary gap within a positive integer N is any maximal sequence                                                                              
	 *            of consecutive zeros that is surrounded by ones at both ends in                                                                               
	 *            the binary representation of N. For example, number 9 has binary                                                                              
	 *            representation 1001 and contains a binary gap of length 2. The                                                                                
	 *            number 529 has binary representation 1000010001 and contains two                                                                              
	 *            binary gaps: one of length 4 and one of length 3. The number 20                                                                               
	 *            has binary representation 10100 and contains one binary gap of                                                                                
	 *            length 1. The number 15 has binary representation 1111 and has no                                                                             
	 *            binary gaps. The number 32 has binary representation 100000 and                                                                               
	 *            has no binary gaps.                                                                                                                           
	 *                                                                                                                                                          
	 *            Write a function: class Solution { public int solution(int N); }                                                                              
	 *            that, given a positive integer N, returns the length of its                                                                                   
	 *            longest binary gap. The function should return 0 if N doesn't                                                                                 
	 *            contain a binary gap.                                                                                                                         
	 *                                                                                                                                                          
	 *            For example, given N = 1041 the function should return 5, because                                                                             
	 *            N has binary representation 10000010001 and so its longest binary                                                                             
	 *            gap is of length 5. Given N = 32 the function should return 0,                                                                                
	 *            because N has binary representation '100000' and thus no binary                                                                               
	 *            gaps. Assume that: N is an integer within the range                                                                                           
	 *            [1..2,147,483,647].                                                                                                                           
	 *                                                                                                                                                          
	 *            Complexity: - expected worst-case time complexity is O(log(N)); -                                                                             
	 *            expected worst-case space complexity is O(1).                                                                                                 
	 *                                                                                                                                                          
	 *            Copyright 2009–2018 by Codility Limited. All Rights Reserved.                                                                                 
	 *            Unauthorized copying, publication or disclosure prohibited.                                                                                   
	 */                                                                                                                                                         
                                                                                                                                                                
	/**                                                                                                                                                         
	 * @param N                                                                                                                                                 
	 * @return                                                                                                                                                  
	 */                                                                                                                                                         
	public int solution(int N) {                                                                                                                                
		int longestSequence = 0;                                                                                                                                
		int count = -1;                                                                                                                                         
		int rightMostBit = 0;                                                                                                                                   
                                                                                                                                                                
		while (N > 0) {                                                                                                                                         
			// get the right most bit                                                                                                                           
			rightMostBit = N & 1;                                                                                                                               
                                                                                                                                                                
			// shift right                                                                                                                                      
			N = N >> 1;                                                                                                                                         
                                                                                                                                                                
			if (0 == rightMostBit && count >= 0) {                                                                                                              
				count++;                                                                                                                                        
			}                                                                                                                                                   
                                                                                                                                                                
			if (1 == rightMostBit) {                                                                                                                            
				longestSequence = count > longestSequence ? count : longestSequence;                                                                            
				count = 0;                                                                                                                                      
			}                                                                                                                                                   
		}                                                                                                                                                       
                                                                                                                                                                
		return longestSequence;                                                                                                                                 
	}                                                                                                                                                           
                                                                                                                                                                
	public static void main(String[] args) {                                                                                                                    
		BinaryGap binaryGap = new BinaryGap();                                                                                                                  
		Integer N = 657648742;                                                                                                                                  
		System.out.println("--------------------------------");                                                                                                 
		System.out.println("Length of the longest binary gap");                                                                                                 
		System.out.println("--------------------------------");                                                                                                 
		System.out.println("   N = " + N + "\n   BinaryString(" + N + ") = " + Integer.toBinaryString(N)                                                        
				+ "\n   LongestBinaryGap(" + N + ") = " + binaryGap.solution(N) + "\n");                                                                        
	}                                                                                                                                                           
}                                                                                                                                                               
                                                                                                                                                                
```

`
N = 10100000100011101010;`<br/>`Longest binaryGap = 5`
http://tpcg.io/0uFCK1 

<a href="http://tpcg.io/0uFCK1 " target="_blank">Here is a live Demo</a>


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
