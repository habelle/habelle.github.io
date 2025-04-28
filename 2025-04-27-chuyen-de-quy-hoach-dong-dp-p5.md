---
layout: post
title: Chuyên đề Quy hoạch động (Phần 5)
subtitle: Bài tập luyện tập Quy hoạch động từ dễ tới khó
tags: [dp, Quy hoạch động]
author: Hoàng Hà
---

# Bài tập Quy hoạch động - Bài 21 đến 25

---

### Bài 21: [Burst Balloons](https://leetcode.com/problems/burst-balloons/)

- **Đề bài (dịch chi tiết)**:
  Bạn có n quả bóng, được đánh số từ 0 đến n-1, mỗi quả bóng có điểm số. Khi bạn bắn quả bóng i, bạn nhận được điểm số nums[left] * nums[i] * nums[right], với left và right là các quả bóng còn lại gần nhất bên trái và bên phải quả bóng i. Tính điểm số tối đa có thể nhận được.

- **Hướng dẫn thuật toán**:
  - **Định nghĩa hàm DP**: `dp[i][j]` là điểm tối đa có thể đạt được khi chỉ bắn bóng từ i đến j.
  - **Cách chuyển trạng thái**:
    - Chọn quả bóng k (i <= k <= j) làm quả bóng cuối cùng bắn trong đoạn [i,j].
    - Công thức: `dp[i][j] = max(dp[i][k-1] + nums[i-1]*nums[k]*nums[j+1] + dp[k+1][j])`
  - **Cơ sở**: dp[i][i] là bắn 1 quả bóng.

- **Code mẫu C++**:
```cpp
class Solution {
public:
    int maxCoins(vector<int>& nums) {
        int n = nums.size();
        nums.insert(nums.begin(), 1);
        nums.push_back(1);
        vector<vector<int>> dp(n+2, vector<int>(n+2, 0));
        for (int len = 1; len <= n; ++len) {
            for (int i = 1; i <= n-len+1; ++i) {
                int j = i + len - 1;
                for (int k = i; k <= j; ++k) {
                    dp[i][j] = max(dp[i][j],
                        dp[i][k-1] + nums[i-1]*nums[k]*nums[j+1] + dp[k+1][j]);
                }
            }
        }
        return dp[1][n];
    }
};
```

---

### Bài 22: [Perfect Squares](https://leetcode.com/problems/perfect-squares/)

- **Đề bài (dịch chi tiết)**:
  Cho số nguyên n. Tính số lượng bình phương hoàn hảo ít nhất cần dùng để tổng thành n.

- **Hướng dẫn thuật toán**:
  - **Định nghĩa hàm DP**: `dp[i]` là số lượng bình phương nhỏ nhất để đạt tổng i.
  - **Cách chuyển trạng thái**: 
    - Với mỗi bình phương j*j <= i: `dp[i] = min(dp[i], dp[i-j*j] + 1)`
  - **Cơ sở**: `dp[0] = 0`

- **Code mẫu C++**:
```cpp
class Solution {
public:
    int numSquares(int n) {
        vector<int> dp(n+1, INT_MAX);
        dp[0] = 0;
        for (int i = 1; i <= n; ++i) {
            for (int j = 1; j*j <= i; ++j) {
                dp[i] = min(dp[i], dp[i-j*j]+1);
            }
        }
        return dp[n];
    }
};
```

---

### Bài 23: [Word Break](https://leetcode.com/problems/word-break/)

- **Đề bài (dịch chi tiết)**:
  Cho một chuỗi s và một danh sách từ điển wordDict. Kiểm tra xem s có thể được tách thành các từ trong wordDict hay không.

- **Hướng dẫn thuật toán**:
  - **Định nghĩa hàm DP**: `dp[i]` là true nếu s[0..i-1] có thể tách hợp lệ.
  - **Cách chuyển trạng thái**: với mỗi j < i, nếu dp[j] == true và s[j..i-1] thuộc wordDict thì dp[i] = true.
  - **Cơ sở**: `dp[0] = true`

