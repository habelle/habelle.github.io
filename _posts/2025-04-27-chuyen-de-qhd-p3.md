---
layout: post
title: Chuyên đề Quy hoạch động (Phần 3)
subtitle: Bài tập luyện tập Quy hoạch động từ dễ tới khó
tags: [dp, Quy hoạch động]
author: Hoàng Hà
---

# Bài tập Quy hoạch động - Bài 11 đến 15

---

### Bài 11: [Decode Ways](https://leetcode.com/problems/decode-ways/)

- **Đề bài (dịch chi tiết)**:
  Cho một chuỗi số chứa chỉ các chữ số ('0'-'9'). Mỗi chữ số hoặc cặp chữ số đại diện cho một chữ cái theo mã: '1' -> 'A', '2' -> 'B', ..., '26' -> 'Z'. Tính số cách giải mã chuỗi này.

- **Hướng dẫn thuật toán**:
  - **Định nghĩa hàm DP**: `dp[i]` là số cách giải mã đoạn s[0..i-1].
  - **Cách chuyển trạng thái**:
    - Nếu s[i-1] != '0', cộng dp[i-1].
    - Nếu s[i-2,i-1] thuộc [10..26], cộng dp[i-2].
  - **Cơ sở**: `dp[0] = 1`

- **Code mẫu C++**:
```cpp
class Solution {
public:
    int numDecodings(string s) {
        int n = s.size();
        if (n == 0 || s[0] == '0') return 0;
        vector<int> dp(n+1, 0);
        dp[0] = dp[1] = 1;
        for (int i = 2; i <= n; ++i) {
            if (s[i-1] != '0')
                dp[i] += dp[i-1];
            if (s[i-2] == '1' || (s[i-2] == '2' && s[i-1] <= '6'))
                dp[i] += dp[i-2];
        }
        return dp[n];
    }
};
```

---

### Bài 12: [Jump Game](https://leetcode.com/problems/jump-game/)

- **Đề bài (dịch chi tiết)**:
  Cho một mảng số nguyên nums, mỗi phần tử đại diện cho số bước nhảy tối đa. Kiểm tra xem có thể nhảy tới phần tử cuối hay không.

- **Hướng dẫn thuật toán**:
  - **Định nghĩa hàm DP**: `dp[i]` là true nếu có thể tới vị trí i.
  - **Cách chuyển trạng thái**: từ vị trí j có thể nhảy tới i nếu `j + nums[j] >= i`.
  - **Cơ sở**: `dp[0] = true`

- **Code mẫu C++**:
```cpp
class Solution {
public:
    bool canJump(vector<int>& nums) {
        int maxReach = 0, n = nums.size();
        for (int i = 0; i < n; ++i) {
            if (i > maxReach) return false;
            maxReach = max(maxReach, i + nums[i]);
        }
        return true;
    }
};
```

---

### Bài 13: [Minimum Path Sum](https://leetcode.com/problems/minimum-path-sum/)

- **Đề bài (dịch chi tiết)**:
  Cho một lưới m x n chứa các số không âm, tìm đường đi từ (0,0) tới (m-1,n-1) sao cho tổng nhỏ nhất (chỉ được đi xuống hoặc phải).

- **Hướng dẫn thuật toán**:
  - **Định nghĩa hàm DP**: `dp[i][j]` là tổng nhỏ nhất đến (i,j).
  - **Cách chuyển trạng thái**: `dp[i][j] = min(dp[i-1][j], dp[i][j-1]) + grid[i][j]`
  - **Cơ sở**: góc trên trái = grid[0][0]

- **Code mẫu C++**:
```cpp
class Solution {
public:
    int minPathSum(vector<vector<int>>& grid) {
        int m = grid.size(), n = grid[0].size();
        vector<vector<int>> dp(m, vector<int>(n, 0));
        dp[0][0] = grid[0][0];
        for (int i = 1; i < m; ++i) dp[i][0] = dp[i-1][0] + grid[i][0];
        for (int j = 1; j < n; ++j) dp[0][j] = dp[0][j-1] + grid[0][j];
        for (int i = 1; i < m; ++i) {
            for (int j = 1; j < n; ++j) {
                dp[i][j] = min(dp[i-1][j], dp[i][j-1]) + grid[i][j];
            }
        }
        return dp[m-1][n-1];
    }
};
```

---

### Bài 14: [Palindrome Partitioning II](https://leetcode.com/problems/palindrome-partitioning-ii/)

- **Đề bài (dịch chi tiết)**:
  Cho chuỗi s, cắt chuỗi thành các đoạn sao cho mỗi đoạn là palindrome. Tính số lần cắt tối thiểu.

- **Hướng dẫn thuật toán**:
  - **Định nghĩa hàm DP**: `dp[i]` là số lần cắt tối thiểu cho s[0..i].
  - **Cách chuyển trạng thái**: nếu s[j..i] là palindrome thì `dp[i] = min(dp[i], dp[j-1] + 1)`
  - **Cơ sở**: nếu toàn bộ chuỗi là palindrome thì dp[i]=0.

- **Code mẫu C++**:
```cpp
class Solution {
public:
    int minCut(string s) {
        int n = s.length();
        vector<int> dp(n, 0);
        vector<vector<bool>> pal(n, vector<bool>(n, false));
        for (int i = 0; i < n; ++i) {
            int minCut = i;
            for (int j = 0; j <= i; ++j) {
                if (s[i] == s[j] && (i-j <= 1 || pal[j+1][i-1])) {
                    pal[j][i] = true;
                    minCut = j == 0 ? 0 : min(minCut, dp[j-1] + 1);
                }
            }
            dp[i] = minCut;
        }
        return dp[n-1];
    }
};
```

---

### Bài 15: [Best Time to Buy and Sell Stock](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/)

- **Đề bài (dịch chi tiết)**:
  Cho mảng giá cổ phiếu theo từng ngày. Chọn một ngày mua và một ngày bán để tối đa hóa lợi nhuận. (Phải mua trước khi bán.)

- **Hướng dẫn thuật toán**:
  - **Định nghĩa hàm DP**: không cần dp, chỉ cần lưu minPrice và maxProfit.
  - **Cách chuyển trạng thái**: lợi nhuận tại ngày i là giá[i] - minPrice trước đó.
  - **Cơ sở**: ban đầu minPrice = giá[0].

- **Code mẫu C++**:
```cpp
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        int minPrice = prices[0], maxProfit = 0;
        for (int i = 1; i < prices.size(); ++i) {
            minPrice = min(minPrice, prices[i]);
            maxProfit = max(maxProfit, prices[i] - minPrice);
        }
        return maxProfit;
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

