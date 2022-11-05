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
        numbers.insert(50);
        numbers.removeAt(30);
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
        // if the array is full, resize it
        if (items.length == count) {
            // create a new array (twice the size)
            int[] newItems = new int[count * 2];
            // copy all the existing items
            for (int i = 0; i < count; i++) {
                newItems[i] = items[i];
            }
            // set "items" to this new array
            items = newItems;
        }
        items[count++] = item;
    }

    public void removeAt(int index) {
        // validate the index
        if (index < 0 || index >= count) {
            throw new IllegalArguementException();
        }
        // shift the items to the left to fill the whole
        for (int i = index; i < count; i++) {
            items[i] = items[i + 1];
        }

        count--;
    }

    public int indexOf(int item) {
        // if we find it, return index
        // else return -1
        for (int i = 0; i < count; i++) {
            if (items[i] == item) {
                return i;
            }
        return -1;
        }
    }

    public void print() {
        for (int i = 0; i < count.length; i++) {
        System.out.println(items[i])
        }
    }
}
```