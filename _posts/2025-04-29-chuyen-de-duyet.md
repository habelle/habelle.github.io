---
layout: post
title: "Chuyên đề: Duyệt toàn bộ các trường hợp trong lập trình"
subtitle: "Kỹ thuật duyệt tuần tự, duyệt tổ hợp, hoán vị, tập con từ cơ bản đến nâng cao"
tags: [Duyệt]
author: Hoàng Hà
use_mathjax: true
---

# Giới thiệu

Duyệt toàn bộ các khả năng là kỹ thuật nền tảng trong lập trình thuật toán. Hiểu rõ cách duyệt tuần tự, duyệt mọi cặp, bộ ba, tập con, hoán vị... giúp học sinh tự tin giải quyết các bài toán yêu cầu liệt kê, kiểm tra, hoặc tối ưu nghiệm trên tập nhỏ.

Bài viết này tổng hợp hướng dẫn từng kiểu duyệt, kèm ví dụ minh họa và bài tập tự luyện.

---

# 1. Duyệt tuần tự

## Mô tả
- Duyệt lần lượt qua tất cả các phần tử trong một tập hợp (mảng, vector).

## Ví dụ mẫu
```cpp
for (int i = 0; i < n; ++i) {
    cout << a[i] << " ";
}
```

## Bài tập tự luyện
- [Printing Array](https://oj.vnoi.info/problem/printarray): In ra lần lượt các phần tử mảng.
- [Sum of Array](https://oj.vnoi.info/problem/sumarray): Tính tổng các phần tử mảng.
- [Maximum Element](https://oj.vnoi.info/problem/maxelement): Tìm phần tử lớn nhất.
- [Even Count](https://oj.vnoi.info/problem/evencount): Đếm số phần tử chẵn.
- [Odd Positions](https://oj.vnoi.info/problem/oddpositions): In các phần tử ở vị trí lẻ.

Gợi ý: Dùng vòng `for` đơn để duyệt từ 0 đến `n-1`.

---

# 2. Duyệt mọi cặp (2 phần tử)

## Mô tả
- Duyệt tất cả các cặp $(i, j)$ với $i < j$.

## Ví dụ mẫu
```cpp
for (int i = 0; i < n; ++i)
    for (int j = i+1; j < n; ++j)
        cout << a[i] << ", " << a[j] << endl;
```

## Bài tập tự luyện
- [Two Sum](https://leetcode.com/problems/two-sum/): Tìm hai số cộng lại được target.
- [Good Pairs](https://leetcode.com/problems/number-of-good-pairs/): Đếm số cặp bằng nhau.
- [Minimum Absolute Difference](https://leetcode.com/problems/minimum-absolute-difference/): Tìm cặp có hiệu nhỏ nhất.
- [Max Product of Two Elements](https://leetcode.com/problems/maximum-product-of-two-elements-in-an-array/): Tìm tích lớn nhất hai phần tử.
- [Sum of Two Integers](https://leetcode.com/problems/sum-of-two-integers/): Thử mọi cặp số nguyên.

Gợi ý: Duyệt hai vòng lồng nhau, chỉ xét $j>i$.

---

# 3. Duyệt mọi bộ ba (3 phần tử)

## Mô tả
- Duyệt tất cả các bộ ba $(i, j, k)$ với $i < j < k$.

## Ví dụ mẫu
```cpp
for (int i = 0; i < n; ++i)
    for (int j = i+1; j < n; ++j)
        for (int k = j+1; k < n; ++k)
            cout << a[i] << ", " << a[j] << ", " << a[k] << endl;
```

## Bài tập tự luyện
- [3Sum](https://leetcode.com/problems/3sum/): Tìm bộ ba có tổng bằng 0.
- [Triangle Count](https://leetcode.com/problems/valid-triangle-number/): Đếm số bộ ba tạo thành tam giác.
- [Triplets with Smaller Sum](https://leetcode.com/problems/3sum-smaller/): Bộ ba có tổng nhỏ hơn target.
- [Closest 3Sum](https://leetcode.com/problems/3sum-closest/): Bộ ba tổng gần nhất target.
- [Three Equal Parts](https://leetcode.com/problems/three-equal-parts/): Chia mảng thành ba phần bằng nhau.

Gợi ý: Ba vòng `for` lồng nhau.

---

# 4. Duyệt mọi bộ 4, 5, 6 phần tử

- Duyệt tương tự bộ 2, bộ 3, thêm vòng lặp cho mỗi thành phần.
- Độ phức tạp tăng rất nhanh: $O(n^k)$ với bộ $k$ phần tử.
- Chỉ áp dụng khi $n$ nhỏ.

## Bài tập tự luyện (Bộ 4)
- [4Sum](https://leetcode.com/problems/4sum/): Tìm bộ bốn có tổng bằng target.
- [Quadruplet Sum to Target](https://www.geeksforgeeks.org/find-all-quadruplets-from-four-arrays-that-sum-up-to-a-given-value/): Tìm bộ bốn từ 4 mảng.
- [Four Sum II](https://leetcode.com/problems/4sum-ii/): Đếm số bộ bốn tổng bằng 0.
- [Rectangle Detection](https://leetcode.com/problems/minimum-area-rectangle/): Tìm hình chữ nhật nhỏ nhất.
- [Maximize Number of Quadruplets](https://leetcode.com/problems/maximum-number-of-quadruplets/): Chọn bộ bốn thỏa điều kiện.

Gợi ý: Duyệt 4 vòng `for` hoặc tối ưu bằng map.

---

# 5. Duyệt mọi tập con (Subset)

## Mô tả
- Với tập $n$ phần tử, có $2^n$ tập con.

## Ví dụ mẫu
```cpp
for (int mask = 0; mask < (1 << n); ++mask) {
    for (int i = 0; i < n; ++i)
        if (mask >> i & 1)
            cout << a[i] << " ";
}
```

## Bài tập tự luyện
- [Subsets](https://leetcode.com/problems/subsets/): Liệt kê tất cả tập con.
- [Subset Sum](https://practice.geeksforgeeks.org/problems/subset-sum-problem/0): Có tồn tại tập con có tổng = target không?
- [K Subsets with Equal Sum](https://leetcode.com/problems/partition-to-k-equal-sum-subsets/): Chia tập thành K tập con có tổng bằng nhau.
- [Minimum Difference Subsets](https://leetcode.com/problems/partition-array-into-two-arrays-to-minimize-sum-difference/): Chia tập sao cho hiệu tổng hai phần nhỏ nhất.
- [Count Subsets with Sum K](https://leetcode.com/problems/target-sum/): Đếm số tập con có tổng bằng k.

Gợi ý: Duyệt bằng bitmask, mỗi bit ứng với chọn/không chọn.

---

# 6. Duyệt mọi hoán vị (Permutation)

## Mô tả
- Với tập $n$ phần tử, có $n!$ hoán vị.

## Ví dụ mẫu
```cpp
sort(a, a+n);
do {
    for (int i = 0; i < n; ++i) cout << a[i] << " ";
} while (next_permutation(a, a+n));
```

## Bài tập tự luyện
- [Permutations](https://leetcode.com/problems/permutations/): Sinh ra tất cả hoán vị.
- [Next Permutation](https://leetcode.com/problems/next-permutation/): Tìm hoán vị kế tiếp.
- [Permutations II](https://leetcode.com/problems/permutations-ii/): Sinh hoán vị không trùng lặp.
- [Sequence Reconstruction](https://leetcode.com/problems/sequence-reconstruction/): Kiểm tra khôi phục hoán vị ban đầu.
- [Rearrange String k Distance Apart](https://leetcode.com/problems/rearrange-string-k-distance-apart/): Xếp chuỗi theo điều kiện khoảng cách.

Gợi ý: Dùng `next_permutation` hoặc đệ quy backtracking.

---

# Kết luận

Hiểu và thành thạo các kỹ thuật duyệt toàn bộ sẽ giúp học sinh:
- Tự tin giải quyết các bài toán nhỏ.
- Làm nền tảng để học thuật toán tối ưu hơn (quy hoạch động, backtracking).
- Rèn luyện khả năng phân tích độ phức tạp.

Chúc bạn luyện tập vui vẻ và tiến bộ vững chắc! 🚀
