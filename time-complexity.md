### Example 01:

```python
def foo(array):
    sum = 0
    product = 1
    for i in range(len(array)):
        sum += array[i]
    for i in range(len(array)):
        product *= array[i]
    print(sum, product)
```

**Analysis:**
The fact that we iterate through the array twice doesn't matter because we drop the constants when we talk about time complexity. So, Time Complexity = O(N) + O(N) = O(2N) = O(N). Space Complexity = O(1) + O(1) = O(2) = O(1).

---

### Example 02:

```python
def printPairs(array):
    for i in range(len(array)):
        for j in range(len(array)):
            print(array[i], array[j])
```

**Analysis:**
The inner for loop has O(N) iterations and it is called N times. Therefore, the runtime is O(N^2). Another way we can see this is by inspecting what the "meaning" of the code is. It is printing all pairs (two-element sequences). There are O(N^2) pairs. Therefore, the runtime is O(N^2). Time Complexity = O(N) * O(N) = O(N^2). Space Complexity = O(1) + O(1) = O(2) = O(1).

---

### Example 03:

```python
def printUnorderedPairs(array):
    for i in range(len(array)):
        for j in range(i + 1, len(array)):
            print(array[i], array[j])
```

**Analysis:**
The first loop will iterate N times, and the second loop will iterate (N - 1) + (N - 2) + ... + 2 + 1 times. This is equal to the sum of the integers from 1 to N - 1, which is (N - 1)N / 2. So, N + (N - 1)N / 2 = N^2 / 2. Therefore, the runtime is O(N^2).

---

### Example 04:

```python
def printUnorderedPairs(arrayA, arrayB):
    for i in range(len(arrayA)):
        for j in range(len(arrayB)):
            if arrayA[i] < arrayB[j]:
                print(arrayA[i], arrayB[j])
```

**Analysis:**
The runtime here is a bit tricky to derive. The outer loop runs N times. How many times does the inner loop run? Well, it depends on the value of arrayA[i]. If arrayA[i] is 1, then the inner loop runs 1 time. If it's 2, then the inner loop runs 2 times. If it's 3, then the inner loop runs 3 times. In general, it runs arrayA[i] times. Therefore, we must sum up arrayA[0] + arrayA[1] + ... + arrayA[N - 1]. This is equal to the sum of all the elements in arrayA. Let's call this sum A. The inner loop runs A times. Therefore, the total runtime is O(AN).

---

### Example 05:

```python
def printUnorderedPairs(arrayA, arrayB):
    for i in range(len(arrayA)):
        for j in range(len(arrayB)):
            for k in range(0, 100000):
                print(arrayA[i], arrayB[j])
```

**Analysis:**
The inner loop runs in constant time. The outer loop runs N times. The middle loop runs M times. Therefore, the total runtime is O(MN).

---

### Example 06:

```python
def reverse(array):
    for i in range(0, len(array) / 2):
        other = len(array) - i - 1
        temp = array[i]
        array[i] = array[other]
        array[other] = temp
```

**Analysis:**
This algorithm runs in O(N) time. The fact that it only goes through half of the array (in terms of iterations) does not impact the big O time. Time Complexity = O(N). Space Complexity = O(1).

---