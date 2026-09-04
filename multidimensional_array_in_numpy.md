# Multidimensional Arrays in NumPy

A multidimensional array is an array that contains data organized across two or more dimensions.

In NumPy, multidimensional arrays are represented using the `ndarray` object.

You can think of dimensions as different levels of organization:

- 0D → Single value
- 1D → A list of values
- 2D → Rows and columns, like a table or matrix
- 3D → Multiple 2D tables stacked together
- 4D → Multiple 3D arrays grouped together
- Higher dimensions → Additional levels of organization

NumPy allows us to efficiently create, access, modify, calculate, reshape, and manipulate these arrays.

---

## 1. Understanding Dimensions

### 0-Dimensional Array

A 0D array contains only one value.

    import numpy as np

    arr = np.array(10)

    print(arr)
    print(arr.ndim)

Output:

    10
    0

Here:

    arr.ndim

returns `0`, because the array has no dimension.

A 0D array is also called a scalar array.

---

# 2. One-Dimensional Array

A 1D array contains values arranged in a single direction.

    arr = np.array([10, 20, 30, 40, 50])

    print(arr)
    print(arr.ndim)
    print(arr.shape)

Output:

    [10 20 30 40 50]
    1
    (5,)

There are 5 elements, so its shape is:

    (5,)

You can think of it as:

    10  20  30  40  50
    ↑
    one dimension

Index positions:

    Index:   0   1   2   3   4
    Value:  10  20  30  40  50

---

# 3. Two-Dimensional Array

A 2D array contains rows and columns.

For example:

    arr = np.array([
        [10, 20, 30],
        [40, 50, 60],
        [70, 80, 90]
    ])

Visually:

             Column
              0   1   2
            ┌────────────
    Row 0   │ 10  20  30
    Row 1   │ 40  50  60
    Row 2   │ 70  80  90

This array has:

    3 rows
    3 columns

Therefore:

    print(arr.ndim)
    print(arr.shape)
    print(arr.size)

Output:

    2
    (3, 3)
    9

### Understanding Shape

The shape:

    (3, 3)

means:

    3 rows
    3 columns

The general form of a 2D array shape is:

    (number_of_rows, number_of_columns)

For example:

    (2, 4)

means:

    2 rows
    4 columns

Example:

    arr = np.array([
        [1, 2, 3, 4],
        [5, 6, 7, 8]
    ])

Shape:

    (2, 4)

Visualization:

    1  2  3  4
    5  6  7  8

---

# 4. Accessing Elements in a 2D Array

To access an element from a 2D array, use:

    array[row, column]

Example:

    arr = np.array([
        [10, 20, 30],
        [40, 50, 60],
        [70, 80, 90]
    ])

    print(arr[0, 0])

Output:

    10

Here:

    arr[0, 0]

means:

    row = 0
    column = 0

Python uses zero-based indexing.

So:

    arr[0, 1] → 20
    arr[0, 2] → 30
    arr[1, 0] → 40
    arr[1, 1] → 50
    arr[2, 2] → 90

---

# 5. Row Indexing

You can access an entire row using:

    array[row_number]

Example:

    arr = np.array([
        [10, 20, 30],
        [40, 50, 60],
        [70, 80, 90]
    ])

    print(arr[1])

Output:

    [40 50 60]

Because row index `1` is:

    [40, 50, 60]

Another example:

    print(arr[0])

Output:

    [10 20 30]

---

# 6. Column Access

To access a complete column, use:

    arr[:, column_number]

Example:

    arr = np.array([
        [10, 20, 30],
        [40, 50, 60],
        [70, 80, 90]
    ])

    print(arr[:, 1])

Output:

    [20 50 80]

Explanation:

    :  → select all rows
    1  → select column 1

So:

    arr[:, 1]

means:

    "Take every row, but only column 1."

---

# 7. 2D Array Slicing

You can slice rows and columns simultaneously.

Syntax:

    array[row_start:row_end, column_start:column_end]

Example:

    arr = np.array([
        [10, 20, 30, 40],
        [50, 60, 70, 80],
        [90, 100, 110, 120]
    ])

    print(arr[0:2, 1:3])

Output:

    [[20 30]
     [60 70]]

Explanation:

    0:2 → rows 0 and 1
    1:3 → columns 1 and 2

So NumPy selects:

    20  30
    60  70

---

