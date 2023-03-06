1. What are the factors on which method overloading depends on? Is return type of a method one of them?

- Method overloading is a feature that allows a class to have multiple methods with the same name, but with different parameters. There are 3 factors affecting method overloading in Java:

- Number of parameters in the method.
- Data type of parameters.
- Order of parameters.

- The return type of a method **doesn't** affect method overloading. So if we have two functions with same parameter count, sequence and datatype but different return type, it will throw an error.

---

2. Write a program to reverse each word in a string without reversing the characters in the word.<p>Eg: This is a word &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Output: word a is This</p>

```java
public class ReverseWord {
    public static void main(String[] args) {
        String s = "This is a string";
        System.out.println(wordReverse(s));
    }

    public static String wordReverse(String s) {
        String[] words = s.split(" ");
        String temp = "";
        for(int i = 0, j = words.length - 1; i < j; i++, j--) {
            temp = words[i];
            words[i] = words[j];
            words[j] = temp;
        }

        String result = "";
        for(int i = 0; i < words.length; i++) {
            result += words[i] + " ";
        }

        return result.trim();
    }
}

```
