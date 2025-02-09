## **1. Sliding Window Technique**
### **Introduction**
- Used for problems involving **contiguous subarrays** or **subsequences**.
- Efficient in solving problems with **O(n) complexity** instead of O(n²).
- Works by maintaining a **window** (range of indices) that slides through the array.

### **Types of Sliding Window**
1. **Fixed-size window** (constant window size)
2. **Variable-size window** (window size changes dynamically)

---

### **Fixed-Size Sliding Window**
- Used when the problem specifies a **fixed window size `k`**.
- Example: Find the **maximum sum of a subarray of size `k`**.

#### **Example: Maximum sum of subarray of size `k`**
```java
public class SlidingWindowFixed {
    public static int maxSumSubarray(int[] arr, int k) {
        int maxSum = 0, windowSum = 0;
        
        // First window sum
        for (int i = 0; i < k; i++) {
            windowSum += arr[i];
        }
        maxSum = windowSum;

        // Sliding the window
        for (int i = k; i < arr.length; i++) {
            windowSum += arr[i] - arr[i - k]; // Add new element, remove first element of the window
            maxSum = Math.max(maxSum, windowSum);
        }
        
        return maxSum;
    }

    public static void main(String[] args) {
        int[] arr = {2, 1, 5, 1, 3, 2};
        int k = 3;
        System.out.println(maxSumSubarray(arr, k)); // Output: 9
    }
}
```

---

### **Variable-Size Sliding Window**
- Used when the problem requires **finding the smallest/largest subarray** that meets a condition.

#### **Example: Smallest subarray with sum ≥ `S`**
```java
public class SlidingWindowVariable {
    public static int minSubarrayLen(int[] arr, int S) {
        int minLength = Integer.MAX_VALUE;
        int left = 0, sum = 0;

        for (int right = 0; right < arr.length; right++) {
            sum += arr[right]; // Expand window

            while (sum >= S) { // Contract window
                minLength = Math.min(minLength, right - left + 1);
                sum -= arr[left++];
            }
        }
        
        return (minLength == Integer.MAX_VALUE) ? 0 : minLength;
    }

    public static void main(String[] args) {
        int[] arr = {2, 3, 1, 2, 4, 3};
        int S = 7;
        System.out.println(minSubarrayLen(arr, S)); // Output: 2
    }
}
```

---

## **2. Two-Pointer Technique**
### **Introduction**
- Used when solving **sorted arrays, searching, or pair problems**.
- Instead of **nested loops**, we use two pointers to **reduce time complexity**.

### **Types of Two-Pointer Approaches**
1. **Opposite ends**: One pointer at the start, another at the end (e.g., **two-sum** in sorted arrays).
2. **Same direction**: Both pointers move from the start (e.g., merging two sorted arrays).

---

### **Example: Two-Sum in Sorted Array (Opposite Ends)**
```java
public class TwoPointer {
    public static boolean twoSumSorted(int[] arr, int target) {
        int left = 0, right = arr.length - 1;

        while (left < right) {
            int sum = arr[left] + arr[right];

            if (sum == target) return true;
            else if (sum < target) left++; // Move left pointer forward
            else right--; // Move right pointer backward
        }
        
        return false;
    }

    public static void main(String[] args) {
        int[] arr = {1, 2, 3, 4, 6};
        int target = 6;
        System.out.println(twoSumSorted(arr, target)); // Output: true (2+4)
    }
}
```

---

### **Example: Remove Duplicates from Sorted Array (Same Direction)**
```java
public class RemoveDuplicates {
    public static int removeDuplicates(int[] arr) {
        if (arr.length == 0) return 0;
        
        int j = 1; // Points to the next unique position
        
        for (int i = 1; i < arr.length; i++) {
            if (arr[i] != arr[i - 1]) {
                arr[j++] = arr[i]; // Place the unique element
            }
        }
        
        return j; // Length of the unique array
    }

    public static void main(String[] args) {
        int[] arr = {1, 1, 2, 2, 3, 4, 4};
        System.out.println(removeDuplicates(arr)); // Output: 4 (Unique elements: [1, 2, 3, 4])
    }
}
```

---

## **When to Use These Techniques?**
| **Scenario**                        | **Technique**      |
|--------------------------------------|--------------------|
| Subarray problems (sum, max, min)    | Sliding Window    |
| Problems with sorted arrays          | Two-Pointer       |
| Finding pairs that sum to `X`        | Two-Pointer       |
| Finding longest/shortest subarray    | Sliding Window    |
| Removing duplicates in sorted array  | Two-Pointer       |
