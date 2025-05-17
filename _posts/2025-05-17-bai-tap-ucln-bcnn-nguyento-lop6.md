---
layout: post
title: "[Bài tập] UCLN – BCNN – Phân tích số nguyên tố (lớp 6)"
subtitle: "Bài tập rèn tư duy cơ bản về số học cho học sinh lớp 6"
tags: [UCLN, BCNN, Số nguyên tố, Lớp 6, Bài tập cơ bản]
author: Hoàng Hà
---


## Bài 1: Tìm UCLN của hai số nguyên dương

**Mô tả bài toán**  
Cho hai số nguyên dương `a` và `b`. Hãy tính ước chung lớn nhất của chúng.

**Tên tệp:** `gcd.cpp`

**Input**  
Một dòng chứa hai số nguyên dương `a` và `b` (1 ≤ a, b ≤ 10⁴).

**Output**  
In ra UCLN của hai số.

**Ví dụ mẫu**

| Input  | Output |
|--------|--------|
| 12 18  | 6      |
| 100 75 | 25     |

**Giải thích**  
- GCD(12, 18) = 6 vì 6 là số lớn nhất chia hết cả 12 và 18.  
- GCD(100, 75) = 25 vì 25 là ước chung lớn nhất.

---

## Bài 2: Kiểm tra hai số có nguyên tố cùng nhau không

**Mô tả bài toán**  
Cho hai số nguyên dương `a` và `b`. Hãy kiểm tra xem chúng có phải là nguyên tố cùng nhau không (tức là UCLN(a, b) = 1).

**Tên tệp:** `cop.cpp`

**Input**  
Một dòng chứa hai số nguyên dương `a` và `b` (1 ≤ a, b ≤ 10⁴).

**Output**  
In `YES` nếu nguyên tố cùng nhau, ngược lại in `NO`.

**Ví dụ mẫu**

| Input | Output |
|-------|--------|
| 8 15  | YES    |
| 9 12  | NO     |

**Giải thích**  
- 8 và 15 không có ước chung nào ngoài 1 ⇒ YES  
- 9 và 12 có ước chung là 3 ⇒ NO

---

## Bài 3: Tìm BCNN của hai số

**Mô tả bài toán**  
Cho hai số nguyên dương `a` và `b`. Hãy tính bội chung nhỏ nhất của chúng.

**Tên tệp:** `lcm.cpp`

**Input**  
Một dòng chứa hai số nguyên dương `a` và `b` (1 ≤ a, b ≤ 10⁴).

**Output**  
In ra BCNN của hai số.

**Ví dụ mẫu**

| Input | Output |
|-------|--------|
| 4 6   | 12     |
| 5 7   | 35     |

**Giải thích**  
- BCNN(4, 6) = 12 là số nhỏ nhất chia hết cho cả 4 và 6.  
- BCNN(5, 7) = 35 là tích của hai số vì chúng nguyên tố cùng nhau.

---

## Bài 4: Tìm số nhỏ nhất chia hết cho cả 2 số và không quá 100

**Mô tả bài toán**  
Cho hai số nguyên dương `a` và `b`. Tìm số nhỏ nhất chia hết cho cả hai mà không vượt quá 100. Nếu không có, in ra `-1`.

**Tên tệp:** `cm100.cpp`

**Input**  
Một dòng chứa hai số nguyên dương `a` và `b` (1 ≤ a, b ≤ 100).

**Output**  
In ra số nhỏ nhất chia hết cho cả hai không vượt quá 100, hoặc `-1` nếu không có.

**Ví dụ mẫu**

| Input | Output |
|-------|--------|
| 7 9   | 63     |
| 11 13 | -1     |

**Giải thích**  
- BCNN(7, 9) = 63 ≤ 100 ⇒ in 63  
- BCNN(11, 13) = 143 > 100 ⇒ in -1

---

## Bài 5: Liệt kê các thừa số nguyên tố của một số

**Mô tả bài toán**  
Cho số nguyên dương `n`. Hãy in ra các thừa số nguyên tố của `n`, theo thứ tự tăng dần (có thể trùng lặp).

**Tên tệp:** `fact.cpp`

**Input**  
Một dòng chứa số nguyên dương `n` (2 ≤ n ≤ 10⁴).

**Output**  
In ra các thừa số nguyên tố, cách nhau bởi dấu cách.

**Ví dụ mẫu**

| Input | Output    |
|-------|-----------|
| 30    | 2 3 5     |
| 60    | 2 2 3 5   |

**Giải thích**  
- 30 = 2 × 3 × 5  
- 60 = 2 × 2 × 3 × 5

---

## Bài 6: Kiểm tra số nguyên tố

**Mô tả bài toán**  
Cho số nguyên dương `n`. Hãy kiểm tra xem `n` có phải là số nguyên tố không.

**Tên tệp:** `prime.cpp`

**Input**  
Một dòng chứa số nguyên dương `n` (2 ≤ n ≤ 10⁴).

**Output**  
In ra `YES` nếu `n` là số nguyên tố, `NO` nếu không.

**Ví dụ mẫu**

| Input | Output |
|-------|--------|
| 29    | YES    |
| 30    | NO     |

**Giải thích**  
- 29 là số nguyên tố (chỉ chia hết cho 1 và chính nó).  
- 30 chia hết cho nhiều số khác ⇒ không phải số nguyên tố.