# 8. Negative Indexing in Multidimensional Arrays

NumPy supports negative indexing.

Example:

    arr = np.array([
        [10, 20, 30],
        [40, 50, 60],
        [70, 80, 90]
    ])

    print(arr[-1])

Output:

    [70 80 90]

`-1` means the last row.

To access the last element:

    print(arr[-1, -1])

Output:

    90

Here:

    -1 → last row
    -1 → last column

---

# 9. Three-Dimensional Arrays

A 3D array is an array containing multiple 2D arrays.

For example:

    arr = np.array([
        [
            [1, 2, 3],
            [4, 5, 6]
        ],
        [
            [7, 8, 9],
            [10, 11, 12]
        ]
    ])

You can visualize this as two 2D arrays:

    Array 0:

        1   2   3
        4   5   6

    Array 1:

        7   8   9
        10  11  12

Check its dimensions:

    print(arr.ndim)

Output:

    3

Check its shape:

    print(arr.shape)

Output:

    (2, 2, 3)

This means:

    2 → number of 2D arrays
    2 → number of rows in each 2D array
    3 → number of columns in each row

Therefore:

    (2, 2, 3)

can be understood as:

    2 blocks
    × 2 rows
    × 3 columns

Total elements:

    2 × 2 × 3 = 12

Therefore:

    print(arr.size)

Output:

    12

---

# 10. Accessing Elements in a 3D Array

For a 3D array, indexing follows:

    array[block, row, column]

Example:

    arr = np.array([
        [
            [1, 2, 3],
            [4, 5, 6]
        ],
        [
            [7, 8, 9],
            [10, 11, 12]
        ]
    ])

To access `5`:

    print(arr[0, 1, 1])

Explanation:

    0 → first block
    1 → second row
    1 → second column

Output:

    5

Another example:

    print(arr[1, 0, 2])

Output:

    9

Explanation:

    1 → second block
    0 → first row
    2 → third column

---

# 11. Accessing a Complete 2D Array from a 3D Array

You can select one complete block.

    print(arr[0])

Output:

    [[1 2 3]
     [4 5 6]]

And:

    print(arr[1])

Output:

    [[7 8 9]
     [10 11 12]]

Therefore:

    arr[0]

means:

    "Give me the first 2D array."

---

# 12. Accessing a Row from a 3D Array

Example:

    print(arr[0, 1])

Output:

    [4 5 6]

Explanation:

    0 → first block
    1 → second row

---

# 13. Accessing a Column from a 3D Array

Example:

    print(arr[:, :, 1])

Output:

    [[2 5]
     [8 11]]

Explanation:

    : → all blocks
    : → all rows
    1 → column 1

This selects the second column from every row in every block.

---

# 14. Four-Dimensional Arrays

NumPy can also create arrays with four or more dimensions.

Example:

    arr = np.zeros((2, 3, 4, 5))

    print(arr.ndim)
    print(arr.shape)
    print(arr.size)

Output:

    4
    (2, 3, 4, 5)
    120

The shape:

    (2, 3, 4, 5)

means the array contains:

    2 groups
    3 blocks per group
    4 rows per block
    5 columns per row

Total elements:

    2 × 3 × 4 × 5 = 120

Higher-dimensional arrays are useful for structured scientific and machine-learning data.

---

# 15. Dimension vs Shape vs Size

These three concepts are extremely important.

### ndim

`ndim` tells you how many dimensions the array has.

    arr = np.zeros((2, 3, 4))

    print(arr.ndim)

Output:

    3

---

### shape

`shape` tells you the size of the array along each dimension.

    print(arr.shape)

Output:

    (2, 3, 4)

---

### size

`size` tells you the total number of elements.

    print(arr.size)

Output:

    24

Because:

    2 × 3 × 4 = 24

---

# 16. Easy Way to Remember

Suppose:

    arr.shape = (2, 3, 4)

Think:

    2 × 3 × 4

The number of values is:

    2 × 3 × 4 = 24

And:

    arr.ndim = 3

So:

    ndim  → How many dimensions?
    shape → How big is each dimension?
    size  → How many total elements?

---

# 17. Creating Multidimensional Arrays with zeros()

You can create arrays filled with zeros.

Example:

    arr = np.zeros((3, 4))

Output:

    [[0. 0. 0. 0.]
     [0. 0. 0. 0.]
     [0. 0. 0. 0.]]

