# **Arrays in Java**

## **1. Introduction**
- An **array** is a collection of elements of the **same data type** stored in contiguous memory locations.
- Arrays in Java are **fixed in size** once initialized.

## **2. Declaration and Initialization**
### **Declaration**
```java
// Syntax: dataType[] arrayName;
int[] arr;   // Preferred way
int arr2[];  // Allowed but less common
```
### **Instantiation and Initialization**
```java
// Allocate memory and initialize
int[] arr = new int[5]; // Creates an array of size 5 with default values (0 for int)
```
```java
// Direct Initialization
int[] arr = {10, 20, 30, 40, 50};
```

## **3. Accessing Elements**
- Array elements are accessed using an **index** (0-based indexing).
```java
System.out.println(arr[0]); // Access first element
```
- **Updating an element**
```java
arr[2] = 100; // Changes the third element to 100
```

## **4. Length of an Array**
- The `length` property gives the size of the array.
```java
System.out.println(arr.length); // Prints number of elements
```

## **5. Iterating Through an Array**
### **Using a for loop**
```java
for (int i = 0; i < arr.length; i++) {
    System.out.println(arr[i]);
}
```
### **Using an enhanced for loop**
```java
for (int num : arr) {
    System.out.println(num);
}
```

## **6. Multidimensional Arrays**
- Java supports **2D and multi-dimensional arrays**.
### **Declaration and Initialization**
```java
int[][] matrix = new int[3][3]; // 3x3 matrix
```
```java
int[][] matrix = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};
```
### **Accessing Elements**
```java
System.out.println(matrix[1][2]); // Prints element at row 1, column 2
```

## **7. Array Methods**
### **Sorting an Array**
```java
import java.util.Arrays;

int[] numbers = {5, 2, 8, 1, 9};
Arrays.sort(numbers); // Sorts in ascending order
```
### **Filling an Array**
```java
Arrays.fill(arr, 7); // Fills the entire array with 7
```
### **Copying an Array**
```java
int[] newArr = Arrays.copyOf(arr, arr.length);
```

## **8. Common Mistakes**
- **Accessing an index out of bounds**
```java
System.out.println(arr[10]); // Throws ArrayIndexOutOfBoundsException
```
- **Using `==` instead of `Arrays.equals()` for comparison**
```java
int[] a = {1, 2, 3};
int[] b = {1, 2, 3};

System.out.println(a == b); // false (compares references)
System.out.println(Arrays.equals(a, b)); // true (compares values)
```

## **9. Dynamic Arrays**
- Java arrays have **fixed sizes**, but you can use `ArrayList` from `java.util` for dynamic resizing.
```java
import java.util.ArrayList;

ArrayList<Integer> list = new ArrayList<>();
list.add(10);
list.add(20);
System.out.println(list.get(0)); // Prints 10
```
