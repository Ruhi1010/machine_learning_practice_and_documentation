# NumPy: End-to-End Documentation

## 📌 What is NumPy?

NumPy, short for Numerical Python, is a fundamental Python library for numerical computing.

It provides:

- Multidimensional arrays
- Fast mathematical operations
- Array manipulation
- Statistical functions
- Linear algebra
- Random number generation
- Broadcasting
- Sorting and searching
- Fourier transforms
- Basic support for numerical scientific computing

NumPy is widely used in data science, machine learning, scientific computing, engineering, and Python-based numerical applications.

---

# 📦 Installation

NumPy can be installed using pip:

    pip install numpy

To verify the installation:

    python -c "import numpy; print(numpy.__version__)"

Inside Python or Jupyter Notebook:

    import numpy as np

    print(np.__version__)

The common convention is to import NumPy using the alias `np`:

    import numpy as np

---

# 🚀 Getting Started

The first step is importing NumPy:

    import numpy as np

A simple NumPy array can be created using:

    arr = np.array([1, 2, 3, 4, 5])

    print(arr)

Output:

    [1 2 3 4 5]

Unlike a normal Python list, a NumPy array is designed specifically for numerical operations and supports efficient vectorized calculations.

---

# 🧱 NumPy Arrays

The central object in NumPy is the `ndarray`.

`ndarray` means N-dimensional array.

An array can have:

- 0 dimensions
- 1 dimension
- 2 dimensions
- 3 dimensions
- More dimensions

---

# 1️⃣ One-Dimensional Array

A one-dimensional array is similar to a list:

    arr = np.array([10, 20, 30, 40, 50])

    print(arr)

Output:

    [10 20 30 40 50]

---

# 2️⃣ Two-Dimensional Array

A two-dimensional array can be represented as rows and columns:

    arr = np.array([
        [1, 2, 3],
        [4, 5, 6]
    ])

    print(arr)

Output:

    [[1 2 3]
     [4 5 6]]

This can be viewed as a matrix with:

- 2 rows
- 3 columns

---

# 3️⃣ Three-Dimensional Array

A three-dimensional array contains multiple two-dimensional arrays:

    arr = np.array([
        [
            [1, 2],
            [3, 4]
        ],
        [
            [5, 6],
            [7, 8]
        ]
    ])

    print(arr)

A 3D array can be useful when representing data such as images, videos, or batches of matrices.

---

# 📏 Dimensions

The `ndim` attribute tells us how many dimensions an array has.

    arr = np.array([
        [1, 2, 3],
        [4, 5, 6]
    ])

    print(arr.ndim)

Output:

    2

---

# 📐 Shape

The `shape` attribute tells us the size of each dimension.

    arr = np.array([
        [1, 2, 3],
        [4, 5, 6]
    ])

    print(arr.shape)

Output:

    (2, 3)

This means:

    2 rows
    3 columns

---

# 🔢 Size

The `size` attribute tells us the total number of elements.

    arr = np.array([
        [1, 2, 3],
        [4, 5, 6]
    ])

    print(arr.size)

Output:

    6

---

# 🧮 Data Type

The `dtype` attribute tells us the data type of the elements.

    arr = np.array([1, 2, 3, 4])

    print(arr.dtype)

For example, NumPy may report:

    int64

The exact integer size can depend on the platform.

---

# 🔄 Changing Data Type

The `astype()` method can convert an array to another data type.

    arr = np.array([1, 2, 3, 4])

    float_arr = arr.astype(float)

    print(float_arr)

Output:

    [1. 2. 3. 4.]

Another example:

    arr = np.array([1.5, 2.5, 3.5])

    int_arr = arr.astype(int)

    print(int_arr)

Output:

    [1 2 3]

Be careful when converting between types because information can be lost.

---

# 🏗️ Creating Arrays

NumPy provides many functions for creating arrays.

---

# np.array()

Creates an array from Python sequences such as lists or tuples.

    arr = np.array([1, 2, 3, 4])

---

# np.zeros()

Creates an array filled with zeros.

    arr = np.zeros(5)

Output:

    [0. 0. 0. 0. 0.]

