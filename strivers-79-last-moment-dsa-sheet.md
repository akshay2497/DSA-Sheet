# Arrays :

1. https://leetcode.com/problems/next-permutation/description/  
My Solution : https://leetcode.com/problems/next-permutation/solutions/1909745/java-easy-two-pointers-algorithm-with-linear-time-and-constant-space/  
Series pb no - arrays and hashing - 1

2. https://leetcode.com/problems/3sum/description/  
My solution : https://leetcode.com/problems/3sum/solutions/6109193/java-easy-solution-with-2-pointers/  
Series pb no - arrays and hashing - 2

4. https://leetcode.com/problems/maximum-subarray/description/  
My solution : https://leetcode.com/problems/maximum-subarray/solutions/6108684/kadane-s-algorithm-o-n-approach/  
Series pb no - arrays and hashing - 3

6. https://leetcode.com/problems/majority-element/description/  
My solution : https://leetcode.com/problems/majority-element/solutions/6109025/java-brute-force-better-and-optimized-approach-with-time-and-space-complexity/  
Series pb no - Not in the series but prerequisite to next problem

7. https://leetcode.com/problems/majority-element-ii/description/  
My Solutionn : https://leetcode.com/problems/majority-element-ii/solutions/6109162/morres-voting-algorithm-approch-with-edge-case-handling-part/  
Series pb no - arrays and hashing - 4

8. https://leetcode.com/problems/set-mismatch/description/  
My Solutionn : https://leetcode.com/problems/set-mismatch/solutions/6112883/java-hashmap-based-solution-with-linear-time-and-space/  
Series pb no - arrays and hashing - 6

9. https://www.geeksforgeeks.org/problems/inversion-of-array-1587115620/1  
Series pb no - arrays and hashing - 7  

My Solution :
```java
class Solution {
    // Function to count inversions in the array.
    static int inversionCount(int arr[]) {
        if (arr.length == 0) {
            return 0;
        }
        return mergeSort(arr, 0, arr.length -1);
    }


	public static int mergeSort(int[] arr, int low, int high) {
	    int cnt = 0;
  		if (low == high) {
  			return cnt;
  		}
  
  		int mid = (low + high) / 2;
  
  		cnt += mergeSort(arr, low, mid);
  		cnt += mergeSort(arr, mid+1, high);
  		cnt += merge(arr, low, mid, high);
  		return cnt;
	}

	public static int merge(int[] arr, int low, int mid, int high) {
  		List<Integer> list = new ArrayList<>();
  
  		int left = low, right = mid+1;
  
      int cnt = 0;
  		while (left <= mid && right <= high) {
  			if (arr[left] <= arr[right]) {
  				  list.add(arr[left++]);
  			} else {
        // If the left element is greater then the element at right that means it will form the pairs with the right element with all elements till mid from left so increment the count by (mid - left +1)
  			    cnt += (mid - left + 1);
  				  list.add(arr[right++]);
  			}
  		}
  
  		while (left <= mid) {
  			list.add(arr[left++]);
  		}
  
  		while (right <= high) {
  			list.add(arr[right++]);
  		}
  
  		for (int i = low; i <= high; i++) {
  			arr[i] = list.get(i - low);
  		}
  		
  		return cnt;
  	}
}
```

Prerequisite merge sort  
Merge sort question: https://www.naukri.com/code360/problems/merge-sort_920442  
Merge sort algorithm :  

```java
public class Solution {
	public static void mergeSort(int[] arr, int n) {
		if (n == 0) {
			return; // Avoid unnecessary operations for an empty array
		}
		mergeSort1(arr, 0, n-1);
	}

	public static void mergeSort1(int[] arr, int low, int high) {
		if (low == high) {
			return;
		}

		int mid = (low + high) / 2;

		mergeSort1(arr, low, mid);
		mergeSort1(arr, mid+1, high);
		merge(arr, low, mid, high);
	}

	public static void merge(int[] arr, int low, int mid, int high) {
		List<Integer> list = new ArrayList<>();

		int left = low, right = mid+1;

		while (left <= mid && right <= high) {
			if (arr[left] <= arr[right]) {
				list.add(arr[left++]);
			} else {
				list.add(arr[right++]);
			}
		}

		while (left <= mid) {
			list.add(arr[left++]);
		}

		while (right <= high) {
			list.add(arr[right++]);
		}

		for (int i = low; i <= high; i++) {
			arr[i] = list.get(i - low);
		}
	}
}
```

10. https://leetcode.com/problems/maximum-product-subarray/description/  
My Solution : https://leetcode.com/problems/maximum-product-subarray/solutions/6114712/java-observation-based-solution-using-prefix-and-suffix-product-o-n-solution/  
Series pb no - arrays and hashing - 8  




