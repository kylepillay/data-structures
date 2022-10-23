import java.util.NoSuchElementException;

public class LinkedList {
    private class Node {
        private int value;
        private Node next;

        public Node(int value) {
            this.value =value;
        }
    }
    private Node first;
    private Node last;
    private int size;

    public int size() {
        return this.size;
    }
    
    public void addLast(int value) {
        var node = new Node(value);

        if (isEmpty()) {
            this.first = node;
        } else {
            last.next = node;
        }
        this.last = node;

        this.size++;
    }

    public void addFirst(int value) {
        var node = new Node(value);

        if (isEmpty()) {
            this.first = node;
            this.last = node;
        } else {
            node.next = this.first;
            this.first = node;
        }

        this.size++;
    }

    public int indexOf(int num) {
        var index = 0;
        var current = this.first;

        while(current != null) {
            if (current.value == num) {
                return index;
            } else {
                current = current.next;
                index++;
            }
        }

        return -1;
    }

    public boolean contains(int num) {
        var current = this.first;

        while (current != null) {
            if (current.value == num) {
                return true;
            }

            current = current.next;
        }

        return false;
    }

    public void removeFirst() {
        if (isEmpty()) {
            throw new NoSuchElementException();
        }
        else if (first == last) {
            first = last = null;
        } else {
            var second = first.next;
            first.next = null;
            first = second;
        }

        this.size--;
    }

    public void removeLast() {
        if (isEmpty()) {
            throw new NoSuchElementException();
        }

        if (first == last) {
            first = last = null;
        } else {
            var previous = findPreviousNode(this.last);
            previous.next = null;
        }

        this.size--;

    }

    public int[] toArray() {
        int[] resultArray = new int[size];
        var current = this.first;
        int index = 0;

        while (current != null) {
            resultArray[index] = current.value;
            current = current.next;
            index++;
        }

        return resultArray;
    }

    public void reverse() {
        if (isEmpty()) return;

        var previous = first;
        var current = previous.next;

        while (current != null) {
            var next = current.next;
            current.next = previous;
            previous = current;
            current = next;
        }

        last = first;
        last.next = null;
        first = previous;
    }

    public int getKthFromTheEnd(int k) {
        if (isEmpty())
            throw new IllegalStateException();

        var a = first;
        var b = first;

        for (int i = 0; i < k - 1; i++) {
            b = b.next;
            if (b == null)
                throw new IllegalArgumentException();
        }

        while (b != last) {
            a = a.next;
            b = b.next;
        }

        return a.value;
    }

    public void findMiddleNode() {
        if (isEmpty())
            throw new IllegalStateException();

        var a = first;
        var b = first;

        while (b != last && b.next !=last) {
            b = b.next.next;
            a = a.next;
        }

        if (b == last)
            System.out.println(a.value);
        else
            System.out.println(a.value + ", " + a.next.value);
    }

    private Node findPreviousNode(Node item) {
        var current = first;

        while (current != null) {
            if (current.next == item) return current;
            current = current.next;
        }

        return null;
    }

    private boolean isEmpty() {
        return this.first == null;
    }
}
