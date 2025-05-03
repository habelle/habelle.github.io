---
layout: post
title: "Nguyên tắc tối ưu thuật toán từ brute-force"
subtitle: "Một số nguyên tắc tối ưu thuật toán và bài tập ví dụ cụ thể"
tags: [Phương pháp dạy học]
author: Hoàng Hà
---

## 📖 Giới thiệu

Trong hành trình học lập trình giải thuật, nhiều học sinh bắt đầu bằng cách viết lời giải brute-force – tức là duyệt qua mọi khả năng để giải quyết bài toán. Đây là giai đoạn cần thiết để học sinh hiểu rõ cấu trúc dữ liệu, vòng lặp và logic cơ bản. Tuy nhiên, để giải được các bài toán ở mức nâng cao hơn hoặc đạt hiệu quả tính toán tốt hơn, việc rèn luyện **tư duy tối ưu thuật toán** là bước chuyển không thể thiếu.

Tối ưu không chỉ là việc viết chương trình nhanh hơn, mà là giúp học sinh phát hiện và khai thác các quy luật, cấu trúc đặc biệt của bài toán để loại bỏ các thao tác dư thừa, lặp lại. Tài liệu này ra đời nhằm cung cấp cho giáo viên và học sinh một định hướng rõ ràng để **chuyển giao từ brute-force sang tối ưu một cách bài bản**, thông qua nguyên tắc tư duy và hệ thống bài tập cụ thể.

## 🎯 Mục tiêu

* Hiểu bản chất của việc tối ưu là làm **ít việc hơn** mà vẫn **đúng yêu cầu bài toán**.
* Biết cách phân tích brute-force để **tìm ra quy luật/tính chất** có thể khai thác.
* Biết **từng bước nâng cấp lời giải** từ thô sơ đến tối ưu bằng kỹ thuật phù hợp.

---

## 🧱 Khung tư duy tối ưu hóa từ brute-force

1. **Viết đúng brute-force đã**.
2. **Ước lượng độ phức tạp**: Có bao nhiêu vòng lặp? Bao nhiêu phép tính?
3. **Phát hiện trùng lặp hoặc tính chất lặp lại**:

   * Tổng đoạn → prefix sum
   * Truy vấn giống nhau → lưu cache
   * Đúng/sai theo ngưỡng → binary search
4. **Gợi mở cấu trúc/tính chất bài toán**:

   * Quy hoạch động, tìm min/max liên tiếp, greedy,...
5. **Tối ưu từng bước** → học sinh thấy được *quá trình cải tiến dần*.

---

# 🧪 Bộ 5 bài luyện từ brute-force → tối ưu — Kèm link bài gốc

## 🧮 Bài 1: Tổng dãy con lớn nhất

* **Mô tả**: Cho mảng `n` số nguyên, tìm tổng lớn nhất của một đoạn con liên tiếp.
* **Brute-force**: Duyệt mọi cặp `(i, j)`, tính tổng `a[i]..a[j]` → O(n³)
* **Tối ưu**: Sử dụng thuật toán Kadane → O(n)
* **Kỹ thuật chính**: Prefix sum → Quy hoạch động
* **Link bài gốc**: [UVa 507 - Jill Rides Again](https://onlinejudge.org/index.php?option=onlinejudge&page=show_problem&problem=448)

---

## 🔍 Bài 2: Tìm phần tử ≥ X trong mảng đã sắp xếp

* **Mô tả**: Cho mảng `a[]` đã sắp xếp tăng. Trả lời `Q` truy vấn: tìm phần tử ≥ `X` gần nhất.
* **Brute-force**: Duyệt tuyến tính từng truy vấn → O(Qn)
* **Tối ưu**: Binary search → O(Q log n)
* **Kỹ thuật chính**: Binary search trên mảng có thứ tự
* **Link bài gốc**: [LeetCode 704 - Binary Search](https://leetcode.com/problems/binary-search/)

---

## 🍬 Bài 3: Tìm đoạn con có tổng bằng k dài nhất

* **Mô tả**: Cho mảng `a[]`, tìm độ dài lớn nhất đoạn con liên tiếp có tổng bằng `k`.
* **Brute-force**: Duyệt mọi cặp `(i, j)`, tính tổng đoạn → O(n²)
* **Tối ưu**: Sử dụng prefix sum và hash map → O(n)
* **Kỹ thuật chính**: Prefix sum + Hash map
* **Link bài gốc**: [LeetCode 325 - Maximum Size Subarray Sum Equals k](https://leetcode.com/problems/maximum-size-subarray-sum-equals-k/)

---

## 📦 Bài 4: Truy vấn tổng đoạn con nhiều lần

* **Mô tả**: Cho mảng `a[]`. Có `Q` truy vấn hỏi tổng từ `a[L]` đến `a[R]`.
* **Brute-force**: Duyệt từ `L` đến `R` mỗi truy vấn → O(Qn)
* **Tối ưu**: Tiền xử lý prefix sum → O(n + Q)
* **Kỹ thuật chính**: Tiền xử lý – prefix sum
* **Link bài gốc**: [LeetCode 303 - Range Sum Query - Immutable](https://leetcode.com/problems/range-sum-query-immutable/)

---

## ⚖️ Bài 5: Phân chia công việc tham lam

* **Mô tả**: Cho `n` công việc có thời điểm bắt đầu và kết thúc. Chọn nhiều nhất các công việc không chồng nhau.
* **Brute-force**: Duyệt mọi tập con → O(2ⁿ)
* **Tối ưu**: Sắp xếp theo thời gian kết thúc, duyệt greedy → O(n log n)
* **Kỹ thuật chính**: Greedy + sort theo tiêu chí hợp lý
* **Link bài gốc**: [GeeksforGeeks - Activity Selection Problem](https://www.geeksforgeeks.org/activity-selection-problem-greedy-algo-1/)

---

# 📌 Tổng kết kỹ thuật ứng với từng bài

| Bài | Kỹ thuật tối ưu       | Từ độ phức tạp nào → tối ưu |
| --- | --------------------- | --------------------------- |
| 1   | Prefix sum → Kadane   | O(n³) → O(n)                |
| 2   | Binary search         | O(Qn) → O(Q log n)          |
| 3   | Prefix sum + Hash map | O(n²) → O(n)                |
| 4   | Prefix sum trả lời Q  | O(Qn) → O(Q + n)            |
| 5   | Greedy + sort         | O(2ⁿ) → O(n log n)          |

---

**Tài liệu này dùng để tổ chức dạy chuyển giao từ tư duy duyệt sang tối ưu hoá cho học sinh trung học có nền tảng cơ bản.**
