# data-structures-and-algorithms

Arrays are used to store a list of items like strings, numbers, objects, etc. .
These items get stored sequentially in memory. If you need to store a list of items and access them
by their index arrays are the optimal data structure with a lookup time of O(1), insert O(n), delete O(n).

```java
public class Main {
    public static void main(String[] args) {
        // int[] numbers = new int[3]
        int[] numbers = {10, 20, 30}
        // numbers[0] = 10;
        // numbers[0] = 20;
        // numbers[0] = 30;
        System.out.println(Arrays.toString(numbers))
    }
}
```

```java
public class Array {
    public int[] items;
    private int count;

    public Array(int length) {
        items = new int[length];
    }

    public void insert(int item) {
        items[count++] = item;
    }

    public void print() {
        for (int i = 0; i < count.length; i++) {
        System.out.println(items[i])
        }
    }
}
```