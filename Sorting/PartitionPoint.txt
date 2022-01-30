/*Given an unsorted array of integers. Find an element such that all 
the elements to its left are smaller and to its right are greater. 
Print -1 if no such element exists. Note that there can be more than 
one such element. In that case print the first such number
 occurring in the array.

Example 1:

Input: N = 7, arr[] = {4, 3, 2, 5, 8,  
                                6, 7} 
Output: 5
Explanation: To the left of element 5 
every element is smaller to it and to 
the right of eleement 5 every element 
is greater to it.  */ 


import java.io.*;
import java.util.*;


// Driver class
class Array {

    // Driver code
    public static void main(String[] args) throws IOException {
        // Taking input using buffered reader
        BufferedReader br =
            new BufferedReader(new InputStreamReader(System.in));

        int testcases = Integer.parseInt(br.readLine());
        // looping through all testcases
        while (testcases-- > 0) {
            int n = Integer.parseInt(br.readLine());
            //            String line = br.readLine();
            //            String[] a2 = line.trim().split("\\s+");
            //            int n =Integer.parseInt(a2[0]);
            //            int m =Integer.parseInt(a2[1]);
            // int y =Integer.parseInt(a2[2]);
            String line1 = br.readLine();
            String[] a1 = line1.trim().split("\\s+");
            long a[] = new long[n];
            for (int i = 0; i < n; i++) {
                a[i] = Long.parseLong(a1[i]);
            }
            Solution ob = new Solution();
            // ArrayList<Long> ans=ob.smallestDifferenceTriplet(a,b,c,n);
            long ans = ob.FindElement(a, n);
            System.out.println(ans);
        }
    }
}
// } Driver Code Ends


// User function Template for Java

class Solution {
    long FindElement(long arr[], int N) {
        
        for(int i=0;i<N;i++)
        {
            int flag=0;
            for(int j=0;j<i;j++)
                if(arr[j]>=arr[i])
                {flag=1;
                break;
                }
            
            for(int j=i+1;j<N;j++)
                if(arr[j]<=arr[i])
                {
                    flag=1;
                    break;
                }
            if(flag==0)
                return arr[i];
        }
        return -1;
    }
}
