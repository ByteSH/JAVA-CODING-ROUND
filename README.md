# JAVA-CODING-ROUND

---

#### Click :star: if you like it!!

Every contribution counts, no matter how small. Join me on this exciting journey of open-source collaboration and learning. Together, let's build something amazing! 🚀

---

## 💻 Questions

**1. String IMP methods**

<ul>
<li>Print Length of String "s"</li>
<li>Print Character at 3rd position in Stirng "s".</li>
<li>input : s       output : ksforGeeks.</li>
<li>Print input : s       output : eks.</li>
<li>Concatenate String "s1" and "s2".</li>
<li>Index of "Share" word into string "s4".</li>
<li>Index of "a" word from the last. use string "s".</li>
<li>use equal keywords and find "Geeks"="Geeks" > true& "Geeks"="geeks" > false.</li>
<li>compare "Geeks" and "geeks" by ignoring their case.</li>
<li>convert string to lowercase.</li>
<li>convert string to uppercase.</li>
<li>remove the space from the string "   Hamza".</li>
<li>input : "geeksforgeeks"   output : "teeksforteeks"</li>
<li>use keyword : contains</li>
<li>use keyword : startsWith</li>
<li>use keyword : endsWith</li>
<li>use keyword : isEmpty</li>
<li>use formatted string</li>
<li>using the join keyword.       output : apple, banana, cherry      # your output should be string.</li>
<li>input : "abc123def456"    output : "abc###def### "</li>
</ul>

```java
class Main {
    public static void main(String[] args) {

        String s= "GeeksforGeeks";
        String s1 = "Geeks";
        String s2 = "forGeeks";
        String s4 = "Learn Share Learn";

        System.out.println("s.length() = " + s.length());
        System.out.println("s.charAt(3) = " + s.charAt(3));
        System.out.println("s.substring(3) = " + s.substring(3));
        System.out.println("s.substring(2,5) = " + s.substring(2,5));
        System.out.println("s1.concat(s2) = " + s1.concat(s2));
        System.out.println("s4.indexOf(\"Share\") = " + s4.indexOf("Share"));
        System.out.println("s.lastIndexOf(\"a\") = " + s.lastIndexOf("a"));
        System.out.println("\"Geeks\".equals(\"geeks\") = " + "Geeks".equals("geeks"));
        System.out.println("\"Geeks\".equals(\"Geeks\") = " + "Geeks".equals("Geeks"));
        System.out.println("\"Geeks\".equalsIgnoreCase(\"gEeks\") = " + "Geeks".equalsIgnoreCase("gEeks "));
        System.out.println("\"GeekyMe\".toLowerCase() " + "GeekyMe".toLowerCase());
        System.out.println("\"GeekyME\".toUpperCase() = " + "GeekyME".toUpperCase());
        System.out.println("\" Learn Share Learn \".trim() = " + " Learn Share Learn ".trim());
        System.out.println("\"feeksforfeeks\".replace('f' ,'g') = " + "feeksforfeeks".replace('f' ,'g'));
        System.out.println("s2.contains(s1) = " + s2.contains(s1));
        System.out.println("s1.startsWith(s2) = " + s1.startsWith(s2));
        System.out.println("s1.endsWith(s2) = " + s1.endsWith(s2));
        System.out.println(s.isEmpty());
        String result = String.join(", ", "apple", "banana", "cherry");
        System.out.println(result); // Output: apple, banana, cherry
        System.out.println("abc123def456".replaceAll("\\d", "#"));
    }
}
```

