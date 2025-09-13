### Simple Array Implementation

[_Back to Queue_](../15-queue.md)

- java code:

```java
public class Queue {
    private int[] array;
    private int size;
    private int capacity;

    public Queue() {
        capacity = 10; // initial capacity
        array = new int[capacity];
        size = 0;
    }

    public boolean isEmpty() {
        return size == 0;
    }

    public void enqueue(int x) {
        if (size == capacity) {
            throw new IllegalArgumentException();
        }
        array[size++] = x;
    }

    public void dequeue() {
        if (!isEmpty()) {
            for (int i = 1; i < size; i++) {
                array[i - 1] = array[i];
            }
            size--;
        }
    }

    public int getFront() {
        return isEmpty() ? -1 : q[0];
    }

    public void display() {
        for (int i = 0; i < size; i++) {
            System.out.print(array[i] + " ");
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

- python code
```python
class Queue:
    def __init__(self):
        self.capacity = 10  # initial capacity
        self.array = [0] * self.capacity
        self.size = 0

    def is_empty(self):
        return self.size == 0

    def enqueue(self, x):
        if self.size == self.capacity:
            raise ValueError("Queue is full")
        self.array[self.size] = x
        self.size += 1

    def dequeue(self):
        if not self.is_empty():
            for i in range(1, self.size):
                self.array[i - 1] = self.array[i]
            self.size -= 1

    def get_front(self):
        return -1 if self.is_empty() else self.array[0]

    def display(self):
        for i in range(self.size):
            print(self.array[i], end=" ")
        print()

if __name__ == "__main__":
    q = Queue()
    q.enqueue(1)
    q.enqueue(2)
    q.enqueue(3)
    print(q.get_front())
    q.dequeue()
    q.enqueue(4)
    q.display()
```