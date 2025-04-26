---
layout: post
title: Giới thiệu chuyên đề Two Pointers
subtitle: Làm quen kỹ thuật hai con trỏ - Xử lý bài toán hiệu quả hơn
tags: [Two Pointers]
author: Hoàng Hà
---

Two Pointers là một kỹ thuật lập trình cơ bản nhưng cực kỳ hiệu quả, thường được sử dụng để giải quyết các bài toán liên quan đến mảng hoặc chuỗi. Ý tưởng chính là sử dụng hai biến làm "con trỏ" để di chuyển trong cấu trúc dữ liệu, từ đó tối ưu hóa quá trình tìm kiếm hoặc kiểm tra điều kiện mà không cần duyệt tất cả các cặp phần tử. Kỹ thuật này đặc biệt hữu dụng khi dữ liệu đã được sắp xếp hoặc bài toán có yêu cầu tìm kiếm theo cặp, theo đoạn, giúp giảm độ phức tạp từ O(n²) xuống O(n) trong nhiều trường hợp.

# ✌️ Giới thiệu chuyên đề Two Pointers (Hai con trỏ)

## 1. Tổng quan

**Two Pointers** là một trong những kỹ thuật thuật toán nền tảng nhất dành cho học sinh mới luyện lập trình thi đấu hoặc thi HSG kiểu USACO.

Nó cho phép tối ưu rất nhiều bài toán liên quan đến:
- Các cặp phần tử (pair)
- Các đoạn con (subarray)
- Truy vấn trên mảng một cách tuyến tính

## 2. Khi nào nghĩ tới Two Pointers?

- Cần tìm **các cặp** thỏa mãn điều kiện tổng/hiệu/số lượng.
- Xử lý **các đoạn con** có tính chất đặc biệt (ví dụ tổng ≤ K).
- Dữ liệu **đã sắp xếp tăng dần** (ưu tiên áp dụng two pointers đối đầu).
- Muốn tối ưu từ `O(n²)` xuống `O(n)` hoặc `O(n log n)`.

## 3. Các biến thể Two Pointers thường gặp

| Biến thể | Mô tả |
|:--------:|------|
| Two Pointers cùng chiều | left và right cùng tiến về phía trước, co giãn cửa sổ |
| Two Pointers đối đầu | left từ đầu, right từ cuối tiến vào tìm điều kiện |
| Một cố định – Một di động | Fix một con trỏ, tìm kiếm con còn lại phù hợp |

## 4. Độ phức tạp tiêu chuẩn

- Đa số bài sử dụng Two Pointers có độ phức tạp **O(n)** hoặc **O(n log n)**.

## 5. Vai trò trong quá trình học giai đoạn cơ bản

- Là công cụ **giảm độ phức tạp bài toán** một cách tự nhiên.
- Giúp học sinh làm quen với việc **suy nghĩ tối ưu hóa**, nhận diện tình huống bài toán.
- Chuẩn bị tư duy nền cho các chuyên đề nâng cao hơn như Sliding Window, Prefix Sum nâng cao, Dynamic Programming.

> 📚 Hãy làm thật nhiều bài tập Two Pointers để thuần thục thói quen tối ưu hóa ngay từ giai đoạn cơ bản!

# 🧩 Bài mẫu 1: Two Sum II – Input Array is Sorted

**Link bài gốc:** [LeetCode - Two Sum II](https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/)

---

## 1. Mô tả bài toán

Bạn được cho một **mảng các số nguyên đã được sắp xếp theo thứ tự tăng dần** và một **số nguyên mục tiêu** (`target`).

Yêu cầu: **Tìm hai số** trong mảng **có tổng đúng bằng target** và trả về **chỉ số của chúng** (theo quy ước chỉ số **bắt đầu từ 1**).

Mỗi bài có đúng một cặp duy nhất thỏa mãn điều kiện.

Bạn phải thiết kế một thuật toán có độ phức tạp **O(n)**.

---

## 2. Định dạng Input

- Một mảng số nguyên **`numbers`** đã **sắp xếp tăng dần** (có ít nhất hai phần tử).
- Một số nguyên **`target`**.

### Ràng buộc:

