
Consider the task of finding the maximum element in an array using **divide-and-conquer.**

```c
#include <stdio.h>

const int MIN_INT = 0x80000000;

int getMax(int a, int b) {
  return a > b ? a : b;
}

int findMax(int arr[], int left, int right) {
  int max = MIN_INT;

  if (left == right) {
    max = arr[left];
  } else {
    int mid = left + (right - left) / 2;
    max = getMax(findMax(arr, left, mid), findMax(arr, mid + 1, right));
  }
  
  return max;
}

int main() {
  int array[] = {3, 28, 65, 32, 45, 12, 4, 0, -1, 5, -3};
  int size = sizeof(array) / sizeof(int);
  int max = findMax(array, 0, size - 1);

  printf("Max: %d\n", max);

  return 0; // Return 0 to indicate successful execution
}
```

---

However, an **_optimization_** arises when the **sub-array contains only two elements.** At this juncture, rather than further recursive division, a direct comparison suffices to determine the maximum.

```c
int findMax(int arr[], int left, int right) {
  int max = MIN_INT;

  if (left == right) {
    max = arr[left];
  } else if ((right - left + 1) == 2) {
    max = getMax(arr[left], arr[right]); // 🤩
  } else {
    int mid = left + (right - left) / 2;
    max = getMax(findMax(arr, left, mid), findMax(arr, mid + 1, right));
  }

  return max;
}
```

$$T(n) = 2 \cdot T\left(\frac{n}{2}\right) + O(1)\implies O(n)$$