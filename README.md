# java
Sure! Here’s a comprehensive list of operations you can perform on an array in Java, categorized for clarity:

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

These operations cover a wide range of manipulations you might need to perform on arrays in Java. By mastering these, you’ll be well-equipped to handle array-related tasks efficiently.
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

These methods provide a wide range of functionalities to handle and manipulate arrays efficiently in Java.
