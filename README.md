# Java
## Data Structures
1. **Arrays**
   - `int[] arr = new int[size];`
   - `Arrays.sort(arr);`
   - `for (int num : arr) { ... }`
### Basic Operations
1. **Declaration**:
    ```java
    int[] array;
    ```
2. **Instantiation**:
    ```java
    array = new int[10];
    ```
3. **Initialization**:
    ```java
    int[] array = {1, 2, 3, 4, 5};
    ```
4. **Accessing elements**:
    ```java
    int element = array[0];
    ```
5. **Modifying elements**:
    ```java
    array[0] = 10;
    ```

### Iteration
1. **For loop**:
    ```java
    for (int i = 0; i < array.length; i++) {
        System.out.println(array[i]);
    }
    ```
2. **Enhanced for loop**:
    ```java
    for (int element : array) {
        System.out.println(element);
    }
    ```

### Utility Operations (using `java.util.Arrays`)
1. **Sorting**:
    ```java
    Arrays.sort(array);
    ```
2. **Binary Search**:
    ```java
    int index = Arrays.binarySearch(array, key);
    ```
3. **Copying**:
    ```java
    int[] copy = Arrays.copyOf(array, array.length);
    ```
    ```java
    int[] partialCopy = Arrays.copyOfRange(array, start, end);
    ```
4. **Comparing**:
    ```java
    boolean areEqual = Arrays.equals(array1, array2);
    ```
5. **Filling**:
    ```java
    Arrays.fill(array, value);
    ```
6. **Converting to String**:
    ```java
    String arrayString = Arrays.toString(array);
    ```
7. **Parallel Sort** (for large arrays):
    ```java
    Arrays.parallelSort(array);
    ```

### Advanced Operations
1. **Stream Operations**:
    ```java
    Arrays.stream(array).forEach(System.out::println);
    ```
2. **Splitting an Array**:
    ```java
    int[] firstPart = Arrays.copyOfRange(array, 0, midIndex);
    int[] secondPart = Arrays.copyOfRange(array, midIndex, array.length);
    ```
3. **Concatenating Arrays** (manually):
    ```java
    int[] combined = new int[array1.length + array2.length];
    System.arraycopy(array1, 0, combined, 0, array1.length);
    System.arraycopy(array2, 0, combined, array1.length, array2.length);
    ```

### Miscellaneous Operations
1. **Finding Maximum/Minimum**:
    ```java
    int max = Arrays.stream(array).max().getAsInt();
    int min = Arrays.stream(array).min().getAsInt();
    ```
2. **Sum and Average**:
    ```java
    int sum = Arrays.stream(array).sum();
    double average = Arrays.stream(array).average().getAsDouble();
    ```
3. **Filtering**:
    ```java
    int[] filtered = Arrays.stream(array).filter(n -> n > 10).toArray();
    ```

### Multidimensional Array Operations
1. **Declaration and Initialization**:
    ```java
    int[][] matrix = {{1, 2}, {3, 4}};
    ```
2. **Accessing Elements**:
    ```java
    int element = matrix[0][1];
    ```
3. **Iterating through Elements**:
    ```java
    for (int i = 0; i < matrix.length; i++) {
        for (int j = 0; j < matrix[i].length; j++) {
            System.out.println(matrix[i][j]);
        }
    }
    ```

### List Conversion
1. **Array to List**:
    ```java
    List<Integer> list = Arrays.asList(array);
    ```
2. **List to Array**:
    ```java
    Integer[] newArray = list.toArray(new Integer[0]);
    ```

### Resizing an Array (Inefficient, usually prefer `ArrayList`)
1. **Manual Resizing**:
    ```java
    int[] newArray = new int[newSize];
    System.arraycopy(oldArray, 0, newArray, 0, Math.min(oldArray.length, newSize));
    ```

## Java.util.Arrays
The `java.util.Arrays` class provides various static methods for array manipulation, including sorting, searching, comparing, filling, and converting arrays. Here’s a categorized list of these methods:

