---
layout: post
title: Chuyên đề Quy hoạch động (Phần 4)
subtitle: Bài tập luyện tập Quy hoạch động từ dễ tới khó
tags: [dp, Quy hoạch động]
author: Hoàng Hà
---

# Bài tập Quy hoạch động - Bài 16 đến 20

---

### Bài 16: [Best Time to Buy and Sell Stock II](https://leetcode.com/problems/best-time-to-buy-and-sell-stock-ii/)

- **Đề bài (dịch chi tiết)**:
  Cho một mảng giá cổ phiếu theo từng ngày. Bạn có thể thực hiện nhiều giao dịch (mua và bán nhiều lần). Tuy nhiên, bạn phải bán cổ phiếu đã mua trước khi mua cổ phiếu khác. Tính lợi nhuận tối đa.

- **Hướng dẫn thuật toán**:
  - **Định nghĩa hàm DP**: không cần mảng dp, chỉ cần cộng tất cả các đoạn tăng.
  - **Cách chuyển trạng thái**: nếu giá[i] > giá[i-1], cộng (giá[i] - giá[i-1]).
  - **Cơ sở**: bắt đầu với lợi nhuận 0.

- **Code mẫu C++**:
```cpp
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        int profit = 0;
        for (int i = 1; i < prices.size(); ++i) {
            if (prices[i] > prices[i-1])
                profit += prices[i] - prices[i-1];
        }
        return profit;
    }
};
```

---

### Bài 17: [Maximum Product Subarray](https://leetcode.com/problems/maximum-product-subarray/)

- **Đề bài (dịch chi tiết)**:
  Cho mảng nums, tìm tích lớn nhất của một dãy con liên tiếp.

- **Hướng dẫn thuật toán**:
  - **Định nghĩa hàm DP**: cần lưu cả maxProduct và minProduct tại mỗi bước.
  - **Cách chuyển trạng thái**:
    - Nếu nums[i] âm, hoán đổi max và min.
    - Cập nhật maxProduct và minProduct bằng cách nhân với nums[i] hoặc bắt đầu lại.
  - **Cơ sở**: maxProduct = minProduct = nums[0]

- **Code mẫu C++**:
```cpp
class Solution {
public:
    int maxProduct(vector<int>& nums) {
        int maxProd = nums[0], minProd = nums[0], res = nums[0];
        for (int i = 1; i < nums.size(); ++i) {
            if (nums[i] < 0)
                swap(maxProd, minProd);
            maxProd = max(nums[i], maxProd * nums[i]);
            minProd = min(nums[i], minProd * nums[i]);
            res = max(res, maxProd);
        }
        return res;
    }
};
```

---

### Bài 18: [Target Sum](https://leetcode.com/problems/target-sum/)

- **Đề bài (dịch chi tiết)**:
  Cho mảng nums và số nguyên target. Mỗi phần tử có thể gán dấu + hoặc -. Tính số cách để tổng bằng target.

- **Hướng dẫn thuật toán**:
  - **Định nghĩa hàm DP**: `dp[i][sum]` là số cách đạt tổng sum xét đến i phần tử.
  - **Cách chuyển trạng thái**:
    - `dp[i][sum] = dp[i-1][sum-nums[i]] + dp[i-1][sum+nums[i]]`
  - **Cơ sở**: `dp[0][0] = 1`

- **Code mẫu C++**:
```cpp
class Solution {
public:
    int findTargetSumWays(vector<int>& nums, int target) {
        int offset = 1000;
        vector<vector<int>> dp(nums.size()+1, vector<int>(2001, 0));
        dp[0][offset] = 1;
        for (int i = 0; i < nums.size(); ++i) {
            for (int sum = 0; sum <= 2000; ++sum) {
                if (dp[i][sum]) {
                    dp[i+1][sum+nums[i]] += dp[i][sum];
                    dp[i+1][sum-nums[i]] += dp[i][sum];
                }
            }
        }
        return (target > 1000 || target < -1000) ? 0 : dp[nums.size()][target+offset];
    }
};
```

---

### Bài 19: [Distinct Subsequences](https://leetcode.com/problems/distinct-subsequences/)

- **Đề bài (dịch chi tiết)**:
  Cho chuỗi s và t. Tính số cách chọn ký tự từ s để tạo ra t (không thay đổi thứ tự).

- **Hướng dẫn thuật toán**:
  - **Định nghĩa hàm DP**: `dp[i][j]` là số cách tạo t[0..j-1] từ s[0..i-1].
  - **Cách chuyển trạng thái**:
    - Nếu s[i-1] == t[j-1]: `dp[i][j] = dp[i-1][j-1] + dp[i-1][j]`
    - Ngược lại: `dp[i][j] = dp[i-1][j]`
  - **Cơ sở**: `dp[i][0] = 1`

- **Code mẫu C++**:
```cpp
class Solution {
public:
    int numDistinct(string s, string t) {
        int m = s.size(), n = t.size();
        vector<vector<unsigned long long>> dp(m+1, vector<unsigned long long>(n+1, 0));
        for (int i = 0; i <= m; ++i) dp[i][0] = 1;
        for (int i = 1; i <= m; ++i) {
            for (int j = 1; j <= n; ++j) {
                if (s[i-1] == t[j-1])
                    dp[i][j] = dp[i-1][j-1] + dp[i-1][j];
                else
                    dp[i][j] = dp[i-1][j];
            }
        }
        return dp[m][n];
    }
};
```

---

### Bài 20: [Edit Distance](https://leetcode.com/problems/edit-distance/)

- **Đề bài (dịch chi tiết)**:
  Cho hai chuỗi word1 và word2. Tính số thao tác tối thiểu (chèn, xóa, thay thế) để biến word1 thành word2.

- **Hướng dẫn thuật toán**:
  - **Định nghĩa hàm DP**: `dp[i][j]` là số bước để biến word1[0..i-1] thành word2[0..j-1].
  - **Cách chuyển trạng thái**:
    - Nếu ký tự giống nhau: `dp[i][j] = dp[i-1][j-1]`
    - Ngược lại: `dp[i][j] = 1 + min(dp[i-1][j], dp[i][j-1], dp[i-1][j-1])`
  - **Cơ sở**: xóa toàn bộ hoặc chèn toàn bộ.

- **Code mẫu C++**:
```cpp
class Solution {
public:
    int minDistance(string word1, string word2) {
        int m = word1.size(), n = word2.size();
        vector<vector<int>> dp(m+1, vector<int>(n+1, 0));
        for (int i = 0; i <= m; ++i) dp[i][0] = i;
        for (int j = 0; j <= n; ++j) dp[0][j] = j;
        for (int i = 1; i <= m; ++i) {
            for (int j = 1; j <= n; ++j) {
                if (word1[i-1] == word2[j-1])
                    dp[i][j] = dp[i-1][j-1];
                else
                    dp[i][j] = 1 + min({dp[i-1][j], dp[i][j-1], dp[i-1][j-1]});
            }
        }
        return dp[m][n];
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

