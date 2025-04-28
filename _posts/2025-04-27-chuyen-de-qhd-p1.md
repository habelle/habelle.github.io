---
layout: post
title: Chuyên đề Quy hoạch động (Phần 1)
subtitle: Bài tập luyện tập Quy hoạch động từ dễ tới khó
tags: [dp, Quy hoạch động]
author: Hoàng Hà
markdown: kramdown
---


# Bài tập Quy hoạch động - Bài 26 đến 30

---

### Bài 26: [Coin Change II](https://leetcode.com/problems/coin-change-ii/)

- **Đề bài (dịch chi tiết)**:
  Cho mảng coins và số nguyên amount. Đếm số cách khác nhau để tạo thành amount bằng các đồng xu.

- **Hướng dẫn thuật toán**:
  - **Định nghĩa hàm DP**: `dp[i]` là số cách để tạo tổng i.
  - **Cách chuyển trạng thái**:
    - Với mỗi coin, cập nhật `dp[i] += dp[i-coin]`.
  - **Cơ sở**: `dp[0] = 1`

- **Code mẫu C++**:
```cpp
class Solution {
public:
    int change(int amount, vector<int>& coins) {
        vector<int> dp(amount+1, 0);
        dp[0] = 1;
        for (int coin : coins) {
            for (int i = coin; i <= amount; ++i) {
                dp[i] += dp[i-coin];
            }
        }
        return dp[amount];
    }
};
```

---

### Bài 27: [Number of Longest Increasing Subsequence](https://leetcode.com/problems/number-of-longest-increasing-subsequence/)

- **Đề bài (dịch chi tiết)**:
  Cho mảng nums. Đếm số lượng dãy con tăng dài nhất.

- **Hướng dẫn thuật toán**:
  - **Định nghĩa hàm DP**: 
    - `dp[i]` là độ dài LIS kết thúc tại i.
    - `cnt[i]` là số dãy LIS kết thúc tại i.
  - **Cách chuyển trạng thái**:
    - Nếu nums[j] < nums[i]:
      - Nếu dp[j]+1 > dp[i], cập nhật dp[i], cnt[i]=cnt[j].
      - Nếu dp[j]+1 == dp[i], cộng cnt[j] vào cnt[i].
  - **Cơ sở**: `dp[i]=1`, `cnt[i]=1`

- **Code mẫu C++**:
```cpp
class Solution {
public:
    int findNumberOfLIS(vector<int>& nums) {
        int n = nums.size(), longest = 0, ans = 0;
        vector<int> dp(n, 1), cnt(n, 1);
        for (int i = 0; i < n; ++i) {
            for (int j = 0; j < i; ++j) {
                if (nums[j] < nums[i]) {
                    if (dp[j]+1 > dp[i]) {
                        dp[i] = dp[j]+1;
                        cnt[i] = cnt[j];
                    } else if (dp[j]+1 == dp[i]) {
                        cnt[i] += cnt[j];
                    }
                }
            }
            if (dp[i] > longest) {
                longest = dp[i];
                ans = cnt[i];
            } else if (dp[i] == longest) {
                ans += cnt[i];
            }
        }
        return ans;
    }
};
```

---

### Bài 28: [Out of Boundary Paths](https://leetcode.com/problems/out-of-boundary-paths/)

- **Đề bài (dịch chi tiết)**:
  Cho lưới m x n, bắt đầu tại (startRow, startColumn), sau maxMove bước, tính số đường đi ra ngoài lưới.

- **Hướng dẫn thuật toán**:
  - **Định nghĩa hàm DP**: `dp[i][j][move]` là số cách đi từ (i,j) với move bước còn lại.
  - **Cách chuyển trạng thái**:
    - Thử 4 hướng: lên, xuống, trái, phải.
  - **Cơ sở**: nếu ra khỏi biên, tăng đếm số đường.

- **Code mẫu C++**:
```cpp
class Solution {
public:
    int findPaths(int m, int n, int maxMove, int startRow, int startColumn) {
        const int MOD = 1e9+7;
        vector<vector<vector<int>>> dp(m, vector<vector<int>>(n, vector<int>(maxMove+1, 0)));
        dp[startRow][startColumn][0] = 1;
        int dirs[4][2] = {{-1,0},{1,0},{0,-1},{0,1}};
        int result = 0;
        for (int move = 0; move < maxMove; ++move) {
            for (int i = 0; i < m; ++i) {
                for (int j = 0; j < n; ++j) {
                    if (dp[i][j][move]) {
                        for (auto& d : dirs) {
                            int ni = i + d[0], nj = j + d[1];
                            if (ni < 0 || nj < 0 || ni >= m || nj >= n)
                                result = (result + dp[i][j][move]) % MOD;
                            else
                                dp[ni][nj][move+1] = (dp[ni][nj][move+1] + dp[i][j][move]) % MOD;
                        }
                    }
                }
            }
        }
        return result;
    }
};
```

---

### Bài 29: [Unique Binary Search Trees](https://leetcode.com/problems/unique-binary-search-trees/)

- **Đề bài (dịch chi tiết)**:
  Cho n, tính số lượng cây BST khác nhau có thể tạo ra từ n số.

- **Hướng dẫn thuật toán**:
  - **Định nghĩa hàm DP**: `dp[n]` là số cây BST với n nút.
  - **Cách chuyển trạng thái**:
    - `dp[n] += dp[i] * dp[n-1-i]` với i = số nút bên trái.
  - **Cơ sở**: `dp[0] = 1`

- **Code mẫu C++**:
```cpp
class Solution {
public:
    int numTrees(int n) {
        vector<int> dp(n+1, 0);
        dp[0] = 1;
        for (int nodes = 1; nodes <= n; ++nodes) {
            for (int left = 0; left < nodes; ++left) {
                dp[nodes] += dp[left] * dp[nodes-left-1];
            }
        }
        return dp[n];
    }
};
```

---

### Bài 30: [Different Ways to Add Parentheses](https://leetcode.com/problems/different-ways-to-add-parentheses/)

- **Đề bài (dịch chi tiết)**:
  Cho biểu thức số và dấu + - *, tính tất cả các giá trị khác nhau có thể đạt được khi thêm dấu ngoặc.

- **Hướng dẫn thuật toán**:
  - **Định nghĩa hàm DP**: DP theo đoạn con.
  - **Cách chuyển trạng thái**:
    - Thử chia tại từng toán tử, tính tổ hợp hai bên.
  - **Cơ sở**: nếu chỉ là số, trả về chính số đó.

- **Code mẫu C++**:
```cpp
class Solution {
public:
    vector<int> diffWaysToCompute(string input) {
        vector<int> res;
        for (int i = 0; i < input.size(); ++i) {
            if (ispunct(input[i])) {
                auto left = diffWaysToCompute(input.substr(0, i));
                auto right = diffWaysToCompute(input.substr(i+1));
                for (auto l : left) {
                    for (auto r : right) {
                        if (input[i] == '+') res.push_back(l+r);
                        else if (input[i] == '-') res.push_back(l-r);
                        else if (input[i] == '*') res.push_back(l*r);
                    }
                }
            }
        }
        if (res.empty()) res.push_back(stoi(input));
        return res;
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
