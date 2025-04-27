---
layout: post
title: Chuyên đề Mảng cộng dồn (Prefix Sum)
subtitle: Làm chủ kỹ thuật Prefix Sum để xử lý nhanh tổng đoạn
tags: [Prefix Sum]
author: Hoàng Hà
---

**Mảng cộng dồn (Prefix Sum)** là một kỹ thuật thuật toán đơn giản nhưng cực kỳ hiệu quả, cho phép tính nhanh tổng của bất kỳ đoạn con liên tiếp nào trong mảng. Bằng cách tiền xử lý trước một mảng tổng tích lũy, ta có thể trả lời các truy vấn tổng đoạn trong thời gian `O(1)`, thay vì phải cộng lại từng phần tử. Kỹ thuật này đặc biệt hữu dụng trong các bài toán có nhiều truy vấn tổng, yêu cầu tối ưu thời gian, và cũng là nền tảng để phát triển các kỹ thuật nâng cao hơn như Difference Array hay 2D Prefix Sum.

# ➕ Giới thiệu kỹ thuật Mảng cộng dồn (Prefix Sum)

## 1. Khi nào nên nghĩ tới Prefix Sum?

- Cần tính tổng các đoạn con liên tiếp nhanh.
- Bài có nhiều truy vấn tổng đoạn `a[l..r]`.
- Tính toán các chỉ số cộng dồn, tiền tố, hoặc tổng động.

## 2. Độ phức tạp yêu cầu

- Tính tổng đoạn con: **O(1)** sau tiền xử lý **O(n)**.
- Trả lời nhiều truy vấn tổng nhanh chóng.

---

# 🔥 Các biến thể thường gặp

| Biến thể | Mô tả |
|:---|:---|
| 1D Prefix Sum | Tổng đoạn trên mảng 1 chiều |
| 2D Prefix Sum | Tổng vùng chữ nhật trên bảng 2D |
| Difference Array | Cập nhật nhiều lần hiệu quả (range update) |

---

# 🛠 Công thức khung cơ bản

## 1D Prefix Sum

```python
prefix[0] = 0
for i in range(1, n+1):
    prefix[i] = prefix[i-1] + a[i-1]

# Tổng từ a[l] đến a[r] = prefix[r+1] - prefix[l]
```

## 2D Prefix Sum

```python
prefix[i][j] = prefix[i-1][j] + prefix[i][j-1] - prefix[i-1][j-1] + grid[i-1][j-1]

# Tổng hình chữ nhật từ (x1,y1) đến (x2,y2):
# prefix[x2+1][y2+1] - prefix[x1][y2+1] - prefix[x2+1][y1] + prefix[x1][y1]
```

---

# 📘 5 Bài tập mẫu (có phân tích tư duy)

## Bài 1: Range Sum Query - Immutable (LeetCode)

**Link:** [303. Range Sum Query - Immutable](https://leetcode.com/problems/range-sum-query-immutable/)

**Đề bài:** Trả lời nhiều truy vấn tổng đoạn `[i..j]` trong mảng.

**Phân tích:**
- **Brute-force:** Tính tổng từng lần, `O(n)` mỗi truy vấn.
- **Prefix Sum:** Chuẩn bị trước, mỗi truy vấn `O(1)`.

**Code mẫu:**  
Python và C++ giống mẫu khung trên.

---

## Bài 2: Subarray Sum Equals K (LeetCode)

**Link:** [560. Subarray Sum Equals K](https://leetcode.com/problems/subarray-sum-equals-k/)

**Đề bài:** Đếm số đoạn con có tổng đúng bằng `k`.

**Phân tích:**
- Prefix Sum + HashMap lưu số lượng tổng phụ.

---

## Bài 3: Maximum Sum Rectangle (2D) (LeetCode Hard)

**Link:** [Kadane 2D biến thể](https://leetcode.com/problems/max-sum-of-rectangle-no-larger-than-k/)

**Đề bài:** Tìm tổng lớn nhất hình chữ nhật ≤ k.

**Phân tích:**
- 2D Prefix Sum hoặc Optimized Sliding Window.

---

## Bài 4: Range Sum Query 2D - Immutable (LeetCode)

**Link:** [304. Range Sum Query 2D - Immutable](https://leetcode.com/problems/range-sum-query-2d-immutable/)

**Đề bài:** Truy vấn tổng vùng hình chữ nhật.

**Phân tích:**
- 2D Prefix Sum chuẩn.

---

## Bài 5: Array Manipulation (HackerRank)

**Link:** [Array Manipulation - HackerRank](https://www.hackerrank.com/challenges/crush/problem)

**Đề bài:** Cập nhật nhiều lần tổng đoạn.

**Phân tích:**
- Difference Array để cập nhật nhanh.

---

# 📝 Danh sách 10 bài tự luyện

| STT | Link | Mô tả | Gợi ý |
|:--:|:----|:-----|:-----|
| 1 | [Range Sum Query - LeetCode](https://leetcode.com/problems/range-sum-query-immutable/) | Tổng đoạn | Prefix Sum |
| 2 | [Subarray Sum Equals K](https://leetcode.com/problems/subarray-sum-equals-k/) | Đếm đoạn tổng k | Prefix Sum + HashMap |
| 3 | [Range Sum Query 2D](https://leetcode.com/problems/range-sum-query-2d-immutable/) | Tổng hình chữ nhật | 2D Prefix |
| 4 | [Maximum Size Subarray Sum Equals k](https://leetcode.com/problems/maximum-size-subarray-sum-equals-k/) | Đoạn dài nhất tổng k | HashMap |
| 5 | [Maximum Sum Rectangle](https://leetcode.com/problems/max-sum-of-rectangle-no-larger-than-k/) | Tổng max ≤ k | 2D Prefix |
| 6 | [Matrix Block Sum](https://leetcode.com/problems/matrix-block-sum/) | Tổng lân cận trong ma trận | 2D Prefix |
| 7 | [Sum of All Odd Length Subarrays](https://leetcode.com/problems/sum-of-all-odd-length-subarrays/) | Tổng đoạn lẻ | Prefix Trick |
| 8 | [Array Manipulation (Hackerrank)](https://www.hackerrank.com/challenges/crush/problem) | Range update | Difference Array |
| 9 | [Minimum Value to Get Positive Step by Step Sum](https://leetcode.com/problems/minimum-value-to-get-positive-step-by-step-sum/) | Xử lý tổng | Theo dõi prefix min |
| 10 | [Number of Subarrays with Bounded Maximum](https://leetcode.com/problems/number-of-subarrays-with-bounded-maximum/) | Đếm đoạn thỏa mãn | Biến thể Prefix |

---

# 🎯 Ghi chú

- Kỹ thuật Prefix Sum **cực kỳ mạnh** để tối ưu từ `O(n)` hoặc `O(n²)` xuống `O(1)` khi cần tính tổng đoạn nhiều lần.
- Kết hợp HashMap hoặc Sliding Window có thể giải nhiều bài đếm đoạn, tìm tổng động.