Two-dimensional example:

    arr = np.zeros((2, 3))

Output:

    [[0. 0. 0.]
     [0. 0. 0.]]

---

# np.ones()

Creates an array filled with ones.

    arr = np.ones(5)

Output:

    [1. 1. 1. 1. 1.]

Two-dimensional example:

    arr = np.ones((2, 3))

---

# np.full()

Creates an array filled with a specified value.

    arr = np.full((2, 3), 7)

Output:

    [[7 7 7]
     [7 7 7]]

---

# np.empty()

Creates an array without initializing its entries to a particular value.

    arr = np.empty(5)

The values should not be assumed to be zero.

---

# np.arange()

Creates evenly spaced values within a specified interval.

    arr = np.arange(0, 10)

Output:

    [0 1 2 3 4 5 6 7 8 9]

With a step:

    arr = np.arange(0, 10, 2)

Output:

    [0 2 4 6 8]

The stop value is generally excluded.

---

# np.linspace()

Creates a specified number of evenly spaced values over an interval.

    arr = np.linspace(0, 10, 5)

Output:

    [ 0.   2.5  5.   7.5 10. ]

Unlike `np.arange()`, `linspace()` is especially useful when you want a specific number of values.

---

# 🔢 Identity Matrix

NumPy can create an identity matrix using:

    arr = np.eye(3)

Output:

    [[1. 0. 0.]
     [0. 1. 0.]
     [0. 0. 1.]]

---

# 🎲 Random Arrays

NumPy provides random number generation through `np.random`.

Example:

    arr = np.random.rand(5)

This generates five random floating-point values in the interval [0, 1).

For a two-dimensional array:

    arr = np.random.rand(2, 3)

---

# Random Integers

    arr = np.random.randint(1, 10, size=5)

This generates five random integers from 1 up to, but not including, 10.

---

# Random Normal Distribution

    arr = np.random.randn(5)

This generates values from a standard normal distribution.

For newer code, NumPy recommends using the modern random Generator API for new random-number-generation code:

    rng = np.random.default_rng()

    arr = rng.integers(1, 10, size=5)

---

# 🔍 Indexing

NumPy arrays use zero-based indexing.

Example:

    arr = np.array([10, 20, 30, 40, 50])

    print(arr[0])

Output:

    10

    print(arr[2])

Output:

    30

---

# 🔙 Negative Indexing

Negative indexes access elements from the end.

    arr = np.array([10, 20, 30, 40, 50])

    print(arr[-1])

Output:

    50

    print(arr[-2])

Output:

    40

---

# ✂️ Slicing

Slicing allows us to select a portion of an array.

    arr = np.array([10, 20, 30, 40, 50])

    print(arr[1:4])

Output:

    [20 30 40]

The general syntax is:

    array[start:stop:step]

---

# Slicing With Step

    arr = np.array([0, 1, 2, 3, 4, 5, 6])

    print(arr[::2])

Output:

    [0 2 4 6]

---

# 🔲 Indexing 2D Arrays

Consider:

    arr = np.array([
        [1, 2, 3],
        [4, 5, 6],
        [7, 8, 9]
    ])

Access the first row:

    print(arr[0])

Output:

    [1 2 3]

Access the first row and second column:

    print(arr[0, 1])

Output:

    2

Access the third row and first column:

    print(arr[2, 0])

Output:

    7

---

# ✂️ 2D Slicing

Select the first two rows:

    print(arr[:2])

Select the first two columns:

    print(arr[:, :2])

Select rows 1 and 2 and columns 2 and 3:

    print(arr[1:3, 1:3])

---

# 🧠 Boolean Indexing

Boolean indexing allows us to select elements based on conditions.

    arr = np.array([10, 20, 30, 40, 50])

    print(arr > 25)

Output:

    [False False  True  True  True]

We can use the condition directly:

    print(arr[arr > 25])

Output:

    [30 40 50]

---

# 🔎 np.where()

`np.where()` can be used to find positions or select values based on conditions.

    arr = np.array([10, 20, 30, 40, 50])

    result = np.where(arr > 25)

    print(result)

