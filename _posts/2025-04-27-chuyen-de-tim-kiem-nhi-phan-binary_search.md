---
layout: post
title: Chuyên đề Tìm kiếm nhị phân
subtitle: Làm chủ kỹ thuật Binary Search để tối ưu giải thuật
tags: [Binary Search]
author: Hoàng Hà
---

Tìm kiếm nhị phân (Binary Search) là một kỹ thuật thuật toán kinh điển dùng để tìm kiếm hiệu quả trong một không gian có tính chất đơn điệu (tăng, giảm hoặc đúng/sai liên tiếp). Ý tưởng cốt lõi là tại mỗi bước, ta chia đôi khoảng tìm kiếm và chỉ giữ lại nửa không gian có khả năng chứa đáp án. Kỹ thuật này giúp giảm độ phức tạp từ O(n) xuống O(log n), rất phù hợp khi làm việc với mảng đã sắp xếp hoặc khi cần tìm kiếm đáp án thỏa mãn một điều kiện trong một phạm vi giá trị.

# 🔍 Giới thiệu kỹ thuật Tìm kiếm nhị phân (Binary Search)

## 1. Khi nào nên nghĩ tới Binary Search?

- Bài yêu cầu tìm kiếm một giá trị trong **mảng đã sắp xếp**.
- Bài yêu cầu tìm **giá trị nhỏ nhất/lớn nhất** thỏa mãn một điều kiện.
- Không gian tìm kiếm có **tính đơn điệu** (đúng/sai, tăng/giảm).

## 2. Độ phức tạp yêu cầu

- Đa số bài Binary Search có độ phức tạp **O(log n)** cho mảng, hoặc **O(log answer)** nếu tìm kiếm trên miền đáp án.

---

# 🔥 Các biến thể thường gặp

| Biến thể | Mô tả |
|:---:|---|
| Tìm kiếm trên mảng | classic: tìm số |
| Tìm kiếm trên đáp án | parametric search |
| Tìm kiếm trạng thái boolean | tìm ngưỡng đạt điều kiện đúng/sai |

---

# 🛠 Công thức khung cơ bản

```python
left = ... # giá trị nhỏ nhất có thể
right = ... # giá trị lớn nhất có thể

while left <= right:
    mid = (left + right) // 2
    if (mid thỏa mãn điều kiện):
        right = mid - 1 # hoặc left = mid + 1 tùy yêu cầu
    else:
        left = mid + 1
```

---

# 📘 5 Bài tập mẫu (có phân tích tư duy)

## Bài 1: Binary Search (LeetCode)

