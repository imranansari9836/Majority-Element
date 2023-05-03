# Majority-Element
Given an array A of N elements. Find the majority element in the array. A majority element in an array A of size N is an element that appears more than N/2 times in the array.
 

Example 1:

Input:
N = 3 
A[] = {1,2,3} 
Output:
-1
Explanation:
Since, each element in 
{1,2,3} appears only once so there 
is no majority element.
Example 2:

Input:
N = 5 
A[] = {3,1,3,3,2} 
Output:
3
Explanation:
Since, 3 is present more
than N/2 times, so it is 
the majority element.

class Solution
{
    static int majorityElement(int a[], int size)
    {
       Arrays.sort(a);
        int c = 0;
        int m = 0;
        if(size == 1){
            return a[0];
        }
        for(int i=1;i<size;i++){
            if(a[i-1] == a[i]){
                c++;
                if(c >= size/2){
                    m = a[i];
                }
            }else{
                c = 0;
            }
        }
        return m == 0? -1: m;
        
        // your code here
    }
}