This returns the indexes where the condition is true.

It can also select between two values:

    result = np.where(arr > 25, 1, 0)

Output:

    [0 0 1 1 1]

---

# ➕ Arithmetic Operations

NumPy supports element-wise arithmetic operations.

    a = np.array([1, 2, 3])
    b = np.array([4, 5, 6])

Addition:

    print(a + b)

Output:

    [5 7 9]

Subtraction:

    print(a - b)

Output:

    [-3 -3 -3]

Multiplication:

    print(a * b)

Output:

    [ 4 10 18]

Division:

    print(a / b)

Output:

    [0.25 0.4  0.5 ]

---

# ⚡ Vectorization

One of NumPy's most important features is vectorized computation.

Instead of writing:

    result = []

    for x in arr:
        result.append(x * 2)

NumPy allows:

    result = arr * 2

This performs the operation efficiently on the entire array.

---

# 🧮 Mathematical Functions

NumPy provides many mathematical functions.

Example:

    arr = np.array([1, 4, 9, 16])

Square root:

    print(np.sqrt(arr))

Output:

    [1. 2. 3. 4.]

Power:

    print(np.power(arr, 2))

Exponential:

    print(np.exp(arr))

Logarithm:

    print(np.log(arr))

Absolute value:

    print(np.abs(arr))

---

# 📊 Aggregation Functions

NumPy provides functions for calculating statistics and summaries.

Example:

    arr = np.array([10, 20, 30, 40, 50])

Sum:

    print(np.sum(arr))

Output:

    150

Mean:

    print(np.mean(arr))

Output:

    30.0

Minimum:

    print(np.min(arr))

Output:

    10

Maximum:

    print(np.max(arr))

Output:

    50

---

# 📈 Median

    arr = np.array([10, 20, 30, 40, 50])

    print(np.median(arr))

Output:

    30.0

---

# 📉 Standard Deviation

    arr = np.array([10, 20, 30, 40, 50])

    print(np.std(arr))

Standard deviation measures how spread out the values are around the mean.

---

# 📊 Variance

    print(np.var(arr))

Variance is related to the square of the standard deviation.

---

# 🔢 Percentiles

    arr = np.array([10, 20, 30, 40, 50])

    print(np.percentile(arr, 50))

The 50th percentile corresponds to the median.

---

# 🧭 Axis

The `axis` parameter is extremely important when working with multidimensional arrays.

Consider:

    arr = np.array([
        [1, 2, 3],
        [4, 5, 6]
    ])

Sum of all elements:

    print(np.sum(arr))

Sum along rows:

    print(np.sum(arr, axis=1))

Output:

    [ 6 15]

Sum along columns:

    print(np.sum(arr, axis=0))

Output:

    [5 7 9]

A useful way to remember this is:

- `axis=0` works down the rows and produces column-wise results.
- `axis=1` works across columns and produces row-wise results.

---

# 🔄 Reshaping Arrays

The `reshape()` method changes the shape without changing the elements.

Example:

    arr = np.array([1, 2, 3, 4, 5, 6])

    new_arr = arr.reshape(2, 3)

Output:

    [[1 2 3]
     [4 5 6]]

The total number of elements must remain the same.

For example:

    2 × 3 = 6

---

# 🧩 Automatic Reshaping

NumPy can infer one dimension using `-1`.

    arr = np.arange(12)

    new_arr = arr.reshape(3, -1)

The remaining dimension is calculated automatically.

---

# 🔄 Flattening an Array

Flattening converts a multidimensional array into one dimension.

    arr = np.array([
        [1, 2, 3],
        [4, 5, 6]
    ])

    result = arr.flatten()

Output:

    [1 2 3 4 5 6]

---

# 🔄 ravel()

Another option is:

    result = arr.ravel()

`ravel()` often returns a view when possible, while `flatten()` returns a copy.

This difference can matter when modifying the resulting array.

---

# 🔀 Transpose

Transpose changes rows into columns and columns into rows.

    arr = np.array([
        [1, 2, 3],
        [4, 5, 6]
    ])

    print(arr.T)

