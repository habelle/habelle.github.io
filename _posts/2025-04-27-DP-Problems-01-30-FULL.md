# Tổng hợp 30 bài tập Quy hoạch động (Dynamic Programming)


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