This is a 2D array with:

    3 rows
    4 columns

For a 3D array:

    arr = np.zeros((2, 3, 4))

This creates:

    2 blocks
    3 rows
    4 columns

---

# 18. Creating Multidimensional Arrays with ones()

Example:

    arr = np.ones((2, 3))

Output:

    [[1. 1. 1.]
     [1. 1. 1.]]

For 3D:

    arr = np.ones((2, 3, 4))

---

# 19. Creating Multidimensional Arrays with full()

`np.full()` creates an array filled with a specific value.

Example:

    arr = np.full((3, 3), 7)

Output:

    [[7 7 7]
     [7 7 7]
     [7 7 7]]

The first argument specifies the shape:

    (3, 3)

The second argument specifies the value:

    7

---

# 20. Reshaping Multidimensional Arrays

`reshape()` changes the structure of an array without changing the number of elements.

Example:

    arr = np.array([1, 2, 3, 4, 5, 6])

    new_arr = arr.reshape(2, 3)

    print(new_arr)

Output:

    [[1 2 3]
     [4 5 6]]

Original:

    [1 2 3 4 5 6]

New:

    1  2  3
    4  5  6

Both contain 6 elements.

Important rule:

    Old total elements = New total elements

For example:

    6 elements → reshape(2, 3)

because:

    2 × 3 = 6

But this is invalid:

    arr.reshape(4, 2)

because:

    4 × 2 = 8

and the original array contains only 6 elements.

---

# 21. Reshaping into 3D

Example:

    arr = np.arange(24)

    new_arr = arr.reshape(2, 3, 4)

    print(new_arr)

The original array has 24 elements.

The new shape contains:

    2 × 3 × 4 = 24

Therefore, the reshape is valid.

---

# 22. Using -1 in reshape()

NumPy can automatically calculate one dimension if you use `-1`.

Example:

    arr = np.arange(12)

    new_arr = arr.reshape(3, -1)

    print(new_arr)

Output:

    [[ 0  1  2  3]
     [ 4  5  6  7]
     [ 8  9 10 11]]

NumPy calculates the missing dimension.

There are 12 elements.

We specify:

    3 rows

So NumPy calculates:

    12 / 3 = 4

Therefore:

    reshape(3, -1)

becomes:

    reshape(3, 4)

---

# 23. Flattening a Multidimensional Array

Flattening converts a multidimensional array into a 1D array.

Example:

    arr = np.array([
        [1, 2, 3],
        [4, 5, 6]
    ])

    flat = arr.flatten()

    print(flat)

Output:

    [1 2 3 4 5 6]

The original:

    [[1 2 3]
     [4 5 6]]

becomes:

    [1 2 3 4 5 6]

---

# 24. Transpose of a Multidimensional Array

Transpose changes rows into columns and columns into rows.

Example:

    arr = np.array([
        [1, 2, 3],
        [4, 5, 6]
    ])

    print(arr.T)

Output:

    [[1 4]
     [2 5]
     [3 6]]

Original shape:

    (2, 3)

After transpose:

    (3, 2)

So:

    rows become columns
    columns become rows

You can also use:

    np.transpose(arr)

---

# 25. Axis in Multidimensional Arrays

`axis` is one of the most important concepts when working with multidimensional NumPy arrays.

Consider:

    arr = np.array([
        [10, 20, 30],
        [40, 50, 60],
        [70, 80, 90]
    ])

The array has shape:

    (3, 3)

### axis=0

`axis=0` works down the rows.

For example:

    print(np.sum(arr, axis=0))

Output:

    [120 150 180]

Calculation:

    10 + 40 + 70 = 120
    20 + 50 + 80 = 150
    30 + 60 + 90 = 180

So `axis=0` produces a result for each column.

---

### axis=1

`axis=1` works across the columns of each row.

    print(np.sum(arr, axis=1))

Output:

    [ 60 150 240]

Calculation:

    10 + 20 + 30 = 60
    40 + 50 + 60 = 150
    70 + 80 + 90 = 240

So `axis=1` produces a result for each row.

### Easy Memory Trick

For a 2D array:

    axis=0 → operate vertically → result for each column

    axis=1 → operate horizontally → result for each row

---

# 26. Mean with Axis

Example:

    arr = np.array([
        [10, 20, 30],
        [40, 50, 60],
        [70, 80, 90]
    ])