### 1. Sorting
- **`sort`**: Sorts the specified array into ascending order.
  ```java
  Arrays.sort(array);
  Arrays.sort(array, fromIndex, toIndex);
  Arrays.sort(array, comparator);
  ```

### 2. Searching
- **`binarySearch`**: Searches the specified array for the specified value using the binary search algorithm.
  ```java
  int index = Arrays.binarySearch(array, key);
  int index = Arrays.binarySearch(array, fromIndex, toIndex, key);
  ```

### 3. Comparing
- **`equals`**: Returns `true` if the two specified arrays are equal to one another.
  ```java
  boolean areEqual = Arrays.equals(array1, array2);
  boolean areEqual = Arrays.equals(array1, array2, comparator);
  ```
- **`deepEquals`**: Returns `true` if the two specified arrays are deeply equal to one another.
  ```java
  boolean areDeepEqual = Arrays.deepEquals(array1, array2);
  ```

### 4. Filling
- **`fill`**: Assigns the specified value to each element of the specified array.
  ```java
  Arrays.fill(array, value);
  Arrays.fill(array, fromIndex, toIndex, value);
  ```

### 5. Copying
- **`copyOf`**: Copies the specified array, truncating or padding with default values if necessary.
  ```java
  int[] newArray = Arrays.copyOf(original, newLength);
  ```
- **`copyOfRange`**: Copies the specified range of the specified array into a new array.
  ```java
  int[] newArray = Arrays.copyOfRange(original, from, to);
  ```

### 6. Converting
- **`toString`**: Returns a string representation of the contents of the specified array.
  ```java
  String arrayString = Arrays.toString(array);
  ```
- **`deepToString`**: Returns a string representation of the "deep contents" of the specified array.
  ```java
  String deepArrayString = Arrays.deepToString(array);
  ```

### 7. Hashing
- **`hashCode`**: Returns a hash code based on the contents of the specified array.
  ```java
  int hashCode = Arrays.hashCode(array);
  ```
- **`deepHashCode`**: Returns a hash code based on the "deep contents" of the specified array.
  ```java
  int deepHashCode = Arrays.deepHashCode(array);
  ```

### 8. Miscellaneous
- **`asList`**: Returns a fixed-size list backed by the specified array.
  ```java
  List<Integer> list = Arrays.asList(array);
  ```
- **`stream`**: Returns a sequential stream with the specified array as its source.
  ```java
  IntStream stream = Arrays.stream(array);
  ```
- **`setAll`**: Sets all elements of the specified array, using the provided generator function to compute each element.
  ```java
  Arrays.setAll(array, index -> value);
  ```
- **`parallelSetAll`**: Sets all elements of the specified array in parallel, using the provided generator function to compute each element.
  ```java
  Arrays.parallelSetAll(array, index -> value);
  ```
- **`parallelSort`**: Sorts the specified array into ascending order, potentially in parallel.
  ```java
  Arrays.parallelSort(array);
  Arrays.parallelSort(array, fromIndex, toIndex);
  Arrays.parallelSort(array, comparator);
  ```

### Summary
- **Sorting**: `sort`, `parallelSort`
- **Searching**: `binarySearch`
- **Comparing**: `equals`, `deepEquals`
- **Filling**: `fill`
- **Copying**: `copyOf`, `copyOfRange`
- **Converting**: `toString`, `deepToString`
- **Hashing**: `hashCode`, `deepHashCode`
- **Miscellaneous**: `asList`, `stream`, `setAll`, `parallelSetAll`

In LeetCode solutions, Java operations and constructs often revolve around common data structures, algorithmic techniques, and utility functions. Here’s a list of some of the most common Java operations and constructs used in LeetCode solutions:

2. **Lists**
   - `List<Integer> list = new ArrayList<>();`
   - `list.add(value);`
   - `list.get(index);`
   - `list.size();`
   - `Collections.sort(list);`