Output:

    [[1 4]
     [2 5]
     [3 6]]

---

# 🔗 Concatenation

NumPy can combine arrays using `np.concatenate()`.

    a = np.array([1, 2, 3])
    b = np.array([4, 5, 6])

    result = np.concatenate((a, b))

Output:

    [1 2 3 4 5 6]

For two-dimensional arrays, the axis determines how they are joined.

---

# 📚 Stack

NumPy provides several stacking functions.

## vstack()

Vertical stacking:

    a = np.array([1, 2, 3])
    b = np.array([4, 5, 6])

    result = np.vstack((a, b))

Output:

    [[1 2 3]
     [4 5 6]]

## hstack()

Horizontal stacking:

    result = np.hstack((a, b))

Output:

    [1 2 3 4 5 6]

---

# ✂️ Splitting Arrays

NumPy provides functions for splitting arrays.

    arr = np.array([1, 2, 3, 4, 5, 6])

    result = np.split(arr, 3)

This splits the array into three equal sections.

---

# 🔀 Sorting

NumPy provides sorting functionality.

    arr = np.array([5, 2, 8, 1, 3])

    print(np.sort(arr))

Output:

    [1 2 3 5 8]

The `sort()` method can also be used:

    arr.sort()

---

# 🔎 Searching

`np.where()` can be used to locate elements satisfying conditions.

    arr = np.array([10, 20, 30, 40, 50])

    indexes = np.where(arr == 30)

    print(indexes)

---

# 🔢 Counting Non-Zero Elements

Use:

    arr = np.array([0, 1, 0, 2, 3, 0])

    print(np.count_nonzero(arr))

Output:

    3

---

# 📐 Linear Algebra

NumPy provides a linear algebra module:

    np.linalg

It includes functions for:

- Matrix multiplication
- Determinants
- Inverse matrices
- Eigenvalues
- Eigenvectors
- Solving linear equations
- Matrix norms

---

# ✖️ Matrix Multiplication

Element-wise multiplication:

    a * b

Matrix multiplication:

    a @ b

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

Output:

    [[19 22]
     [43 50]]

---

# 🧮 Dot Product

For one-dimensional arrays:

    a = np.array([1, 2, 3])
    b = np.array([4, 5, 6])

    print(np.dot(a, b))

Output:

    32

Calculation:

    1×4 + 2×5 + 3×6
    = 4 + 10 + 18
    = 32

---

# 🔄 Matrix Transpose

    matrix.T

or:

    np.transpose(matrix)

---

# 🔢 Matrix Determinant

    matrix = np.array([
        [1, 2],
        [3, 4]
    ])

    determinant = np.linalg.det(matrix)

---

# 🔁 Matrix Inverse

    inverse = np.linalg.inv(matrix)

A matrix must satisfy the mathematical requirements for an inverse to exist.

---

# 🧮 Solving Linear Equations

For a system:

    Ax = b

NumPy can solve it using:

    x = np.linalg.solve(A, b)

This is generally preferable to explicitly calculating the inverse for solving linear systems.

---

# 📦 Broadcasting

Broadcasting allows NumPy to perform operations between arrays of compatible shapes.

Example:

    arr = np.array([1, 2, 3])

    result = arr + 10

Output:

    [11 12 13]

The scalar `10` is conceptually applied to every element.

Another example:

    arr = np.array([
        [1, 2, 3],
        [4, 5, 6]
    ])

    result = arr + np.array([10, 20, 30])

Output:

    [[11 22 33]
     [14 25 36]]

Broadcasting is one of the key features that makes NumPy powerful for numerical computation.

---

# 💾 Copy vs View

NumPy arrays can share underlying data.

## View

A view provides another way to access existing array data.

    arr = np.array([1, 2, 3, 4])

    view = arr.view()

Changes to the view can affect the original array because they can share the same underlying data.

## Copy

A copy creates independent data:

    arr = np.array([1, 2, 3, 4])

    copy_arr = arr.copy()

Changes to the copy do not modify the original array.

---

# 🔗 Combining Conditions

NumPy supports logical operations for arrays.

Use:

    &

