---
layopost
title: "Chuyên đề Tối ưu bằng Prefix Sum"
subtitle: "Định hướng dạy học nội dung tối ưu thuật toán bằng prefix-sum"
tags: [Phương pháp dạy học, Prefix Sum]
author: Hoàng Hà
---


## 🧠 Mục tiêu chuyên đề

* Hiểu rõ khái niệm **Prefix Sum** (tổng tích luỹ).
* Biết cách dùng prefix sum để:

  * Tính tổng nhanh trên đoạn \[L, R].
  * Giảm độ phức tạp từ O(n²) xuống O(n) hoặc O(Q + n).
* Vận dụng giải quyết bài toán tính tổng, kiểm tra điều kiện trên đoạn con.

---

## 📘 Lý thuyết tổng quát

Prefix Sum là mảng `s[]` với:

```
s[0] = 0
s[i] = a[0] + a[1] + ... + a[i - 1]  (1 ≤ i ≤ n)
```

\=> Tổng đoạn \[L..R] = s\[R+1] - s\[L]

### 💡 Áp dụng:

* Tính tổng đoạn con nhanh.
* Tìm đoạn con thoả điều kiện tổng.
* Trả lời nhiều truy vấn tổng đoạn.

---

## 🧪 Các bài tập tiêu biểu

Dưới đây là 5 bài tập kinh điển giúp học sinh hiểu rõ cách chuyển từ brute-force sang dùng prefix sum. Mỗi bài đều chỉ ra:

* **Cách brute-force ban đầu** và độ phức tạp.
* **Cách nghĩ để tối ưu** bằng prefix sum.
* **So sánh độ phức tạp sau tối ưu.**

### Bài 1: Tính tổng đoạn con (Range Sum Query)

* **Link**: [LeetCode 303](https://leetcode.com/problems/range-sum-query-immutable/)
* **Mô tả**: Cho mảng a\[], trả lời Q truy vấn tổng từ a\[L] đến a\[R].
* **Brute-force**: Với mỗi truy vấn, duyệt từ L đến R → O(Q × n).
* **Cách tối ưu**: Dùng mảng prefix s\[], tính trước tổng tích lũy → mỗi truy vấn chỉ cần s\[R+1] - s\[L].
* **Độ phức tạp**:

  * Trước: O(Q × n)
  * Sau: O(n + Q)

---

### Bài 2: Tổng đoạn con bằng k dài nhất

* **Link**: [LeetCode 325](https://leetcode.com/problems/maximum-size-subarray-sum-equals-k/)
* **Mô tả**: Cho mảng số nguyên a\[], tìm độ dài lớn nhất của đoạn con liên tiếp có tổng bằng k.
* **Brute-force**: Duyệt mọi cặp (i, j), tính tổng từ a\[i] đến a\[j] → O(n²).
* **Cách tối ưu**: Tạo prefix sum s\[], lưu s\[i] vào hashmap theo vị trí đầu tiên xuất hiện. Với mỗi s\[j], nếu tồn tại s\[i] = s\[j] - k → đoạn i..j có tổng k.
* **Độ phức tạp**:

  * Trước: O(n²)
  * Sau: O(n)

---

### Bài 3: Kiểm tra đoạn con chia hết cho k

* **Link**: [LeetCode 523](https://leetcode.com/problems/continuous-subarray-sum/)
* **Mô tả**: Có đoạn con liên tiếp dài ≥ 2 chia hết cho k không?
* **Brute-force**: Duyệt mọi đoạn (i, j), tính tổng rồi kiểm tra chia hết cho k → O(n²).
* **Cách tối ưu**: Tạo prefix sum, với mỗi tổng `s`, tính `s % k`. Nếu cùng một giá trị `mod` xuất hiện ở 2 vị trí cách nhau ≥ 2 → tồn tại đoạn chia hết.
* **Độ phức tạp**:

  * Trước: O(n²)
  * Sau: O(n)

---

### Bài 4: Tổng hình chữ nhật con lớn nhất (2D prefix sum)

* **Link**: [UVa 108](https://onlinejudge.org/external/1/108.pdf)
* **Mô tả**: Ma trận n×n, tìm hình chữ nhật con có tổng lớn nhất.
* **Brute-force**: Duyệt mọi hình chữ nhật → 4 vòng lặp → O(n⁴).
* **Cách tối ưu**: Duyệt cặp cột (left, right), tính tổng trên từng hàng → chuyển về bài tổng dãy con lớn nhất bằng Kadane → O(n³).
* **Độ phức tạp**:

  * Trước: O(n⁴)
  * Sau: O(n³)

---

### Bài 5: Tìm số lượng đoạn con có tổng ≤ k

* **Link**: [HackerRank - Subarray Sum](https://www.hackerrank.com/challenges/subarray-sum/problem)
* **Mô tả**: Đếm số đoạn con liên tiếp có tổng không vượt quá k.
* **Brute-force**: Duyệt mọi cặp (i, j), kiểm tra tổng đoạn a\[i..j] ≤ k → O(n²).
* **Cách tối ưu**: Dùng prefix sum + binary search để đếm số đoạn thoả mãn tại mỗi vị trí.
* **Độ phức tạp**:

  * Trước: O(n²)
  * Sau: O(n log n) (hoặc O(n) nếu dùng cấu trúc phù hợp)

---

## ✅ Tổng kết kỹ thuật

| Tình huống                  | Cách dùng prefix sum          |
| --------------------------- | ----------------------------- |
| Truy vấn tổng đoạn          | s\[R+1] - s\[L]               |
| Tìm đoạn con có tổng bằng K | Lưu s\[i] và dùng hashmap     |
| Nhiều truy vấn              | Tiền xử lý O(n), trả lời O(1) |
| Tổng hình chữ nhật 2D       | Tính prefix theo hàng + cột   |
| So sánh tổng với K          | Kết hợp binary search / map   |

---

**Prefix sum là kỹ thuật nền tảng và mạnh mẽ – nên luyện thuần thục trước khi bước vào quy hoạch động hoặc cấu trúc dữ liệu nâng cao.**