Column averages:

    print(np.mean(arr, axis=0))

Output:

    [40. 50. 60.]

Row averages:

    print(np.mean(arr, axis=1))

Output:

    [20. 50. 80.]

---

# 27. Multidimensional Array Comparison

You can compare every element in a multidimensional array.

Example:

    arr = np.array([
        [10, 20, 30],
        [40, 50, 60]
    ])

    print(arr > 30)

Output:

    [[False False False]
     [ True  True  True]]

NumPy performs the comparison element by element.

---

# 28. Boolean Filtering in Multidimensional Arrays

Example:

    arr = np.array([
        [10, 20, 30],
        [40, 50, 60]
    ])

    result = arr[arr > 30]

    print(result)

Output:

    [40 50 60]

This extracts all values greater than 30.

Notice that the result becomes a 1D array.

---

# 29. Using np.where() with Multidimensional Arrays

`np.where()` can find the positions where a condition is true.

Example:

    arr = np.array([
        [10, 20, 30],
        [40, 50, 60]
    ])

    positions = np.where(arr > 30)

    print(positions)

The result contains the row and column positions of values greater than 30.

For example, the values:

    40
    50
    60

are located at:

    (1, 0)
    (1, 1)
    (1, 2)

---

# 30. Adding Two Multidimensional Arrays

NumPy allows element-by-element operations.

Example:

    a = np.array([
        [1, 2],
        [3, 4]
    ])

    b = np.array([
        [5, 6],
        [7, 8]
    ])

    print(a + b)

Output:

    [[ 6  8]
     [10 12]]

Calculation:

    1 + 5 = 6
    2 + 6 = 8
    3 + 7 = 10
    4 + 8 = 12

The arrays must have compatible shapes for element-wise operations.

---

# 31. Multiplication of Multidimensional Arrays

Element-wise multiplication:

    a = np.array([
        [1, 2],
        [3, 4]
    ])

    b = np.array([
        [5, 6],
        [7, 8]
    ])

    print(a * b)

Output:

    [[ 5 12]
     [21 32]]

This means:

    1 × 5 = 5
    2 × 6 = 12
    3 × 7 = 21
    4 × 8 = 32

Important:

    *

performs element-wise multiplication.

It does NOT mean matrix multiplication.

---

# 32. Matrix Multiplication

For matrix multiplication, use:

    @

Example:

    a = np.array([
        [1, 2],
        [3, 4]
    ])

    b = np.array([
        [5, 6],
        [7, 8]
    ])

    result = a @ b

    print(result)

Output:

    [[19 22]
     [43 50]]

The calculation for the first element is:

    (1 × 5) + (2 × 7)
    = 5 + 14
    = 19

So:

    a * b

means element-wise multiplication.

While:

    a @ b

means matrix multiplication.

---

# 33. Broadcasting with Multidimensional Arrays

Broadcasting allows NumPy to perform operations between arrays with compatible shapes.

Example:

    arr = np.array([
        [10, 20, 30],
        [40, 50, 60]
    ])

    result = arr + 10

    print(result)

Output:

    [[20 30 40]
     [50 60 70]]

NumPy adds `10` to every element.

Conceptually:

    [[10, 20, 30],       [[10, 10, 10],
     [40, 50, 60]]   +    [10, 10, 10]]

becomes:

    [[20, 30, 40],
     [50, 60, 70]]

The single value `10` is broadcast across the entire array.

---

# 34. Broadcasting with a 1D Array

Example:

    arr = np.array([
        [10, 20, 30],
        [40, 50, 60]
    ])

    values = np.array([1, 2, 3])

    result = arr + values

    print(result)

Output:

    [[11 22 33]
     [41 52 63]]

NumPy effectively applies:

    [1, 2, 3]

to every row.

---

# 35. Practical Example: Student Marks

Multidimensional arrays are very useful for storing structured data.

Suppose we have marks for 3 students in 4 subjects:

    marks = np.array([
        [80, 75, 90, 85],
        [70, 88, 92, 78],
        [95, 90, 85, 88]
    ])

Shape:

    (3, 4)

Meaning:

    3 students
    4 subjects

The rows represent students.

The columns represent subjects.

    Student 1 → [80, 75, 90, 85]
    Student 2 → [70, 88, 92, 78]
    Student 3 → [95, 90, 85, 88]

---

# 36. Calculate Each Student's Average