for AND,

    |

for OR,

and:

    ~

for NOT.

Example:

    arr = np.array([10, 20, 30, 40, 50])

    result = arr[(arr > 20) & (arr < 50)]

Output:

    [30 40]

Do not use Python's `and` and `or` directly for element-wise array conditions.

---

# 📊 Unique Values

`np.unique()` returns unique elements.

    arr = np.array([1, 2, 2, 3, 3, 3])

    print(np.unique(arr))

Output:

    [1 2 3]

It can also return counts:

    values, counts = np.unique(
        arr,
        return_counts=True
    )

---

# 🧮 Cumulative Functions

Cumulative sum:

    arr = np.array([1, 2, 3, 4])

    print(np.cumsum(arr))

Output:

    [ 1  3  6 10]

Cumulative product:

    print(np.cumprod(arr))

Output:

    [ 1  2  6 24]

---

# 📐 Mathematical Constants

NumPy provides common mathematical constants.

Pi:

    np.pi

Euler's number:

    np.e

Example:

    print(np.pi)

---

# 📐 Trigonometric Functions

NumPy provides:

    np.sin()
    np.cos()
    np.tan()

Example:

    angles = np.array([0, np.pi / 2, np.pi])

    print(np.sin(angles))

Angles are expressed in radians.

---

# 🔢 Rounding

Round values using:

    arr = np.array([1.234, 2.567, 3.891])

    print(np.round(arr, 2))

Other useful functions include:

    np.floor()
    np.ceil()
    np.trunc()

---

# 🧹 Handling NaN

NaN means "Not a Number".

Example:

    arr = np.array([1, 2, np.nan, 4])

Check for NaN:

    print(np.isnan(arr))

Output:

    [False False  True False]

Find the mean while ignoring NaN:

    print(np.nanmean(arr))

Other useful functions include:

    np.nansum()
    np.nanmin()
    np.nanmax()
    np.nanmedian()
    np.nanstd()

---

# ♾️ Infinity

NumPy provides:

    np.inf

Example:

    arr = np.array([1, 2, np.inf])

Check for infinity:

    print(np.isinf(arr))

---

# 📁 Saving NumPy Arrays

NumPy provides several ways to save arrays.

## Save as .npy

    arr = np.array([1, 2, 3, 4])

    np.save("data.npy", arr)

Load it:

    loaded = np.load("data.npy")

    print(loaded)

---

# 💾 Saving Multiple Arrays

Use `np.savez()`:

    np.savez(
        "data.npz",
        array1=a,
        array2=b
    )

Load:

    data = np.load("data.npz")

    print(data["array1"])
    print(data["array2"])

---

# 📄 CSV Files

NumPy can also work with text and CSV-style data.

Save:

    np.savetxt(
        "data.csv",
        arr,
        delimiter=","
    )

Load:

    arr = np.loadtxt(
        "data.csv",
        delimiter=","
    )

For complex CSV files with headers, missing values, mixed data types, or labeled columns, pandas is often a better choice.

---

# 🧠 NumPy in Data Science

NumPy is one of the foundations of the Python data-science ecosystem.

It is commonly used with:

- Pandas
- Matplotlib
- SciPy
- Scikit-learn
- TensorFlow
- PyTorch

For example, machine-learning datasets are frequently represented as NumPy arrays.

Example:

    X = np.array([
        [1, 2],
        [3, 4],
        [5, 6]
    ])

    y = np.array([0, 1, 1])

Here:

- `X` can represent input features.
- `y` can represent target labels.

---

# 🤖 NumPy and Machine Learning

NumPy is important in machine learning because many mathematical operations can be performed directly on arrays.

For example:

    weights = np.array([0.5, 0.2])
    features = np.array([10, 20])

    result = np.dot(weights, features)

This type of vector operation appears throughout machine-learning mathematics.

NumPy is also useful for:

- Feature matrices
- Mathematical transformations
- Statistical calculations
- Vector operations
- Matrix operations
- Data preprocessing
- Numerical experimentation

---

# ⚡ Why NumPy Is Fast

Python lists store references to Python objects and are general-purpose containers.

