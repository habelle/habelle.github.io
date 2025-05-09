---
layout: post
title: "[Chuyên đề] Kỹ thuật đếm phân phối (Counting Sort)"
subtitle: "Giới thiệu, ví dụ, độ phức tạp và bài tập vận dụng từ LeetCode"
tags: [Counting Sort, Sắp xếp, Kỹ thuật đếm, LeetCode, Dạy học thuật toán]
author: Hoàng Hà
----------------

Counting Sort là một thuật toán sắp xếp tuyến tính hiệu quả khi giá trị các phần tử đầu vào là các số nguyên không âm và nằm trong một phạm vi nhỏ. Thay vì so sánh các phần tử, thuật toán sử dụng kỹ thuật đếm số lần xuất hiện để phân phối lại các phần tử theo đúng thứ tự.

## 🧠 **Chuyên đề: Kỹ thuật đếm phân phối (Counting Sort)**

### 1. **Giới thiệu kỹ thuật Counting Sort**

**Ý tưởng chính**:

* Đếm số lần xuất hiện của mỗi giá trị (mảng `count`).
* Nếu cần giữ thứ tự ổn định, dùng `prefix sum` để tính vị trí bắt đầu của mỗi phần tử.
* Duyệt mảng ban đầu, phân phối phần tử vào đúng vị trí trong mảng kết quả.

**Ưu điểm**:

* Rất nhanh với dãy số nguyên không âm, giá trị nhỏ.
* Không dựa vào phép so sánh nên nhanh hơn `O(n log n)` trong nhiều trường hợp.

**Nhược điểm**:

* Không phù hợp nếu giá trị phần tử trải rộng.
* Chỉ áp dụng tốt với số nguyên không âm.

---

### 2. **Phân tích bài mẫu: Sort Colors (LeetCode 75)**

🔗 Link bài gốc: [https://leetcode.com/problems/sort-colors/](https://leetcode.com/problems/sort-colors/)

#### 📝 Mô tả bài toán

Cho mảng `nums` gồm các số 0, 1, 2. Hãy sắp xếp mảng sao cho các phần tử có thứ tự 0 trước, rồi đến 1 và 2.

#### 📥 Input:

* Mảng `nums` có độ dài từ 1 đến 10⁵.
* Mỗi phần tử là 0, 1 hoặc 2.

#### 📤 Output:

* Mảng `nums` đã được sắp xếp theo thứ tự: 0 → 1 → 2 (in-place).

#### 📌 Ví dụ:

| Input          | Output         |
| -------------- | -------------- |
| \[2,0,2,1,1,0] | \[0,0,1,1,2,2] |

#### 💡 Gợi ý giải:

Dùng counting sort:

* Đếm số lượng mỗi giá trị 0, 1, 2.
* Ghi đè lại mảng theo thứ tự đếm.

#### 📊 Độ phức tạp:

* Thời gian: `O(n)`
* Không gian: `O(1)` (do chỉ dùng thêm mảng `count` có 3 phần tử)

---

### 3. **7 Bài tập vận dụng có hướng dẫn ngắn**

| STT | Tên bài                               | Link                                                                                                                                                                       | Hướng dẫn tư duy                                                                                              |
| --- | ------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| 1   | Sort Colors                           | [https://leetcode.com/problems/sort-colors/](https://leetcode.com/problems/sort-colors/)                                                                                   | Đếm 0, 1, 2 rồi xây mảng mới.                                                                                 |
| 2   | Relative Sort Array                   | [https://leetcode.com/problems/relative-sort-array/](https://leetcode.com/problems/relative-sort-array/)                                                                   | Đếm số lần xuất hiện trong `arr1`, sắp xếp theo thứ tự `arr2`, sau đó thêm phần còn lại theo thứ tự tăng dần. |
| 3   | Top K Frequent Elements               | [https://leetcode.com/problems/top-k-frequent-elements/](https://leetcode.com/problems/top-k-frequent-elements/)                                                           | Đếm tần suất bằng hashmap, dùng bucket sort để gom nhóm theo tần suất.                                        |
| 4   | Sort Integers by The Number of 1 Bits | [https://leetcode.com/problems/sort-integers-by-the-number-of-1-bits/](https://leetcode.com/problems/sort-integers-by-the-number-of-1-bits/)                               | Đếm số bit 1 trong biểu diễn nhị phân, sắp xếp bằng bucket theo số bit.                                       |
| 5   | Maximum Frequency Stack               | [https://leetcode.com/problems/maximum-frequency-stack/](https://leetcode.com/problems/maximum-frequency-stack/)                                                           | Dùng hashmap đếm tần suất, mỗi nhóm có một stack, mô phỏng theo tần suất giảm dần.                            |
| 6   | Count Sort Variant                    | [https://leetcode.com/problems/how-many-numbers-are-smaller-than-the-current-number/](https://leetcode.com/problems/how-many-numbers-are-smaller-than-the-current-number/) | Dùng mảng đếm để biết mỗi số có bao nhiêu số nhỏ hơn nó.                                                      |
| 7   | Counting Bits                         | [https://leetcode.com/problems/counting-bits/](https://leetcode.com/problems/counting-bits/)                                                                               | Dù không sắp xếp, bài toán vẫn dùng kỹ thuật đếm và xây dựng mảng kết quả dựa trên bit.                       |

---

Bạn có thể chọn 2–3 bài đầu để luyện áp dụng trực tiếp Counting Sort, các bài sau giúp mở rộng mô hình tư duy từ đếm sang nhóm, tổ chức dữ liệu.