Use:

    average = np.mean(marks, axis=1)

    print(average)

Output:

    [82.5 82.  89.5]

Why `axis=1`?

Because we want to calculate across the subjects for each student.

---

# 37. Calculate Average for Each Subject

Use:

    subject_average = np.mean(marks, axis=0)

    print(subject_average)

Output:

    [81.66666667 84.33333333 89.         83.66666667]

Why `axis=0`?

Because we want to calculate down the students for each subject.

---

# 38. Multidimensional Arrays in Machine Learning

Multidimensional arrays are extremely important in machine learning and deep learning.

For example, an image can be represented as an array.

A grayscale image can commonly be represented as:

    (height, width)

For example:

    (28, 28)

means:

    28 pixels high
    28 pixels wide

A color image can commonly be represented as:

    (height, width, channels)

For example:

    (224, 224, 3)

means:

    224 pixels high
    224 pixels wide
    3 color channels

The three channels commonly represent:

    Red
    Green
    Blue

---

# 39. Image Example

A small grayscale image could be represented as:

    image = np.array([
        [0, 100, 255],
        [50, 150, 200],
        [255, 80, 20]
    ])

Each number represents a pixel intensity.

For a typical 8-bit grayscale image:

    0   → black
    255 → white

Values between them represent different shades of gray.

---

# 40. Batch of Images

If we have many grayscale images, we can have another dimension.

For example:

    (32, 28, 28)

can represent:

    32 images
    28 pixels high
    28 pixels wide

This is a 3D array.

For color images:

    (32, 224, 224, 3)

can represent:

    32 images
    224 height
    224 width
    3 color channels

This is a 4D array.

---

# 41. Important Multidimensional Array Terms

### Dimension

The number of axes in an array.

    arr.ndim

Example:

    shape = (2, 3, 4)

Then:

    ndim = 3

---

### Axis

An individual direction or dimension of an array.

For:

    shape = (2, 3, 4)

there are three axes:

    axis 0 → size 2
    axis 1 → size 3
    axis 2 → size 4

---

### Shape

The size along every axis.

    arr.shape

Example:

    (2, 3, 4)

---

### Size

Total number of elements.

    arr.size

For:

    (2, 3, 4)

size is:

    2 × 3 × 4 = 24

---

# 42. Summary Table

| Array | Example Shape | Dimensions | Meaning |
|---|---|---:|---|
| Scalar | `()` | 0D | One value |
| 1D | `(5,)` | 1D | 5 values |
| 2D | `(3, 4)` | 2D | 3 rows × 4 columns |
| 3D | `(2, 3, 4)` | 3D | 2 blocks × 3 rows × 4 columns |
| 4D | `(2, 3, 4, 5)` | 4D | 2 × 3 × 4 × 5 |

---

# 43. Most Important Rules

Remember these rules when working with multidimensional arrays:

1. `ndim` tells you the number of dimensions.

2. `shape` tells you the size of each dimension.

3. `size` tells you the total number of elements.

4. A 2D array uses:

       array[row, column]

5. A 3D array uses:

       array[block, row, column]

6. A 4D array has one additional level of indexing.

7. `axis=0` generally means operating down the first dimension.

8. `axis=1` generally means operating across the next dimension.

9. `reshape()` changes the structure but preserves the number of elements.

10. `flatten()` converts a multidimensional array into 1D.

11. `*` performs element-wise multiplication.

12. `@` performs matrix multiplication.

13. Broadcasting allows compatible arrays of different shapes to participate in operations.

---

# 44. Official NumPy References

NumPy Documentation:
https://numpy.org/doc/

NumPy User Guide:
https://numpy.org/doc/stable/user/

NumPy Array Objects:
https://numpy.org/doc/stable/reference/arrays.html

NumPy `ndarray`:
https://numpy.org/doc/stable/reference/generated/numpy.ndarray.html

NumPy `reshape()`:
https://numpy.org/doc/stable/reference/generated/numpy.reshape.html

NumPy indexing:
https://numpy.org/doc/stable/user/basics.indexing.html

NumPy broadcasting:
https://numpy.org/doc/stable/user/basics.broadcasting.html

NumPy linear algebra:
https://numpy.org/doc/stable/reference/routines.linalg.html

These official NumPy references provide the authoritative definitions and behavior of multidimensional arrays, indexing, reshaping, broadcasting, and array operations.