NumPy arrays are designed for homogeneous numerical data and use optimized implementations for many operations.

Instead of manually processing every element with Python loops, NumPy can perform many operations in optimized compiled code.

For example:

    arr = np.array([1, 2, 3, 4, 5])

    result = arr * 10

This performs the multiplication across the entire array without an explicit Python loop.

---

# 🆚 Python List vs NumPy Array

Python list:

    numbers = [1, 2, 3, 4]

NumPy array:

    numbers = np.array([1, 2, 3, 4])

A NumPy array provides numerical operations directly:

    numbers * 2

For a NumPy array, this produces:

    [2 4 6 8]

For a Python list, `numbers * 2` repeats the list instead of performing element-wise multiplication.

---

# 🧪 Complete Beginner Example

    import numpy as np

    # Create an array
    numbers = np.array([10, 20, 30, 40, 50])

    # Display array
    print("Array:", numbers)

    # Shape
    print("Shape:", numbers.shape)

    # Number of dimensions
    print("Dimensions:", numbers.ndim)

    # Number of elements
    print("Size:", numbers.size)

    # Data type
    print("Data type:", numbers.dtype)

    # Sum
    print("Sum:", np.sum(numbers))

    # Mean
    print("Mean:", np.mean(numbers))

    # Minimum
    print("Minimum:", np.min(numbers))

    # Maximum
    print("Maximum:", np.max(numbers))

    # Standard deviation
    print("Standard deviation:", np.std(numbers))

    # Multiply every element
    print("Multiplied:", numbers * 2)

    # Elements greater than 25
    print("Greater than 25:", numbers[numbers > 25])

---

# 🧪 Intermediate Example

    import numpy as np

    # Create a 2D array
    data = np.array([
        [10, 20, 30],
        [40, 50, 60],
        [70, 80, 90]
    ])

    print("Data:")
    print(data)

    print("Shape:", data.shape)

    print("Dimensions:", data.ndim)

    print("Total elements:", data.size)

    print("Column sums:", np.sum(data, axis=0))

    print("Row sums:", np.sum(data, axis=1))

    print("Mean:", np.mean(data))

    print("Maximum:", np.max(data))

    print("Minimum:", np.min(data))

    print("Values greater than 50:")
    print(data[data > 50])

---

# 🧪 End-to-End Mini Project

The following example demonstrates a simple student-score analysis using NumPy.

    import numpy as np

    # Student scores
    scores = np.array([
        [80, 75, 90],
        [65, 70, 72],
        [90, 88, 95],
        [55, 60, 58],
        [78, 82, 85]
    ])

    print("Student Scores:")
    print(scores)

    # Average score of each student
    student_average = np.mean(scores, axis=1)

    print("\nAverage score of each student:")
    print(student_average)

    # Average score of each subject
    subject_average = np.mean(scores, axis=0)

    print("\nAverage score of each subject:")
    print(subject_average)

    # Highest score
    highest = np.max(scores)

    print("\nHighest score:", highest)

    # Lowest score
    lowest = np.min(scores)

    print("Lowest score:", lowest)

    # Students whose average is greater than 75
    high_performers = student_average > 75

    print("\nStudents with average above 75:")
    print(high_performers)

    # Scores greater than or equal to 80
    print("\nScores >= 80:")
    print(scores[scores >= 80])

This example demonstrates:

- Creating NumPy arrays
- Two-dimensional data
- `axis`
- Mean
- Maximum
- Minimum
- Boolean indexing
- Conditional filtering

---

# 🧠 Important NumPy Concepts to Learn

For beginners, the recommended learning order is:

1. Importing NumPy
2. Creating arrays
3. `ndarray`
4. Dimensions
5. Shape
6. Size
7. Data types
8. Indexing
9. Slicing
10. Boolean indexing
11. Array arithmetic
12. Vectorization
13. Aggregation functions
14. Axis
15. Reshaping
16. Transpose
17. Concatenation
18. Broadcasting
19. Copy vs view
20. Random number generation
21. Linear algebra
22. File handling
23. NumPy with Pandas
24. NumPy with Matplotlib
25. NumPy in Machine Learning