- **Code mẫu C++**:
```cpp
class Solution {
public:
    bool wordBreak(string s, vector<string>& wordDict) {
        unordered_set<string> dict(wordDict.begin(), wordDict.end());
        vector<bool> dp(s.size()+1, false);
        dp[0] = true;
        for (int i = 1; i <= s.size(); ++i) {
            for (int j = 0; j < i; ++j) {
                if (dp[j] && dict.count(s.substr(j, i-j))) {
                    dp[i] = true;
                    break;
                }
            }
        }
        return dp[s.size()];
    }
};
```

---

### Bài 24: [Interleaving String](https://leetcode.com/problems/interleaving-string/)

- **Đề bài (dịch chi tiết)**:
  Cho ba chuỗi s1, s2, s3. Kiểm tra xem s3 có thể tạo thành bằng cách trộn s1 và s2 theo đúng thứ tự không.

- **Hướng dẫn thuật toán**:
  - **Định nghĩa hàm DP**: `dp[i][j]` true nếu s1[0..i-1] và s2[0..j-1] có thể tạo thành s3[0..i+j-1].
  - **Cách chuyển trạng thái**:
    - Nếu s1[i-1]==s3[i+j-1] và dp[i-1][j]
    - Hoặc s2[j-1]==s3[i+j-1] và dp[i][j-1]
  - **Cơ sở**: `dp[0][0] = true`

- **Code mẫu C++**:
```cpp
class Solution {
public:
    bool isInterleave(string s1, string s2, string s3) {
        int m = s1.size(), n = s2.size();
        if (m + n != s3.size()) return false;
        vector<vector<bool>> dp(m+1, vector<bool>(n+1, false));
        dp[0][0] = true;
        for (int i = 0; i <= m; ++i) {
            for (int j = 0; j <= n; ++j) {
                if (i > 0 && s1[i-1] == s3[i+j-1])
                    dp[i][j] = dp[i][j] || dp[i-1][j];
                if (j > 0 && s2[j-1] == s3[i+j-1])
                    dp[i][j] = dp[i][j] || dp[i][j-1];
            }
        }
        return dp[m][n];
    }
};
```

---

### Bài 25: [Scramble String](https://leetcode.com/problems/scramble-string/)

- **Đề bài (dịch chi tiết)**:
  Cho hai chuỗi s1 và s2, kiểm tra xem s2 có thể tạo thành từ s1 bằng cách tráo đổi các phần con không.

- **Hướng dẫn thuật toán**:
  - **Định nghĩa hàm DP**: `dp[i][j][len]` true nếu s1 từ i có độ dài len có thể tráo thành s2 từ j.
  - **Cách chuyển trạng thái**:
    - Thử tất cả các cách chia thành hai phần và kiểm tra hoán đổi hoặc không hoán đổi.
  - **Cơ sở**: nếu độ dài = 1 thì kiểm tra ký tự bằng nhau.

- **Code mẫu C++**:
```cpp
class Solution {
public:
    bool isScramble(string s1, string s2) {
        int n = s1.size();
        if (n != s2.size()) return false;
        vector<vector<vector<bool>>> dp(n, vector<vector<bool>>(n, vector<bool>(n+1, false)));
        for (int i = 0; i < n; ++i) {
            for (int j = 0; j < n; ++j) {
                dp[i][j][1] = (s1[i] == s2[j]);
            }
        }
        for (int len = 2; len <= n; ++len) {
            for (int i = 0; i <= n-len; ++i) {
                for (int j = 0; j <= n-len; ++j) {
                    for (int k = 1; k < len; ++k) {
                        if ((dp[i][j][k] && dp[i+k][j+k][len-k]) ||
                            (dp[i][j+len-k][k] && dp[i+k][j][len-k])) {
                            dp[i][j][len] = true;
                            break;
                        }
                    }
                }
            }
        }
        return dp[0][0][n];
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

