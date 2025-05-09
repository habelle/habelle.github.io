---
layout: post
title: "Chuyên đề: Duyệt toàn bộ các trường hợp trong lập trình (P2)"
subtitle: "Kỹ thuật duyệt tuần tự, duyệt tổ hợp, hoán vị, tập con từ cơ bản đến nâng cao"
tags: [Duyệt]
author: Hoàng Hà
---

# Tuyển tập các bài luyện theo số vòng `for`: từ 1 đến 6 vòng

---

## 🔹 Bài 1 vòng `for` – Running Sum of 1D Array

🔗 Link: [LeetCode 1480](https://leetcode.com/problems/running-sum-of-1d-array/)

### 📋 Mô tả bài toán:
Cho một mảng số nguyên `nums`, hãy trả về mảng `res` sao cho `res[i] = nums[0] + nums[1] + ... + nums[i]`.

### 🔧 Input:
- Một mảng `nums` gồm `n` số nguyên.

### 📤 Output:
- Một mảng `res` có cùng độ dài với `nums`.

### 📌 Ví dụ:
```
Input: [1, 2, 3, 4]
Output: [1, 3, 6, 10]
```

### 🎯 Ràng buộc:
- 1 ≤ nums.length ≤ 1000
- -10⁶ ≤ nums[i] ≤ 10⁶

### 💡 Hướng dẫn thuật toán:
- Duyệt 1 vòng `for` từ i = 1 đến n-1
- Cộng dồn kết quả từ phần tử trước

### ⏱️ Độ phức tạp:
- Thời gian: O(n)
- Bộ nhớ: O(1) nếu tính trực tiếp trên mảng

### 💻 Code C++:
```cpp
vector<int> runningSum(vector<int>& nums) {
    for (int i = 1; i < nums.size(); i++)
        nums[i] += nums[i - 1];
    return nums;
}
```

---

## 🔹 Bài 2 vòng `for` – Two Sum (Brute-force)

🔗 Link: [LeetCode 1](https://leetcode.com/problems/two-sum/)

### 📋 Mô tả bài toán:
Cho một mảng số nguyên `nums` và một số nguyên `target`, hãy trả về **2 chỉ số i, j** sao cho `nums[i] + nums[j] == target`.

### 🔧 Input:
- Mảng `nums`, số nguyên `target`.

### 📤 Output:
- Một mảng gồm 2 chỉ số (0-based).

### 📌 Ví dụ:
```
Input: nums = [2,7,11,15], target = 9
Output: [0,1]
```

### 🎯 Ràng buộc:
- 2 ≤ nums.length ≤ 10⁴
- Chỉ có **một** cặp duy nhất thỏa mãn

### 💡 Hướng dẫn thuật toán:
- Duyệt 2 vòng `for` để kiểm tra tất cả các cặp i < j

### ⏱️ Độ phức tạp:
- Thời gian: O(n²)
- Bộ nhớ: O(1)

### 💻 Code C++:
```cpp
vector<int> twoSum(vector<int>& nums, int target) {
    for (int i = 0; i < nums.size(); i++)
        for (int j = i + 1; j < nums.size(); j++)
            if (nums[i] + nums[j] == target)
                return {i, j};
    return {};
}
```

---

## 🔹 Bài 3 vòng `for` – 3Sum

🔗 Link: [LeetCode 15](https://leetcode.com/problems/3sum/)

### 📋 Mô tả bài toán:
Tìm tất cả bộ ba `a + b + c = 0` trong mảng `nums`, không trùng lặp.

### 🔧 Input:
- Một mảng số nguyên `nums`

### 📤 Output:
- Danh sách các bộ ba có tổng bằng 0

### 📌 Ví dụ:
```
Input: [-1,0,1,2,-1,-4]
Output: [[-1,-1,2],[-1,0,1]]
```

### 🎯 Ràng buộc:
- 3 ≤ nums.length ≤ 3000

### 💡 Hướng dẫn thuật toán:
- Duyệt 3 vòng for (i, j, k) với i < j < k
- Kiểm tra tổng == 0, lưu bộ ba nếu chưa xuất hiện

### ⏱️ Độ phức tạp:
- Thời gian: O(n³)
- Bộ nhớ: O(k) với k là số bộ ba tìm được

### 💻 Code C++:
```cpp
vector<vector<int>> threeSum(vector<int>& nums) {
    vector<vector<int>> res;
    int n = nums.size();
    for (int i = 0; i < n; i++)
        for (int j = i + 1; j < n; j++)
            for (int k = j + 1; k < n; k++)
                if (nums[i] + nums[j] + nums[k] == 0) {
                    vector<int> triplet = {nums[i], nums[j], nums[k]};
                    sort(triplet.begin(), triplet.end());
                    if (find(res.begin(), res.end(), triplet) == res.end())
                        res.push_back(triplet);
                }
    return res;
}
```

---

## 🔹 Bài 4 vòng `for` – 4Sum

🔗 Link: [LeetCode 18](https://leetcode.com/problems/4sum/)

### 📋 Mô tả bài toán:
Tìm tất cả bộ 4 `a + b + c + d = target` không trùng lặp trong mảng.

### 🔧 Input:
- Mảng `nums`, số nguyên `target`

### 📤 Output:
- Danh sách bộ 4 có tổng bằng `target`

### 📌 Ví dụ:
```
Input: nums = [1,0,-1,0,-2,2], target = 0
Output: [[-2,-1,1,2],[-2,0,0,2],[-1,0,0,1]]
```

### 🎯 Ràng buộc:
- 1 ≤ nums.length ≤ 200

### 💡 Hướng dẫn thuật toán:
- Duyệt 4 vòng (i, j, k, l), với i < j < k < l
- Tính tổng và kiểm tra

### ⏱️ Độ phức tạp:
- O(n⁴), dùng được với n nhỏ (~100)

### 💻 Code C++:
```cpp
vector<vector<int>> fourSum(vector<int>& nums, int target) {
    int n = nums.size();
    vector<vector<int>> res;
    for (int i = 0; i < n; i++)
        for (int j = i + 1; j < n; j++)
            for (int k = j + 1; k < n; k++)
                for (int l = k + 1; l < n; l++)
                    if ((long long)nums[i] + nums[j] + nums[k] + nums[l] == target) {
                        vector<int> quad = {nums[i], nums[j], nums[k], nums[l]};
                        sort(quad.begin(), quad.end());
                        if (find(res.begin(), res.end(), quad) == res.end())
                            res.push_back(quad);
                    }
    return res;
}
```

---

## 🔹 Bài 6 vòng `for` – Tổng hình chữ nhật trong ma trận (Brute-force)

🔗 Link: [LeetCode 363](https://leetcode.com/problems/max-sum-of-rectangle-no-larger-than-k/)

### 📋 Mô tả bài toán:
Cho ma trận số nguyên, tìm hình chữ nhật con có tổng **≤ k** và **lớn nhất** có thể.

### 🔧 Input:
- Ma trận `grid` m x n
- Số nguyên `k`

### 📤 Output:
- Tổng lớn nhất ≤ k từ bất kỳ hình chữ nhật con

### 📌 Ví dụ:
```
Input:
matrix = [[1,0,1],[0,-2,3]]
k = 2
Output: 2
```

### 🎯 Ràng buộc:
- m, n ≤ 100 (chỉ dùng brute-force khi nhỏ)

### 💡 Hướng dẫn thuật toán:
- Duyệt r1, r2, c1, c2 → định nghĩa vùng
- Duyệt i, j trong vùng để tính tổng

### ⏱️ Độ phức tạp:
- O(m² × n² × mn) – không dùng được khi m,n > 20

### 💻 Code C++:
```cpp
int maxSumSubmatrix(vector<vector<int>>& matrix, int k) {
    int m = matrix.size(), n = matrix[0].size(), ans = INT_MIN;
    for (int r1 = 0; r1 < m; r1++)
        for (int r2 = r1; r2 < m; r2++)
            for (int c1 = 0; c1 < n; c1++)
                for (int c2 = c1; c2 < n; c2++) {
                    int total = 0;
                    for (int i = r1; i <= r2; i++)
                        for (int j = c1; j <= c2; j++)
                            total += matrix[i][j];
                    if (total <= k)
                        ans = max(ans, total);
                }
    return ans;
}
```---

## 🔹 Bài duyệt mọi tập con – Subsets

🔗 Link: [LeetCode 78](https://leetcode.com/problems/subsets/)

### 📋 Mô tả bài toán:
Cho mảng các số nguyên khác nhau `nums`, hãy trả về **tất cả các tập con** có thể có (gồm cả tập rỗng và chính nó).

### 🔧 Input:
- Một mảng `nums`, độ dài n (n ≤ 10)

### 📤 Output:
- Danh sách tất cả tập con của `nums`

### 📌 Ví dụ:
```
Input: [1, 2, 3]
Output: [[], [1], [2], [3], [1,2], [1,3], [2,3], [1,2,3]]
```

### 💡 Hướng dẫn thuật toán (Bitmask):
- Có tổng cộng `2^n` tập con
- Dùng bitmask từ `0` đến `2^n - 1` để tạo ra từng tập

### ⏱️ Độ phức tạp:
- Thời gian: O(n × 2ⁿ)

### 💻 Code C++:
```cpp
vector<vector<int>> subsets(vector<int>& nums) {
    int n = nums.size();
    vector<vector<int>> res;
    for (int mask = 0; mask < (1 << n); mask++) {
        vector<int> subset;
        for (int i = 0; i < n; i++)
            if (mask & (1 << i))
                subset.push_back(nums[i]);
        res.push_back(subset);
    }
    return res;
}
```

---

## 🔹 Bài duyệt mọi hoán vị – Permutations

🔗 Link: [LeetCode 46](https://leetcode.com/problems/permutations/)

### 📋 Mô tả bài toán:
Cho mảng `nums` gồm các số **khác nhau**, hãy liệt kê tất cả các **hoán vị** có thể.

### 🔧 Input:
- Một mảng `nums`, độ dài n (n ≤ 6)

### 📤 Output:
- Tất cả hoán vị có thể của `nums`

### 📌 Ví dụ:
```
Input: [1, 2, 3]
Output: [[1,2,3], [1,3,2], [2,1,3], [2,3,1], [3,1,2], [3,2,1]]
```

### 💡 Hướng dẫn thuật toán (Backtracking):
- Dùng mảng `used[]` để đánh dấu phần tử đã chọn
- Gọi đệ quy sinh hoán vị

### ⏱️ Độ phức tạp:
- Thời gian: O(n!)

### 💻 Code C++ (Backtracking):
```cpp
vector<vector<int>> res;
vector<int> path;
vector<bool> used;

void dfs(const vector<int>& nums) {
    if (path.size() == nums.size()) {
        res.push_back(path);
        return;
    }
    for (int i = 0; i < nums.size(); i++) {
        if (used[i]) continue;
        used[i] = true;
        path.push_back(nums[i]);
        dfs(nums);
        path.pop_back();
        used[i] = false;
    }
}

vector<vector<int>> permute(vector<int>& nums) {
    res.clear(); path.clear();
    used.assign(nums.size(), false);
    dfs(nums);
    return res;
}
```

### 💻 Code C++ (next_permutation):
```cpp
vector<vector<int>> permute(vector<int>& nums) {
    sort(nums.begin(), nums.end());
    vector<vector<int>> res;
    do {
        res.push_back(nums);
    } while (next_permutation(nums.begin(), nums.end()));
    return res;
}
```


# Bài tập luyện theo số vòng `for` – mỗi nhóm có 3 bài

---

## 🔹 1 vòng `for`

1. [LeetCode 121 – Best Time to Buy and Sell Stock](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/)  
   → Duyệt từ trái sang phải, cập nhật giá nhỏ nhất và lợi nhuận lớn nhất.  
   💡 **Tối ưu**: O(n) duyệt 1 lần, không cần mảng phụ.

2. [LeetCode 724 – Find Pivot Index](https://leetcode.com/problems/find-pivot-index/)  
   → Duyệt từ trái sang, so sánh tổng trái và phải.  
   💡 **Tối ưu**: Tính tổng toàn mảng, sau đó giảm dần.

3. [CSES – Missing Number](https://cses.fi/problemset/task/1083)  
   → Tính tổng từ 1 đến n, trừ đi tổng mảng.  
   💡 **Tối ưu**: O(n), chỉ cần 1 biến cộng dồn.

---

## 🔹 2 vòng `for`

1. [LeetCode 977 – Squares of a Sorted Array](https://leetcode.com/problems/squares-of-a-sorted-array/)  
   → Duyệt và bình phương rồi sắp xếp.  
   💡 **Tối ưu**: Dùng 2 con trỏ từ 2 đầu để xây mảng từ lớn về nhỏ.

2. [CSES – Pair Sums](https://cses.fi/problemset/task/1640)  
   → Tìm 2 phần tử tổng đúng x.  
   💡 **Tối ưu**: Sử dụng map lưu số đã gặp → O(n).

3. [LeetCode 1385 – Distance Value](https://leetcode.com/problems/find-the-distance-value-between-two-arrays/)  
   → Duyệt từng phần tử `a` và so sánh với toàn bộ `b`.  
   💡 **Tối ưu**: Sort `b` rồi dùng binary search → O(n log n).

---

## 🔹 3 vòng `for`

1. [LeetCode 15 – 3Sum](https://leetcode.com/problems/3sum/)  
   → Duyệt i, j, k → tìm tổng 0.  
   💡 **Tối ưu**: Sort mảng và dùng 2 pointers từ j+1 → O(n²).

2. [LeetCode 18 – 4Sum (dạng 3 vòng + tìm nhị phân)](https://leetcode.com/problems/4sum/)  
   → Duyệt 3 chỉ số, tìm phần còn lại bằng binary search.  
   💡 **Tối ưu**: Dùng 2 vòng và 2 pointers → O(n³).

3. [CSES – Dice Combinations](https://cses.fi/problemset/task/1633)  
   → DP[i] = tổng DP[i−j] với j = 1..6  
   💡 **Tối ưu**: Duyệt từng `i`, bên trong duyệt `j = 1..6`.

---

## 🔹 4 vòng `for`

1. [CSES – Subarray Sums I](https://cses.fi/problemset/task/1660)  
   → Đếm số đoạn con có tổng bằng x.  
   💡 **Tối ưu**: Dùng prefix sum + map → O(n)

2. [LeetCode 454 – 4Sum II](https://leetcode.com/problems/4sum-ii/)  
   → Duyệt 2 mảng A, B; 2 mảng C, D.  
   💡 **Tối ưu**: Duyệt A+B lưu map; sau đó duyệt C+D tra lại.

3. [LeetCode 18 – 4Sum (full brute-force)](https://leetcode.com/problems/4sum/)  
   → Duyệt 4 chỉ số để tìm bộ 4 có tổng target.  
   💡 **Tối ưu**: 2 vòng ngoài + 2 pointers → O(n³)

---

## 🔹 5 vòng `for`

1. [LeetCode 304 – Range Sum Query 2D](https://leetcode.com/problems/range-sum-query-2d-immutable/)  
   → Duyệt nhiều hình chữ nhật.  
   💡 **Tối ưu**: Dùng prefix sum 2D → O(1) mỗi truy vấn.

2. [CSES – Rectangle Queries](https://cses.fi/problemset/task/1739)  
   → Tổng vùng chữ nhật trong ma trận.  
   💡 **Tối ưu**: prefix sum 2D + xử lý truy vấn O(1)

3. [AtCoder ABC106 D – AtCoder Express](https://atcoder.jp/contests/abc106/tasks/abc106_d)  
   → Đếm số đoạn con nằm trong [L, R].  
   💡 **Tối ưu**: Tiền xử lý 2D prefix sum, tránh lặp.

---

## 🔹 6 vòng `for`

1. [LeetCode 363 – Max Sum of Rectangle ≤ K](https://leetcode.com/problems/max-sum-of-rectangle-no-larger-than-k/)  
   → Duyệt toàn bộ vùng và tính tổng từng hình chữ nhật.  
   💡 **Tối ưu**: Giảm về O(n³) dùng Kadane + TreeSet.

2. [CSES – Max Subarray Sum II](https://cses.fi/problemset/task/1644)  
   → Duyệt đoạn con có độ dài trong [a,b].  
   💡 **Tối ưu**: Dùng deque + prefix sum → O(n)

3. [USACO Training – Cow Rectangles](http://www.usaco.org/index.php?page=viewproblem2&cpid=18)  
   → Duyệt mọi hình chữ nhật chứa bò trắng hoặc đen.  
   💡 **Tối ưu**: prefix + loại trừ các loại không thỏa.
   
## Lưu ý

Nếu bạn dạy học cần tài liệu này chi tiết hơn: đề bài, hướng dẫn thuật toán, hướng dẫn tối ưu thuật toán, test chấm offline và định hướng dạy học chủ đề này xin vui lòng liên hệ với tôi.