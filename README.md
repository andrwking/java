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