---

# ⚠️ Common Mistakes

## Mistake 1: Using a Python list for numerical operations

    numbers = [1, 2, 3]

    print(numbers * 2)

This repeats the list rather than multiplying every element.

Use NumPy when you need numerical array operations:

    numbers = np.array([1, 2, 3])

    print(numbers * 2)

---

## Mistake 2: Confusing shape and size

For:

    arr = np.zeros((3, 4))

The shape is:

    (3, 4)

The size is:

    12

Shape describes the dimensions, while size describes the total number of elements.

---

## Mistake 3: Incorrect axis

For a 2D array:

    np.sum(arr, axis=0)

produces column-wise results.

While:

    np.sum(arr, axis=1)

produces row-wise results.

---

## Mistake 4: Using `and` Instead of `&`

Incorrect:

    arr[(arr > 10) and (arr < 50)]

Correct:

    arr[(arr > 10) & (arr < 50)]

---

## Mistake 5: Forgetting Array Shape Compatibility

Operations between arrays require compatible shapes.

For example:

    a = np.array([1, 2, 3])
    b = np.array([4, 5])

These arrays cannot be added element-wise because their shapes are incompatible.

---

# 📌 NumPy Cheat Sheet

| Task | NumPy |
|---|---|
| Create array | `np.array()` |
| Zeros | `np.zeros()` |
| Ones | `np.ones()` |
| Full array | `np.full()` |
| Range | `np.arange()` |
| Evenly spaced values | `np.linspace()` |
| Identity matrix | `np.eye()` |
| Random values | `np.random` / `np.random.default_rng()` |
| Dimensions | `arr.ndim` |
| Shape | `arr.shape` |
| Total elements | `arr.size` |
| Data type | `arr.dtype` |
| Reshape | `arr.reshape()` |
| Flatten | `arr.flatten()` |
| Transpose | `arr.T` |
| Sort | `np.sort()` |
| Unique values | `np.unique()` |
| Sum | `np.sum()` |
| Mean | `np.mean()` |
| Median | `np.median()` |
| Minimum | `np.min()` |
| Maximum | `np.max()` |
| Standard deviation | `np.std()` |
| Variance | `np.var()` |
| Square root | `np.sqrt()` |
| Absolute value | `np.abs()` |
| Exponential | `np.exp()` |
| Logarithm | `np.log()` |
| Conditional selection | `np.where()` |
| Concatenate | `np.concatenate()` |
| Vertical stack | `np.vstack()` |
| Horizontal stack | `np.hstack()` |
| Dot product | `np.dot()` |
| Matrix multiplication | `@` |
| Matrix inverse | `np.linalg.inv()` |
| Solve equations | `np.linalg.solve()` |
| Save array | `np.save()` |
| Load array | `np.load()` |
| Save multiple arrays | `np.savez()` |

---

# 🏁 Conclusion

NumPy is one of the most important libraries in the Python numerical-computing ecosystem.

Its main strength is the `ndarray`, which provides an efficient way to store and manipulate multidimensional numerical data.

By learning NumPy, you gain the foundation required for many areas of Python programming, especially:

- Data Science
- Machine Learning
- Deep Learning
- Scientific Computing
- Statistics
- Engineering
- Numerical Analysis

The most important concepts to master first are arrays, indexing, slicing, shape, dimensions, data types, vectorized operations, aggregation functions, axis, reshaping, broadcasting, and Boolean indexing.

Once these concepts become comfortable, NumPy becomes much less like a mysterious numerical jungle and much more like a powerful calculator with dimensions.

---

# 🔗 Official References

- NumPy Official Documentation:
  https://numpy.org/doc/

- NumPy User Guide:
  https://numpy.org/doc/stable/user/

- NumPy Reference:
  https://numpy.org/doc/stable/reference/

- NumPy Installation Guide:
  https://numpy.org/install/

- NumPy Random Sampling Documentation:
  https://numpy.org/doc/stable/reference/random/

- NumPy Linear Algebra Documentation:
  https://numpy.org/doc/stable/reference/routines.linalg.html