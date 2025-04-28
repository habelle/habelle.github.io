---
layout: post
title: Chuyên đề Quy hoạch động (Phần 2)
subtitle: Bài tập luyện tập Quy hoạch động từ dễ tới khó
tags: [dp, Quy hoạch động]
author: Hoàng Hà
---

# Bài tập Quy hoạch động - Bài 6 đến 10

---

### Bài 6: [Unique Paths](https://leetcode.com/problems/unique-paths/)

- **Đề bài (dịch chi tiết)**:
  Một robot bắt đầu tại góc trên bên trái của lưới m x n. Robot chỉ có thể di chuyển xuống hoặc sang phải. Tính số đường đi khác nhau tới góc dưới bên phải.

- **Hướng dẫn thuật toán**:
  - **Định nghĩa hàm DP**: `dp[i][j]` là số đường đi tới ô (i,j).
  - **Cách chuyển trạng thái**: `dp[i][j] = dp[i-1][j] + dp[i][j-1]`
  - **Cơ sở**: hàng đầu tiên và cột đầu tiên đều là 1 cách.

- **Code mẫu C++**:
```cpp
class Solution {
public:
    int uniquePaths(int m, int n) {
        vector<vector<int>> dp(m, vector<int>(n, 1));
        for (int i = 1; i < m; ++i) {
            for (int j = 1; j < n; ++j) {
                dp[i][j] = dp[i-1][j] + dp[i][j-1];
            }
        }
        return dp[m-1][n-1];
    }
};
```

---

### Bài 7: [Coin Change](https://leetcode.com/problems/coin-change/)

- **Đề bài (dịch chi tiết)**:
  Cho các loại tiền coins[] và số amount. Tính số đồng xu ít nhất để tạo thành amount. Nếu không thể tạo ra amount, trả về -1.

- **Hướng dẫn thuật toán**:
  - **Định nghĩa hàm DP**: `dp[i]` là số xu ít nhất để đạt tổng i.
  - **Cách chuyển trạng thái**: `dp[i] = min(dp[i], dp[i-coin] + 1)`
  - **Cơ sở**: `dp[0] = 0`

- **Code mẫu C++**:
```cpp
class Solution {
public:
    int coinChange(vector<int>& coins, int amount) {
        vector<int> dp(amount + 1, amount + 1);
        dp[0] = 0;
        for (int coin : coins) {
            for (int i = coin; i <= amount; ++i) {
                dp[i] = min(dp[i], dp[i-coin] + 1);
            }
        }
        return dp[amount] > amount ? -1 : dp[amount];
    }
};
```

---

### Bài 8: [Longest Common Subsequence](https://leetcode.com/problems/longest-common-subsequence/)

- **Đề bài (dịch chi tiết)**:
  Cho hai chuỗi, tìm độ dài chuỗi con chung dài nhất giữa chúng.

- **Hướng dẫn thuật toán**:
  - **Định nghĩa hàm DP**: `dp[i][j]` là độ dài LCS giữa text1[0..i-1] và text2[0..j-1].
  - **Cách chuyển trạng thái**: nếu ký tự cuối khớp thì `dp[i][j] = dp[i-1][j-1] + 1`, ngược lại `dp[i][j] = max(dp[i-1][j], dp[i][j-1])`
  - **Cơ sở**: nếu 1 trong 2 chuỗi rỗng thì LCS = 0.

- **Code mẫu C++**:
```cpp
class Solution {
public:
    int longestCommonSubsequence(string text1, string text2) {
        int m = text1.size(), n = text2.size();
        vector<vector<int>> dp(m+1, vector<int>(n+1, 0));
        for (int i = 1; i <= m; ++i) {
            for (int j = 1; j <= n; ++j) {
                if (text1[i-1] == text2[j-1])
                    dp[i][j] = dp[i-1][j-1] + 1;
                else
                    dp[i][j] = max(dp[i-1][j], dp[i][j-1]);
            }
        }
        return dp[m][n];
    }
};
```

---

### Bài 9: [Longest Increasing Subsequence](https://leetcode.com/problems/longest-increasing-subsequence/)

- **Đề bài (dịch chi tiết)**:
  Tìm độ dài dãy con tăng dài nhất trong mảng số nguyên.

- **Hướng dẫn thuật toán**:
  - **Định nghĩa hàm DP**: `dp[i]` là độ dài LIS kết thúc tại i.
  - **Cách chuyển trạng thái**: nếu nums[j] < nums[i] thì `dp[i] = max(dp[i], dp[j]+1)`
  - **Cơ sở**: `dp[i] = 1`

- **Code mẫu C++**:
```cpp
class Solution {
public:
    int lengthOfLIS(vector<int>& nums) {
        int n = nums.size(), res = 1;
        vector<int> dp(n, 1);
        for (int i = 1; i < n; ++i) {
            for (int j = 0; j < i; ++j) {
                if (nums[j] < nums[i])
                    dp[i] = max(dp[i], dp[j] + 1);
            }
            res = max(res, dp[i]);
        }
        return res;
    }
};
```

---

### Bài 10: [Partition Equal Subset Sum](https://leetcode.com/problems/partition-equal-subset-sum/)

- **Đề bài (dịch chi tiết)**:
  Cho mảng nums, kiểm tra có thể chia thành hai tập con bằng tổng nhau không.

- **Hướng dẫn thuật toán**:
  - **Định nghĩa hàm DP**: `dp[i]` là true nếu có thể đạt tổng i.
  - **Cách chuyển trạng thái**: với mỗi num, cập nhật `dp[i] |= dp[i-num]`
  - **Cơ sở**: `dp[0] = true`

- **Code mẫu C++**:
```cpp
class Solution {
public:
    bool canPartition(vector<int>& nums) {
        int sum = accumulate(nums.begin(), nums.end(), 0);
        if (sum % 2 != 0) return false;
        sum /= 2;
        vector<bool> dp(sum + 1, false);
        dp[0] = true;
        for (int num : nums) {
            for (int i = sum; i >= num; --i) {
                dp[i] = dp[i] || dp[i-num];
            }
        }
        return dp[sum];
    }
};
```


## Series 30 bài tập Quy hoạch động cơ bản - DP cơ bản
- [Mức dễ: Bài 01-05](https://habelle.github.io/2025-04-27-chuyen-de-qhd-p1/)
- [Mức dễ: Bài 06-10](https://habelle.github.io/2025-04-27-chuyen-de-qhd-p2/)
- [Mức dễ: Bài 11-15](https://habelle.github.io/2025-04-27-chuyen-de-qhd-p3/)
- [Mức trung bình: Bài 16-20](https://habelle.github.io/2025-04-27-chuyen-de-qhd-p4/)
- [Mức trung bình: Bài 21-25](https://habelle.github.io/2025-04-27-chuyen-de-qhd-p5/)
- [Mức trung bình: Bài 26-30](https://habelle.github.io/2025-04-27-chuyen-de-qhd-p6/)