3. **HashMaps**
   - `Map<Integer, Integer> map = new HashMap<>();`
   - `map.put(key, value);`
   - `map.get(key);`
   - `map.containsKey(key);`
   - `map.remove(key);`

4. **HashSets**
   - `Set<Integer> set = new HashSet<>();`
   - `set.add(value);`
   - `set.contains(value);`
   - `set.remove(value);`

5. **Queues**
   - `Queue<Integer> queue = new LinkedList<>();`
   - `queue.offer(value);`
   - `queue.poll();`
   - `queue.peek();`

6. **Stacks**
   - `Stack<Integer> stack = new Stack<>();`
   - `stack.push(value);`
   - `stack.pop();`
   - `stack.peek();`

7. **PriorityQueues (Heaps)**
   - `PriorityQueue<Integer> pq = new PriorityQueue<>();`
   - `pq.offer(value);`
   - `pq.poll();`
   - `pq.peek();`

8. **LinkedLists**
   - `ListNode head = new ListNode(value);`
   - `head.next = new ListNode(value);`

### Algorithmic Techniques
1. **Binary Search**
   - `Arrays.binarySearch(arr, key);`
   - Implementing custom binary search:
     ```java
     int left = 0, right = arr.length - 1;
     while (left <= right) {
         int mid = left + (right - left) / 2;
         if (arr[mid] == target) { ... }
         else if (arr[mid] < target) { left = mid + 1; }
         else { right = mid - 1; }
     }
     ```

2. **Two Pointers**
   - Used for problems like finding pairs in a sorted array, reversing a string in place, etc.
     ```java
     int left = 0, right = arr.length - 1;
     while (left < right) {
         // Swap elements, move pointers, etc.
         left++;
         right--;
     }
     ```

3. **Depth-First Search (DFS) and Breadth-First Search (BFS)**
   - DFS using recursion or stack:
     ```java
     void dfs(TreeNode node) {
         if (node == null) return;
         dfs(node.left);
         dfs(node.right);
     }
     ```
   - BFS using queue:
     ```java
     Queue<TreeNode> queue = new LinkedList<>();
     queue.offer(root);
     while (!queue.isEmpty()) {
         TreeNode node = queue.poll();
         if (node.left != null) queue.offer(node.left);
         if (node.right != null) queue.offer(node.right);
     }
     ```

### Utility Functions
1. **String Operations**
   - `str.charAt(index);`
   - `str.substring(start, end);`
   - `str.split(delimiter);`
   - `str.equals(otherString);`
   - `StringBuilder sb = new StringBuilder();`
   - `sb.append(value);`

2. **Math Operations**
   - `Math.max(a, b);`
   - `Math.min(a, b);`
   - `Math.abs(value);`
   - `Math.pow(base, exponent);`

3. **Sorting and Searching**
   - `Arrays.sort(arr);`
   - `Collections.sort(list);`
   - `Collections.binarySearch(list, key);`

4. **Stream API**
   - `list.stream().filter(...).collect(Collectors.toList());`
   - `list.stream().map(...).collect(Collectors.toList());`

5. **Custom Comparator**
   - Sorting with custom comparator:
     ```java
     Collections.sort(list, new Comparator<Type>() {
         public int compare(Type t1, Type t2) {
             return t1.property - t2.property;
         }
     });
     ```

