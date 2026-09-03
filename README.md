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

        int original = number;
        int digits = String.valueOf(number).length();
        int sum = 0;

        while (number > 0) {
            int lastDigit = number % 10;
            sum += Math.pow(lastDigit, digits);
            number /= 10;
        }

        return sum == original;
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

        Map<Character , Integer> map = new HashMap<>();

        for (char a : s.replace(" ","").toCharArray()){
            map.put(a, map.getOrDefault(a,0)+1);
        }
        map.forEach((k,v)-> System.out.println(k+" : "+v));
    }
}
```

**[:top: Scroll to Top](#java-coding-round)**

---
