---
layout: post
title: Thuật toán sàng ước số
subtitle: Là một biến thể của sàng nguyên tố, dùng để đếm, tính tổng, liệt kê các ước của từng số
tags: [Sàng ước số, Divisor Sieve]
author: Hoàng Hà

---
Đây là cách hiệu quả và dễ cài đặt để xử lý các bài toán liên quan đến ước số trên đoạn từ 1 đến N.

# Thuật toán Sàng Ước Số (Divisor Sieve)

Kỹ thuật **sàng ước số** là một biến thể của sàng Eratosthenes (sàng nguyên tố), dùng để:
- Tính tổng các ước của mỗi số từ 1 đến N
- Đếm số lượng ước của mỗi số
- Hoặc liệt kê tất cả các ước của từng số

---

## 🧠 Ý tưởng chính

Với mỗi số `i` từ 1 đến N, ta duyệt qua tất cả bội số của `i` là `j = i, 2i, 3i, ..., N`, vì `i` là ước của `j`.  
Từ đó, cập nhật thông tin ước cho `j`.

---

## ✅ Ví dụ 1: Tính tổng ước của mỗi số từ 1 đến N

### Code C++

```cpp
#include <bits/stdc++.h>
using namespace std;

const int N = 1e6;
long long sum_div[N + 1]; // Tổng ước của từng số

int main() {
    for (int i = 1; i <= N; ++i) {
        for (int j = i; j <= N; j += i) {
            sum_div[j] += i;
        }
    }

    // Ví dụ: in tổng ước các số từ 1 đến 10
    for (int i = 1; i <= 10; ++i) {
        cout << "Sum of divisors of " << i << " = " << sum_div[i] << '\n';
    }

    return 0;
}
```

### Độ phức tạp

- Tổng số lần lặp: khoảng `N log N`
- Đủ nhanh cho `N` lên tới `1e6`

---

## ✅ Ví dụ 2: Đếm số ước của mỗi số

```cpp
int cnt_div[N + 1];

for (int i = 1; i <= N; ++i) {
    for (int j = i; j <= N; j += i) {
        cnt_div[j]++;
    }
}
```

---

## ✅ Ví dụ 3: Liệt kê tất cả ước của mỗi số

```cpp
vector<int> divisors[N + 1];

for (int i = 1; i <= N; ++i) {
    for (int j = i; j <= N; j += i) {
        divisors[j].push_back(i);
    }
}
```

---

## ⚙️ Ứng dụng

- Tính tổng ước có điều kiện (chỉ lấy ước chẵn, ước nguyên tố, v.v.)
- Tính các hàm số học như:
  - `σ(n)`: tổng các ước của `n`
  - `d(n)`: số lượng ước của `n`
  - `φ(n)`: hàm Euler (nếu dùng sàng nguyên tố)
- Bài toán chia kẹo, chia tiền, tối ưu số lượng nhóm chia hết...

---

## 📌 Ghi chú

Đây là cách hiệu quả và dễ cài đặt để xử lý các bài toán liên quan đến ước số trên đoạn từ 1 đến N.  
Tổng thời gian chạy cho toàn bộ sàng là O(N log N), rất phù hợp để tiền xử lý trong các bài toán lớn.