### Common Patterns
1. **Sliding Window**
   - Used for problems involving subarrays or substrings.
     ```java
     int left = 0, right = 0;
     while (right < arr.length) {
         // Expand the window
         right++;
         // Shrink the window
         left++;
     }
     ```
   - 1. Fixed Size Sliding Window

      ```java
      // Problem: Find the maximum sum of a subarray of size k.
      public class SlidingWindow {
          public static int maxSum(int[] arr, int k) {
              int n = arr.length;
              if (n < k) {
                  System.out.println("Invalid");
                  return -1;
              }
      
              int maxSum = 0;
              for (int i = 0; i < k; i++) {
                  maxSum += arr[i];
              }
      
              int windowSum = maxSum;
              for (int i = k; i < n; i++) {
                  windowSum += arr[i] - arr[i - k];
                  maxSum = Math.max(maxSum, windowSum);
              }
      
              return maxSum;
          }
      
          public static void main(String[] args) {
              int[] arr = {1, 2, 3, 4, 5, 6, 1, 2, 3};
              int k = 3;
              System.out.println("Maximum sum of subarray of size " + k + " is " + maxSum(arr, k));
          }
      }
      ```
   - 2. Variable Size Sliding Window

      ```java
      // Problem: Find the length of the smallest subarray with a sum greater than or equal to s.
      public class SlidingWindow {
          public static int minSubArrayLen(int s, int[] nums) {
              int n = nums.length;
              int minLength = Integer.MAX_VALUE;
              int sum = 0;
              int left = 0;
      
              for (int right = 0; right < n; right++) {
                  sum += nums[right];
      
                  while (sum >= s) {
                      minLength = Math.min(minLength, right - left + 1);
                      sum -= nums[left++];
                  }
              }
      
              return minLength == Integer.MAX_VALUE ? 0 : minLength;
          }
      
          public static void main(String[] args) {
              int[] nums = {2, 3, 1, 2, 4, 3};
              int s = 7;
              System.out.println("Length of smallest subarray: " + minSubArrayLen(s, nums));
          }
      }

      ```
      

2. **Backtracking**
   - Used for problems like generating permutations, combinations, etc.
     ```java
     void backtrack(List<Integer> list, int[] nums) {
         if (list.size() == nums.length) {
             result.add(new ArrayList<>(list));
             return;
         }
         for (int i = 0; i < nums.length; i++) {
             list.add(nums[i]);
             backtrack(list, nums);
             list.remove(list.size() - 1);
         }
     }
     ```

3. **Dynamic Programming**
   - Often involves filling a DP table:
     ```java
     int[] dp = new int[n + 1];
     dp[0] = 1;
     for (int i = 1; i <= n; i++) {
         dp[i] = dp[i - 1] + dp[i - 2];
     }
     ```

## Dijkstra's algorithm

### 1. Understand the Theory

**Dijkstra's Algorithm** is used to find the shortest path from a source node to all other nodes in a weighted graph. It works on graphs with non-negative weights.

#### Steps:
1. **Initialize**: Set the distance to the source node to 0 and the distance to all other nodes to infinity.
2. **Visit Nodes**: Visit the unvisited node with the smallest known distance.
3. **Update Distances**: For the current node, consider all its unvisited neighbors and calculate their tentative distances through the current node. If the calculated distance of a node is less than the known distance, update the shortest distance.
4. **Mark Visited**: Mark the current node as visited. A visited node will not be checked again.
5. **Repeat**: Repeat steps 2-4 until all nodes have been visited.

### 2. Implementing Dijkstra's Algorithm in Java

Here's a basic implementation of Dijkstra's Algorithm using a priority queue:

```java
import java.util.*;

class Graph {
    private final Map<Integer, List<Node>> nodes = new HashMap<>();

    public void addEdge(int source, int destination, int weight) {
        nodes.putIfAbsent(source, new ArrayList<>());
        nodes.get(source).add(new Node(destination, weight));
    }

    public Map<Integer, Integer> dijkstra(int start) {
        // Priority queue to select the node with the smallest distance
        PriorityQueue<Node> queue = new PriorityQueue<>(Comparator.comparingInt(node -> node.distance));
        queue.add(new Node(start, 0));

        // Map to store the shortest distance from start to each node
        Map<Integer, Integer> distances = new HashMap<>();
        distances.put(start, 0);

        while (!queue.isEmpty()) {
            Node current = queue.poll();

            for (Node neighbor : nodes.getOrDefault(current.vertex, Collections.emptyList())) {
                int newDist = distances.get(current.vertex) + neighbor.distance;

                if (newDist < distances.getOrDefault(neighbor.vertex, Integer.MAX_VALUE)) {
                    distances.put(neighbor.vertex, newDist);
                    queue.add(new Node(neighbor.vertex, newDist));
                }
            }
        }

        return distances;
    }

    static class Node {
        int vertex;
        int distance;

        Node(int vertex, int distance) {
            this.vertex = vertex;
            this.distance = distance;
        }
    }

    public static void main(String[] args) {
        Graph graph = new Graph();
        graph.addEdge(0, 1, 4);
        graph.addEdge(0, 2, 1);
        graph.addEdge(2, 1, 2);
        graph.addEdge(1, 3, 1);
        graph.addEdge(2, 3, 5);

        Map<Integer, Integer> distances = graph.dijkstra(0);
        for (Map.Entry<Integer, Integer> entry : distances.entrySet()) {
            System.out.println("Distance from 0 to " + entry.getKey() + " is " + entry.getValue());
        }
    }
}
```

