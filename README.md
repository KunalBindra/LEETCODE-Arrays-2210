# LEETCODE-Arrays-2210
* A **hill** is a point that is **greater** than its neighbors.
* A **valley** is a point that is **smaller** than its neighbors.
* The code checks a triplet: `nums[i], nums[j], nums[j+1]`

---

### ✅ Method Overview

```java
if(nums[i] < nums[j] && nums[j] > nums[j+1] || 
   nums[i] > nums[j] && nums[j] < nums[j+1])
```

This means:

* **Hill** → `nums[i] < nums[j] && nums[j] > nums[j+1]`
* **Valley** → `nums[i] > nums[j] && nums[j] < nums[j+1]`

On finding a hill/valley:

```java
count++;
i = j; // move the base pointer
```

---

### 🔍 Dry Run with Example

#### Input:

```java
int[] nums = {2, 4, 1, 1, 6, 5};
```

#### Initial:

* `count = 0`
* `i = 0`, `j = 1`

---

#### Step-by-step:

| i | j | nums\[i] | nums\[j] | nums\[j+1] | Pattern Match? | count | Action    |
| - | - | -------- | -------- | ---------- | -------------- | ----- | --------- |
| 0 | 1 | 2        | 4        | 1          | Hill (2<4>1)   | 1     | i = j (1) |
| 1 | 2 | 4        | 1        | 1          | No             | 1     |           |
| 1 | 3 | 4        | 1        | 6          | Valley (4>1<6) | 2     | i = j (3) |
| 3 | 4 | 1        | 6        | 5          | Hill (1<6>5)   | 3     | i = j (4) |
| 4 | 5 | 6        | 5        | —          | loop ends      | 3     |           |

---

### ✅ Final Output:

```java
return count; // 3
```

---

### 🧠 Summary:

The logic successfully counts:

* Hills: 4 at index 1, 6 at index 4
* Valleys: 1 at index 3

---