**Link bài:** [704. Binary Search](https://leetcode.com/problems/binary-search/)

### Đề bài
- Tìm kiếm một giá trị `target` trong mảng đã sắp xếp.

### Phân tích tư duy
- **Brute-force:** Duyệt tuần tự từ đầu đến cuối. `O(n)`.
- **Tối ưu:** Dùng binary search chuẩn. `O(log n)`.

### Code mẫu

```python
def search(nums, target):
    left, right = 0, len(nums) - 1
    while left <= right:
        mid = (left + right) // 2
        if nums[mid] == target:
            return mid
        elif nums[mid] < target:
            left = mid + 1
        else:
            right = mid - 1
    return -1
```

```cpp
int search(vector<int>& nums, int target) {
    int left = 0, right = nums.size() - 1;
    while (left <= right) {
        int mid = (left + right) / 2;
        if (nums[mid] == target) return mid;
        else if (nums[mid] < target) left = mid + 1;
        else right = mid - 1;
    }
    return -1;
}
```

---

## Bài 2: Aggressive Cows (SPOJ)

**Link:** [AGGRCOW - SPOJ](https://www.spoj.com/problems/AGGRCOW/)

### Đề bài
- Cho `n` vị trí stall, cần đặt `c` con bò sao cho khoảng cách nhỏ nhất giữa 2 con bò càng lớn càng tốt.

### Phân tích tư duy
- **Brute-force:** Sinh mọi cách đặt, kiểm tra. `O(2^n)`.
- **Tối ưu:** Tìm khoảng cách lớn nhất qua Binary Search trên đáp án.

---

## Bài 3: Kth Smallest Number in Multiplication Table (LeetCode)

**Link:** [668. Kth Smallest Number in Multiplication Table](https://leetcode.com/problems/kth-smallest-number-in-multiplication-table/)

### Đề bài
- Tìm số nhỏ thứ `k` trong bảng nhân `m x n`.

### Phân tích tư duy
- Binary Search trên giá trị, kiểm tra bao nhiêu số nhỏ hơn hoặc bằng mid.

---

## Bài 4: Capacity to Ship Packages within D Days (LeetCode)

**Link:** [1011. Capacity to Ship Packages](https://leetcode.com/problems/capacity-to-ship-packages-within-d-days/)

### Đề bài
- Chia mảng thành các phần để tổng mỗi phần nhỏ hơn `limit`, sao cho số ngày ≤ `D`.

### Phân tích tư duy
- Binary Search trên đáp án (capacity tối thiểu).

---

## Bài 5: Find Minimum in Rotated Sorted Array (LeetCode)

**Link:** [153. Find Minimum in Rotated Sorted Array](https://leetcode.com/problems/find-minimum-in-rotated-sorted-array/)

### Đề bài
- Mảng đã sắp xếp rồi xoay vòng, tìm phần tử nhỏ nhất.

### Phân tích tư duy
- Binary Search biến thể theo giá trị.

---

# 📝 Danh sách 10 bài tự luyện (Link + Dịch đề + Gợi ý)

| STT | Link | Mô tả | Gợi ý |
|:--:|:----|:-----|:-----|
| 1 | [Binary Search - LeetCode](https://leetcode.com/problems/binary-search/) | Tìm số trong mảng | Tìm mid |
| 2 | [Search Insert Position - LeetCode](https://leetcode.com/problems/search-insert-position/) | Vị trí chèn | Nếu không tìm thấy |
| 3 | [Peak Index in a Mountain Array](https://leetcode.com/problems/peak-index-in-a-mountain-array/) | Tìm đỉnh núi | Binary search peak |
| 4 | [Find First and Last Position](https://leetcode.com/problems/find-first-and-last-position-of-element-in-sorted-array/) | Vị trí đầu/cuối | Hai lần binary search |
| 5 | [Koko Eating Bananas](https://leetcode.com/problems/koko-eating-bananas/) | Ăn chuối | Tìm tốc độ tối thiểu |
| 6 | [Split Array Largest Sum](https://leetcode.com/problems/split-array-largest-sum/) | Chia mảng tổng nhỏ nhất | Binary Search trên tổng |
| 7 | [Minimum Speed to Arrive on Time](https://leetcode.com/problems/minimum-speed-to-arrive-on-time/) | Tốc độ nhỏ nhất | Tìm min thỏa |
| 8 | [Median of Two Sorted Arrays](https://leetcode.com/problems/median-of-two-sorted-arrays/) | Tìm median | Hard: Binary Search |
| 9 | [Square Root (Binary Search Method)](https://leetcode.com/problems/sqrtx/) | Tính căn bậc hai | Search giá trị |
| 10 | [Search a 2D Matrix](https://leetcode.com/problems/search-a-2d-matrix/) | Tìm kiếm trong ma trận | Giả thành array 1D |

---

# 🎯 Ghi chú
- Đa phần bài luyện tập sẽ cần bạn xác định không gian tìm kiếm (`array value`, `answer space`).
- Kỹ thuật tìm kiếm nhị phân cực kỳ mạnh khi kết hợp với kiểm tra điều kiện phức tạp (`parametric search`).

**[Xem thêm các chuyên đề ở đây](https://habelle.github.io/resources/)**