**[:top: Scroll to Top](#java-coding-round)**

---

**2. Create String using : "StringBuffer sb = new StringBuffer("Hello ");" and perform below operations.**
<ul>
<li>Input : Java                        Output : Hello Java</li>
<li>Input : Hello Java                  Output : JavaHello Java</li>
<li>Input : JavaHello Java              Output : JJavaaHello Java</li>
<li>Input : JJavaaHello Java            Output : JvaaHello Java</li>
<li>Input : JvaaHello Java              Output : avaJ olleHaavJ</li>
<li>Input : avaJ olleHaavJ              Output : avJ olleHaavJ</li>
</ul>


```java
class Main {
    public static void main(String[] args) {

        System.out.println("sb.append(\"Java\") = " + sb.append("Java"));

        System.out.println("sb.insert(0, \"Java\") = " + sb.insert(0, "Java"));

        System.out.println("sb.replace(1, 3, \"Java\") = " + sb.replace(1, 3, "Java"));

        System.out.println("sb.delete(1, 3) = " + sb.delete(1, 3));

        System.out.println("sb.reverse() = " + sb.reverse());

        System.out.println("sb.deleteCharAt(2) = " + sb.deleteCharAt(2));
    }
}
```

**[:top: Scroll to Top](#java-coding-round)**

---

**3. Palindrome, Anagram & Armstrong program**

```java
import java.util.Arrays;

public class StringAndNumberChecks {

    // 1. Check if a String is a Palindrome
    public static boolean isPalindrome(String str) {
        if (str == null) return false;
        String cleanStr = str.replaceAll("\\s+", "").toLowerCase();
        int left = 0;
        int right = cleanStr.length() - 1;

        while (left < right) {
            if (cleanStr.charAt(left) != cleanStr.charAt(right)) {
                return false;
            }
            left++;
            right--;
        }
        return true;
    }

    // 2. Check if two Strings are Anagrams
    public static boolean isAnagram(String str1, String str2) {
        if (str1 == null || str2 == null) return false;

        char[] arr1 = str1.replaceAll("\\s+", "").toLowerCase().toCharArray();
        char[] arr2 = str2.replaceAll("\\s+", "").toLowerCase().toCharArray();

        if (arr1.length != arr2.length) return false;

        Arrays.sort(arr1);
        Arrays.sort(arr2);

        return Arrays.equals(arr1, arr2);
    }

    // 3. Check if an Integer is an Armstrong Number
    public static boolean isArmstrong(int number) {
        if (number < 0) return false;

        int digits = String.valueOf(number).length();

        int sum = Arrays.stream(String.valueOf(number).split(""))
                .mapToInt(digit -> (int) Math.pow(Integer.parseInt(digit), digits))
                .sum();

        return sum == number;
    }

    public static void main(String[] args) {
        // --- 1. Palindrome Test ---
        String palStr = "madam";
        System.out.println("Is '" + palStr + "' a Palindrome? " + isPalindrome(palStr));

        // --- 2. Anagram Test ---
        String str1 = "listen";
        String str2 = "silent";
        System.out.println("Are '" + str1 + "' and '" + str2 + "' Anagrams? " + isAnagram(str1, str2));

        // --- 3. Armstrong Test ---
        int num = 153;
        System.out.println("Is " + num + " an Armstrong Number? " + isArmstrong(num));
    }
}
```

**[:top: Scroll to Top](#java-coding-round)**

---

**4. How to find duplicate elements in an array with and without stream**

```java
import java.util.HashSet;
import java.util.Set;

public class DuplicatesWithoutStream {
    public static void main(String[] args) {

	// Without Streams
        int[] numbers = {1, 2, 3, 4, 2, 5, 3, 6};
        Set<Integer> seen = new HashSet<>();

        System.out.print("Duplicates: ");
        for (int num : numbers) {
            if (!seen.add(num)) {
                System.out.print(num + " "); // Output: 2 3 
            }
        }



        System.out.print("Duplicates: ");
        Arrays.stream(numbers)
              .filter(n -> !seen.add(n))
              .distinct() // Optional: Prevents printing the same duplicate twice if it appears 3+ times
              .forEach(n -> System.out.print(n + " ")); // Output: 2 3

    }
}
```

**[:top: Scroll to Top](#java-coding-round)**

---

**5. Counting Element Occurrences**

```java
import java.util.HashMap;
import java.util.Map;

class Main {
    public static void main(String[] args) {

        String s = "Hi my name is Hamza";

        Map<String, Integer> map = new HashMap<>();

        for(String i : s.replace(" ","").split("")){
            map.put(i, map.getOrDefault(i,0)+1);
        }
        map.forEach((k,v)-> System.out.println(k+" : "+v));
    }
}
```

**[:top: Scroll to Top](#java-coding-round)**

---

**6. How to find largest number less than a given number and without a given digit? INPUT : 145,4 | OUTPUT : 139**

```java
public class LargestNumberLess {

    public static void main(String[] args) {
        int number = 145;
        int digit = 4;

        int result = number - 1;
        while (String.valueOf(result).contains(String.valueOf(digit))) {
            result --;
        }
        System.out.println("Result : " + result);
    }
}
```

**[:top: Scroll to Top](#java-coding-round)**

---

**7. How to find all pairs of elements in an array whose sum is equal to given number? INPUT : {4, 5, 7, 11, 9, 13, 8, 12},20 | OUTPUT : (9, 11), (7, 13) and (8, 12)**

```java
class Main {
    public static void main(String[] args) {
        int[] a = {4, 5, 7, 11, 9, 13, 8, 12};
        int sum = 20;

        for (int i = 0; i < a.length; i++)
            for (int j = i + 1; j < a.length; j++)
                if (a[i] + a[j] == sum)
                    System.out.println("(" + a[i] + ", " + a[j] + ")");
    }
}
```

**[:top: Scroll to Top](#java-coding-round)**

---

**8. How to find union & intersection of two arrays in Java?**

```java
import java.util.Arrays;
import java.util.HashSet;

class Main {
    public static void main(String[] args) {
        Integer[] arr1 = {1, 2, 4, 5, 6};
        Integer[] arr2 = {2, 3, 5, 7};

        HashSet<Integer> union = new HashSet<>(Arrays.asList(arr1));
        union.addAll(Arrays.asList(arr2));

        HashSet<Integer> intersection = new HashSet<>();
        Arrays.stream(arr1)
              .filter(x -> Arrays.asList(arr2).contains(x))
              .forEach(intersection::add);

        System.out.println("UNION: " + union);
        System.out.println("INTERSECTION: " + intersection);
    }
}
```

**[:top: Scroll to Top](#java-coding-round)**

---

**9. How to check whether user input is number or not in Java?**

```java
import java.util.Scanner;

public class CheckNumber {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter input: ");

        if (sc.hasNextDouble()) {
            System.out.println("It is a number.");
        } else {
            System.out.println("It is NOT a number.");
        }
        sc.close();
    }
}
```

**[:top: Scroll to Top](#java-coding-round)**

---

**10. How to separate zeros from non-zeros in an array.**

```java
import java.util.Arrays;

public class SeparateZeros {
    public static void main(String[] args) {
        int[] arr = {14, 0, 5, 2, 0, 3, 0};
        int pos = 0;

        for (int i = 0; i < arr.length; i++) {
            if (arr[i] != 0) {
                int temp = arr[i];
                arr[i] = arr[pos];
                arr[pos++] = temp;
            }
        }

        System.out.println(Arrays.toString(arr)); // Output: [14, 5, 2, 3, 0, 0, 0]
    }
}
```

**[:top: Scroll to Top](#java-coding-round)**

---

**11. Selection sort in Java.**

```java
import java.util.Arrays;

public class SelectionSort {
    public static void main(String[] args) {

        int[] arr = {64, 25, 12, 242, 11};

        for(int i = 0; i <= arr.length -2 ; i++){
            for(int j = i+1; j <= arr.length -1 ; j++){
            int left = arr[i];
                if(arr[i] > arr[j]){
                    arr[i] = arr[j];
                    arr[j] = left;
                }
            }
        }
        IO.println(Arrays.toString(arr));  // Output: [11, 12, 25, 64, 242]
    }
}
```

**[:top: Scroll to Top](#java-coding-round)**

---

**12. Reverse the string with preserving the position of spaces. INPUT : I Am Not String | OUTPUT : g ni rtS toNmAI**

```java
public class ReversePreserveSpace {
    public static void main(String[] args) {

        String str = "I Am Not String";
        String str_new = new StringBuffer(str.replace(" ","")).reverse().toString();
        int right = 0;

        for(int i = 0; i <= str.length() -1 ; i++){
            if(str.charAt(i) == ' ') IO.print(' ');
            else{
                IO.print(str_new.charAt(right)); // Output: g ni rtS toNmAI
                right++;
            } 
        }
    }
}
```

**[:top: Scroll to Top](#java-coding-round)**

---

**13. percentage of uppercase, lowercase, digits and special characters in a string.**

```java
public class CharacterPercentage {
    public static void main(String[] args) {
        String str = "Tiger Runs @ 100 km/h";
        int len = str.length(), upper = 0, lower = 0, digits = 0, special = 0;

        for (char c : str.toCharArray()) {
            if (Character.isUpperCase(c)) upper++;
            else if (Character.isLowerCase(c)) lower++;
            else if (Character.isDigit(c)) digits++;
            else special++;
        }

        System.out.printf("Uppercase: %.2f%%\n", (upper * 100.0) / len);
        System.out.printf("Lowercase: %.2f%%\n", (lower * 100.0) / len);
        System.out.printf("Digits:    %.2f%%\n", (digits * 100.0) / len);
        System.out.printf("Special:   %.2f%%\n", (special * 100.0) / len);
    }
}
```

**[:top: Scroll to Top](#java-coding-round)**

---

**14. Find missing number in an array.**

```java
public class MissingNumber {
    public static void main(String[] args) {
        int[] arr = {1, 4, 5, 3, 7, 8, 6};
        int n = 8;

        int expectedSum = n * (n + 1) / 2;
        int actualSum = 0;

        for (int num : arr) actualSum += num;

        System.out.println("Missing Number: " + (expectedSum - actualSum)); // Output: 2
    }
}
```

**[:top: Scroll to Top](#java-coding-round)**

---

**15. Singletone class creation.**

```java
class Singleton {
    private static Singleton singleInstance = null;

    private Singleton() {
        System.out.println("Singleton instance created");
    }

    public static Singleton getInstance() {
        if (singleInstance == null) {
            singleInstance = new Singleton();
        }
        return singleInstance;
    }
}

public class Main {
    public static void main(String[] args) {
        Singleton obj1 = Singleton.getInstance(); // Creates instance
        Singleton obj2 = Singleton.getInstance(); // Returns existing instance

        System.out.println(obj1 == obj2); // Output: true
    }
}
```

**[:top: Scroll to Top](#java-coding-round)**

---

**16. Custome Exception.**

```java
class DivideByZeroException extends Exception {
    public DivideByZeroException(String message) {
        super(message);
    }
}

public class Main {
    public static void main(String[] args) {
        try {
            divide(10, 0);
        } catch (DivideByZeroException e) {
            System.out.println("Caught Exception: " + e.getMessage());
        }
    }

    public static int divide(int a, int b) throws DivideByZeroException {
        if (b == 0) {
            throw new DivideByZeroException("Divide by Zero not allowed.");
        }
        return a / b;
    }
}
```

**[:top: Scroll to Top](#java-coding-round)**

---

**17. Create Thread with Thread & Runnable.**

```java
public class Main {
    public static void main(String[] args) {

        // Method 1: Inline Lambda with Thread
        Thread thread = new Thread(() -> {
            System.out.println("Smart way of running a thread!");
        });
        thread.start();

        // Method 2: Runnable Reference with Lambda
        Runnable fetchPrice = () -> {
            System.out.println("Fetching stock data in background...");
        };

        Thread t1 = new Thread(fetchPrice);
        t1.start();
    }
}
```

**[:top: Scroll to Top](#java-coding-round)**

---

**18. Generics.**

```java
class RepoGenerics<T> {
    private T item;

    public void setItem(T item) {
        this.item = item;
    }

    public T getItem() {
        return item;
    }
}

public class Main {
    public static void main(String[] args) {
        RepoGenerics<Integer> repoGenerics = new RepoGenerics<>();
        repoGenerics.setItem(123);
        System.out.println(repoGenerics.getItem()); // Output: 123
    }
}
```

**[:top: Scroll to Top](#java-coding-round)**

---

**19. Iteration.**

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {

        // Forward Iteration with safe removal
        List<Integer> list1 = new ArrayList<>(Arrays.asList(1, 2, 3, 4, 4));
        Iterator<Integer> iterator = list1.iterator();
        
        while (iterator.hasNext()) {
            if (iterator.next() == 3) {
                iterator.remove();
            }
        }
        System.out.println(list1); // Output: [1, 2, 4, 4]

        // Reverse Iteration
        List<Integer> list2 = new ArrayList<>(Arrays.asList(1, 2, 3, 4, 4));
        ListIterator<Integer> listIterator = list2.listIterator(list2.size());
        
        while (listIterator.hasPrevious()) {
            Integer number = listIterator.previous();
            System.out.print(number + " "); // Output: 4 4 3 2 1 
        }
    }
}
```

**[:top: Scroll to Top](#java-coding-round)**

---
