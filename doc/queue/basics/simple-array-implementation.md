### Simple Array Implementation

- Java code:

```java
public class Queue {
    private int[] array;
    private int size;
    private int capacity;

    public Queue() {
        capacity = 10; // initial capacity
        q = new int[capacity];
        size = 0;
    }

    public boolean isEmpty() {
        return size == 0;
    }

    public void enqueue(int x) {
        if (size == capacity) {
            throw new IllegalArgumentException();
        }
        q[size++] = x;
    }

    public void dequeue() {
        if (!isEmpty()) {
            for (int i = 1; i < size; i++) {
                q[i - 1] = q[i];
            }
            size--;
        }
    }

    public int getFront() {
        return isEmpty() ? -1 : q[0];
    }

    public void display() {
        for (int i = 0; i < size; i++) {
            System.out.print(q[i] + " ");
        }
        System.out.println();
    }

    public static void main(String[] args) {
        Queue q = new Queue();
        q.enqueue(1);
        q.enqueue(2);
        q.enqueue(3);
        System.out.println(q.getFront());
        q.dequeue();
        q.enqueue(4);
        q.display();
    }
}
```
