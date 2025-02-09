# **Strings in Java**

## **1. Introduction**
- A **String** in Java is a **sequence of characters**.
- It is an **immutable** object, meaning once created, it **cannot be changed**.

## **2. Declaration and Initialization**
```java
// Using String Literal (Stored in String Pool)
String s1 = "Hello"; 

// Using new Keyword (Stored in Heap Memory)
String s2 = new String("Hello");
```

## **3. String Methods**
Java provides several useful methods in the `String` class.

### **Getting Length**
```java
System.out.println(s1.length()); // Returns the length of the string
```

### **Concatenation**
```java
String s3 = s1 + " World"; // Using + operator
String s4 = s1.concat(" World"); // Using concat() method
```

### **Accessing Characters**
```java
char ch = s1.charAt(1); // Gets character at index 1 ('e')
```

### **Substring**
```java
String sub = s1.substring(1, 4); // Extracts "ell" from "Hello"
```

### **Comparing Strings**
```java
String str1 = "Java";
String str2 = "java";

// Case-sensitive comparison
System.out.println(str1.equals(str2)); // false

// Case-insensitive comparison
System.out.println(str1.equalsIgnoreCase(str2)); // true

// Lexicographical comparison (-1, 0, or 1)
System.out.println(str1.compareTo(str2)); // Returns a negative value
```

### **Checking Start and End**
```java
System.out.println(s1.startsWith("He")); // true
System.out.println(s1.endsWith("lo"));   // true
```

### **Searching in a String**
```java
System.out.println(s1.indexOf('e'));   // Returns index of 'e' (1)
System.out.println(s1.contains("ll")); // true
```

### **Replacing Characters**
```java
String replaced = s1.replace('l', 'p'); // "Heppo"
```

### **Converting Case**
```java
System.out.println(s1.toUpperCase()); // "HELLO"
System.out.println(s1.toLowerCase()); // "hello"
```

### **Trimming Whitespaces**
```java
String str = "   Java   ";
System.out.println(str.trim()); // "Java" (removes leading & trailing spaces)
```

## **4. StringBuilder (Mutable Strings)**
- Since `String` is **immutable**, modifications create **new objects**.
- `StringBuilder` is **mutable**, meaning it can be changed without creating new objects.

### **Using StringBuilder**
```java
StringBuilder sb = new StringBuilder("Hello");
sb.append(" World"); // Modifies the same object
System.out.println(sb); // "Hello World"
```

### **Common StringBuilder Methods**
```java
sb.insert(5, " Java");  // Inserts " Java" at index 5
sb.replace(6, 10, "C++"); // Replaces "Java" with "C++"
sb.delete(5, 10); // Deletes characters from index 5 to 9
sb.reverse(); // Reverses the string
```

## **5. Converting Between String and Other Types**
```java
int num = 100;
String strNum = String.valueOf(num); // Convert int to String

String str = "200";
int number = Integer.parseInt(str); // Convert String to int
```

## **6. Splitting a String**
```java
String data = "apple,banana,grape";
String[] fruits = data.split(","); // Splits by ","
```