## Two pointers 
- is a common and powerful technique often used to solve problems involving arrays or linked lists. This method uses two pointers to traverse the data structure and find specific values or pairs that meet certain conditions.

### Example 1: Finding a Pair with a Given Sum in a Sorted Array

Given a sorted array and a target sum, find a pair of numbers that add up to the target sum.

```java
public class TwoPointersExample {
    public static int[] findPairWithSum(int[] arr, int targetSum) {
        int left = 0;
        int right = arr.length - 1;

        while (left < right) {
            int sum = arr[left] + arr[right];
            if (sum == targetSum) {
                return new int[]{arr[left], arr[right]};
            } else if (sum < targetSum) {
                left++;
            } else {
                right--;
            }
        }
        return new int[]{-1, -1}; // Return -1, -1 if no pair is found
    }

    public static void main(String[] args) {
        int[] arr = {1, 2, 3, 4, 6};
        int targetSum = 6;
        int[] result = findPairWithSum(arr, targetSum);
        System.out.println("Pair: (" + result[0] + ", " + result[1] + ")");
    }
}
```

### Example 2: Removing Duplicates from a Sorted Array

Given a sorted array, remove the duplicates in-place such that each element appears only once and return the new length.

```java
public class TwoPointersExample {
    public static int removeDuplicates(int[] nums) {
        if (nums.length == 0) return 0;

        int i = 0;
        for (int j = 1; j < nums.length; j++) {
            if (nums[j] != nums[i]) {
                i++;
                nums[i] = nums[j];
            }
        }
        return i + 1;
    }

    public static void main(String[] args) {
        int[] nums = {0, 0, 1, 1, 2, 2, 3, 3, 4};
        int length = removeDuplicates(nums);
        System.out.println("New length: " + length);
        for (int i = 0; i < length; i++) {
            System.out.print(nums[i] + " ");
        }
    }
}
```

### Example 3: Moving Zeros to the End

Given an array of integers, move all zeros to the end while maintaining the relative order of the non-zero elements.

```java
public class TwoPointersExample {
    public static void moveZeroes(int[] nums) {
        int lastNonZeroFoundAt = 0;

        // Move all non-zero elements to the front
        for (int i = 0; i < nums.length; i++) {
            if (nums[i] != 0) {
                nums[lastNonZeroFoundAt++] = nums[i];
            }
        }

        // Fill the remaining positions with zeros
        for (int i = lastNonZeroFoundAt; i < nums.length; i++) {
            nums[i] = 0;
        }
    }

    public static void main(String[] args) {
        int[] nums = {0, 1, 0, 3, 12};
        moveZeroes(nums);
        for (int num : nums) {
            System.out.print(num + " ");
        }
    }
}
```

### Key Points to Remember

1. **Initialization**: Initialize two pointers to start at different positions, typically the beginning and end of the array or list.
2. **Traversal**: Move the pointers based on specific conditions, ensuring that you don't miss any potential solutions.
3. **Condition Checking**: Ensure that your condition checks (like sum, comparison, etc.) are correctly implemented to guide the movement of pointers.
4. **Edge Cases**: Handle edge cases such as empty arrays, arrays with one element, etc.
