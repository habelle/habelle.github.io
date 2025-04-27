---
layout: post
title: "Chuyên đề Quy hoạch động (Phần 1)"
subtitle: "Bài tập luyện tập Quy hoạch động (Dynamic Programming) từ dễ tới trung bình - Bài 1 đến 5"
tags: [Quy hoạch động, Dynamic Programming, DP]
author: Hoàng Hà
---


# Bài tập Quy hoạch động - Bài 1 đến 5

---

### Bài 1: [Fibonacci Number](https://leetcode.com/problems/fibonacci-number/)

- **Đề bài (dịch chi tiết)**:
  Cho một số nguyên `n`, hãy tính số Fibonacci thứ `n`.
  Các số Fibonacci được định nghĩa như sau:
  - `F(0) = 0`
  - `F(1) = 1`
  - `F(n) = F(n-1) + F(n-2)` với `n >= 2`.
  
- **Hướng dẫn thuật toán**:
  - **Định nghĩa hàm DP**: `dp[i]` là số Fibonacci thứ `i`.
  - **Cách chuyển trạng thái**: `dp[i] = dp[i-1] + dp[i-2]`
  - **Cơ sở**: `dp[0] = 0`, `dp[1] = 1`

- **Code mẫu C++**:
```cpp
class Solution {
public:
    int fib(int n) {
        if (n <= 1) return n;
        vector<int> dp(n + 1, 0);
        dp[1] = 1;
        for (int i = 2; i <= n; ++i) {
            dp[i] = dp[i-1] + dp[i-2];
        }
        return dp[n];
    }
};
```

---

### Bài 2: [Climbing Stairs](https://leetcode.com/problems/climbing-stairs/)

- **Đề bài (dịch chi tiết)**:
  Bạn đang leo cầu thang. Mỗi lần bạn có thể leo 1 hoặc 2 bậc. Tính số cách để leo lên n bậc.

- **Hướng dẫn thuật toán**:
  - **Định nghĩa hàm DP**: `dp[i]` là số cách leo đến bậc `i`.
  - **Cách chuyển trạng thái**: `dp[i] = dp[i-1] + dp[i-2]`
  - **Cơ sở**: `dp[0] = 1`, `dp[1] = 1`

- **Code mẫu C++**:
```cpp
class Solution {
public:
    int climbStairs(int n) {
        if (n <= 1) return 1;
        vector<int> dp(n + 1, 0);
        dp[0] = dp[1] = 1;
        for (int i = 2; i <= n; ++i) {
            dp[i] = dp[i-1] + dp[i-2];
        }
        return dp[n];
    }
};
```

---

### Bài 3: [House Robber](https://leetcode.com/problems/house-robber/)

- **Đề bài (dịch chi tiết)**:
  Bạn là một tên trộm, muốn trộm tiền từ các ngôi nhà mà không trộm hai nhà liền kề.

- **Hướng dẫn thuật toán**:
  - **Định nghĩa hàm DP**: `dp[i]` là tiền tối đa từ nhà 0 đến nhà `i`.
  - **Cách chuyển trạng thái**: `dp[i] = max(dp[i-1], dp[i-2] + nums[i])`
  - **Cơ sở**: `dp[0] = nums[0]`, `dp[1] = max(nums[0], nums[1])`

- **Code mẫu C++**:
```cpp
class Solution {
public:
    int rob(vector<int>& nums) {
        int n = nums.size();
        if (n == 0) return 0;
        if (n == 1) return nums[0];
        vector<int> dp(n, 0);
        dp[0] = nums[0];
        dp[1] = max(nums[0], nums[1]);
        for (int i = 2; i < n; ++i) {
            dp[i] = max(dp[i-1], dp[i-2] + nums[i]);
        }
        return dp[n-1];
    }
};
```

---

### Bài 4: [Min Cost Climbing Stairs](https://leetcode.com/problems/min-cost-climbing-stairs/)

- **Đề bài (dịch chi tiết)**:
  Bạn leo cầu thang với chi phí tại mỗi bậc. Tính chi phí tối thiểu để leo tới đỉnh.

- **Hướng dẫn thuật toán**:
  - **Định nghĩa hàm DP**: `dp[i]` là chi phí tối thiểu đến bậc `i`.
  - **Cách chuyển trạng thái**: `dp[i] = min(dp[i-1] + cost[i-1], dp[i-2] + cost[i-2])`
  - **Cơ sở**: `dp[0] = 0`, `dp[1] = 0`

- **Code mẫu C++**:
```cpp
class Solution {
public:
    int minCostClimbingStairs(vector<int>& cost) {
        int n = cost.size();
        vector<int> dp(n + 1, 0);
        for (int i = 2; i <= n; ++i) {
            dp[i] = min(dp[i-1] + cost[i-1], dp[i-2] + cost[i-2]);
        }
        return dp[n];
    }
};
```

---

### Bài 5: [Maximum Subarray](https://leetcode.com/problems/maximum-subarray/)

- **Đề bài (dịch chi tiết)**:
  Cho dãy số nguyên, tìm tổng lớn nhất của một dãy con liên tiếp.

- **Hướng dẫn thuật toán**:
  - **Định nghĩa hàm DP**: `dp[i]` là tổng lớn nhất kết thúc tại `i`.
  - **Cách chuyển trạng thái**: `dp[i] = max(nums[i], dp[i-1] + nums[i])`
  - **Cơ sở**: `dp[0] = nums[0]`

- **Code mẫu C++**:
```cpp
class Solution {
public:
    int maxSubArray(vector<int>& nums) {
        int n = nums.size();
        int maxSum = nums[0];
        for (int i = 1; i < n; ++i) {
            if (nums[i-1] > 0)
                nums[i] += nums[i-1];
            maxSum = max(maxSum, nums[i]);
        }
        return maxSum;
    }
};
```
## Series 30 bài tập Quy hoạch động cơ bản - DP cơ bản
- [Mức dễ: Bài 01-05](https://habelle.github.io/2025-04-27-chuyen-de-quy-hoach-dong-dp-01-05/)
- [Mức dễ: Bài 06-10](https://habelle.github.io/2025-04-27-chuyen-de-quy-hoach-dong-dp-06-10/)
- [Mức dễ: Bài 11-15](https://habelle.github.io/2025-04-27-chuyen-de-quy-hoach-dong-dp-11-15/)
- [Mức trung bình: Bài 16-20](https://habelle.github.io/2025-04-27-chuyen-de-quy-hoach-dong-dp-16-20/)
- [Mức trung bình: Bài 21-25](https://habelle.github.io/2025-04-27-chuyen-de-quy-hoach-dong-dp-21-25/)
- [Mức trung bình: Bài 26-30](https://habelle.github.io/2025-04-27-chuyen-de-quy-hoach-dong-dp-26-30/)
