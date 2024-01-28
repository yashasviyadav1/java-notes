
## HEAPS or PRIORITY QUEUE in java

methods of priority queue 
```java
heap.add(element)
heap.peek() // fetch top element of heap
front = heap.remove() // fetch and remove the top of heap
heap.size()
```

```java
public class Main {
    public static void main(String[] args) {
        
        PriorityQueue<Integer> minHeap = new PriorityQueue<>();
        
        minHeap.add(5);        
        minHeap.add(3);
        minHeap.add(8);
        minHeap.add(10);        
        minHeap.add(1);
        minHeap.add(2);
        System.out.println("min Heap : " + minHeap); // [1, 3, 2, 10, 5, 8] 
        System.out.print("Min Heap : "); 
        while(minHeap.size() != 0){ // printing each element of minHeap 1 2 3 5 8 10 
            int top = minHeap.peek();
            minHeap.remove();
            System.out.print(top + " ");
        }
        System.out.println(); 

        
        PriorityQueue<Integer> maxHeap = new PriorityQueue<>(Collections.reverseOrder());
        
        maxHeap.add(5);        
        maxHeap.add(3);
        maxHeap.add(8);
        maxHeap.add(10);        
        maxHeap.add(1);
        maxHeap.add(2);
        System.out.println("max Heap : " + maxHeap); //[10, 8, 5, 3, 1, 2]
        System.out.print("Max Heap : "); 
        while(maxHeap.size() != 0){ // 10 8 5 3 2 1 
            System.out.print(maxHeap.peek() + " ");
            maxHeap.remove();
        }
    }
}
```