- `2 <= numbers.length <= 3 * 10^4`
- `-1000 <= numbers[i] <= 1000`
- `-10^9 <= target <= 10^9`
- Có **chính xác một** cặp số thỏa mãn tổng bằng `target`.

---

## 3. Định dạng Output

- Một mảng gồm **hai số nguyên**: `[index1, index2]`, với `index1 < index2`.
- Các chỉ số bắt đầu từ **1** (không phải từ 0).

---

## 4. Ví dụ

### Ví dụ 1:

**Input:**

```
numbers = [2,7,11,15]
target = 9
```

**Output:**

```
[1,2]
```

**Giải thích:**  
Số `2` (ở vị trí 1) + số `7` (ở vị trí 2) = `9`.

---

### Ví dụ 2:

**Input:**

```
numbers = [2,3,4]
target = 6
```

**Output:**

```
[1,3]
```

**Giải thích:**  
Số `2` (ở vị trí 1) + số `4` (ở vị trí 3) = `6`.

---

### Ví dụ 3:

**Input:**

```
numbers = [-1,0]
target = -1
```

**Output:**

```
[1,2]
```

**Giải thích:**  
Số `-1` (ở vị trí 1) + số `0` (ở vị trí 2) = `-1`.

---

# 🔥 Phân tích tư duy: Brute-force vs Two Pointers

## Cách làm Brute-force (Duyệt tổ hợp tất cả cặp)

- Duyệt tất cả các cặp `(i, j)` với `i < j`.
- Kiểm tra nếu `numbers[i] + numbers[j] == target` thì trả kết quả.

### Code mẫu Brute-force

```python
def twoSum_bruteforce(numbers, target):
    n = len(numbers)
    for i in range(n):
        for j in range(i+1, n):
            if numbers[i] + numbers[j] == target:
                return [i+1, j+1]
```

### Độ phức tạp

- Thời gian: `O(n^2)`
- Không gian: `O(1)`

**Nhận xét:** Với `n = 30000`, tổng số phép so sánh gần 450 triệu → không khả thi.

---

## Cách làm tối ưu: Two Pointers

- Vì mảng đã **sắp xếp tăng dần**, áp dụng kỹ thuật **hai con trỏ đối đầu**:
  - `left` ở đầu, `right` ở cuối.
  - Nếu tổng nhỏ hơn target → `left += 1`
  - Nếu tổng lớn hơn target → `right -= 1`
  - Nếu tổng đúng target → trả kết quả.

### Code mẫu Two Pointers

```python
def twoSum(numbers, target):
    left, right = 0, len(numbers) - 1
    while left < right:
        current_sum = numbers[left] + numbers[right]
        if current_sum == target:
            return [left + 1, right + 1]
        elif current_sum < target:
            left += 1
        else:
            right -= 1
```

```cpp
#include <vector>
using namespace std;

vector<int> twoSum(vector<int>& numbers, int target) {
    int left = 0, right = numbers.size() - 1;
    while (left < right) {
        int current_sum = numbers[left] + numbers[right];
        if (current_sum == target)
            return {left + 1, right + 1};
        else if (current_sum < target)
            ++left;
        else
            --right;
    }
    return {}; // luôn có cặp thỏa mãn
}
```

### Độ phức tạp

- Thời gian: `O(n)`
- Không gian: `O(1)`

**Nhận xét:** Mỗi bước di chuyển chỉ cần kiểm tra 1 lần → tối đa `n` bước.

---

# 🔍 Bảng so sánh nhanh

| Phương pháp  | Thời gian | Không gian | Ghi chú                        |
| ------------ | --------- | ---------- | ------------------------------ |
| Brute-force  | O(n²)     | O(1)       | Không tận dụng dữ liệu sắp xếp |
| Two Pointers | O(n)      | O(1)       | Tận dụng thứ tự tăng dần       |

---

> 🎯 Ghi nhớ:  
> **Kỹ thuật hai con trỏ đối đầu** rất mạnh khi dữ liệu **đã sắp xếp** và bài yêu cầu tìm **cặp thỏa mãn tổng / hiệu / tích**.

** Tìm hiểu thêm về các chuyên đề ở [đây](https://habelle.github.io/resources/)
