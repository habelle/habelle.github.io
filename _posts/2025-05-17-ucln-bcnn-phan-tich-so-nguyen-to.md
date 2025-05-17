---
layout: post
title: "[Chuyên đề] UCLN – BCNN – Phân tích số nguyên tố"
subtitle: "Lý thuyết nền tảng, ví dụ, bài tập có hướng dẫn từ LeetCode và bài tự luyện"
tags: [GCD, LCM, Prime Factorization, Số học, LeetCode, Dạy học thuật toán]
author: Hoàng Hà
---

## 🧠 **Chuyên đề: UCLN – BCNN – Phân tích số nguyên tố**

### 1. **Giới thiệu chuyên đề**

Trong số học, GCD (Ước chung lớn nhất), LCM (Bội chung nhỏ nhất) và phân tích số nguyên tố là nền tảng cho nhiều kỹ thuật khác như chia hết, chia phần, modul, số lượng ước,...  
Việc hiểu rõ ba công cụ cơ bản này sẽ giúp học sinh xử lý tốt các bài toán tiền xử lý, đếm, hoặc tối ưu chia đều các đối tượng.

---

### 2. **Lý thuyết cơ bản**

#### 📌 GCD (Greatest Common Divisor – UCLN)
* Là ước chung lớn nhất của hai số.
* Thuật toán Euclid: 
```cpp
int gcd(int a, int b) {
    return b == 0 ? a : gcd(b, a % b);
}
```

#### 📌 LCM (Least Common Multiple – BCNN)
* Là bội chung nhỏ nhất của hai số.
* Tính bằng công thức: `lcm(a, b) = a * b // gcd(a, b)`

#### 📌 Phân tích số nguyên tố
* Tách một số thành tích các thừa số nguyên tố.
* Cách đơn giản:
```cpp
void prime_factors(int n) {
    for (int i = 2; i * i <= n; ++i) {
        while (n % i == 0) {
            cout << i << " ";
            n /= i;
        }
    }
    if (n > 1) cout << n;
}
```

---

### 3. **Ví dụ minh họa**

#### ✅ Ví dụ 1: GCD và LCM của 12 và 18
* GCD(12, 18) = 6  
* LCM(12, 18) = 36

#### ✅ Ví dụ 2: Phân tích 84
* 84 = 2 × 2 × 3 × 7

---

### 4. **5 bài LeetCode có hướng dẫn ngắn**

| STT | Tên bài                                   | Link                                                                                                   | Hướng dẫn tư duy                                                        |
| --- | ----------------------------------------- | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------ |
| 1   | Check If It Is a Straight Line            | https://leetcode.com/problems/check-if-it-is-a-straight-line/                                          | GCD để kiểm tra tỉ lệ độ dốc giữa các đoạn thẳng.                      |
| 2   | Find GCD of Array                         | https://leetcode.com/problems/find-greatest-common-divisor-of-array/                                   | Lặp GCD từng phần tử trong mảng.                                        |
| 3   | Ugly Number                               | https://leetcode.com/problems/ugly-number/                                                              | Phân tích thừa số nguyên tố: chỉ chấp nhận các thừa số 2, 3, 5.         |
| 4   | Greatest Common Divisor Traversal         | https://leetcode.com/problems/greatest-common-divisor-traversal/                                       | GCD và cấu trúc dữ liệu Union-Find dựa trên chia hết.                   |
| 5   | Smallest Integer Divisible by K           | https://leetcode.com/problems/smallest-integer-divisible-by-k/                                         | Tư duy chia hết, có thể áp dụng GCD để rút gọn và tối ưu hóa bước lặp. |

---

### 5. **5 bài tự luyện (không có hướng dẫn)**

| STT | Tên bài                            | Link                                                                 |
| --- | ---------------------------------- | -------------------------------------------------------------------- |
| 1   | Valid Palindrome II                | https://leetcode.com/problems/valid-palindrome-ii/                   |
| 2   | Happy Number                       | https://leetcode.com/problems/happy-number/                          |
| 3   | Count Primes                       | https://leetcode.com/problems/count-primes/                          |
| 4   | Power of Three                     | https://leetcode.com/problems/power-of-three/                        |
| 5   | Number of Good Pairs               | https://leetcode.com/problems/number-of-good-pairs/                  |

---

Bạn nên ưu tiên luyện kỹ các bài có hướng dẫn, sau đó thử sức với bài tự luyện. Đây là nền móng vững chắc trước khi học các chuyên đề sâu hơn như modulo, số nguyên tố nâng cao hay lý thuyết chia hết.

---

### 🔁 **Code mẫu C++ cho các thuật toán trong chuyên đề**

#### 📌 GCD – Thuật toán Euclid (C++)
```cpp
int gcd(int a, int b) {
    return b == 0 ? a : gcd(b, a % b);
}
```

#### 📌 LCM từ GCD (C++)
```cpp
int lcm(int a, int b) {
    return a / gcd(a, b) * b;
}
```

#### 📌 Phân tích số nguyên tố (C++)
```cpp
#include <iostream>
using namespace std;

void prime_factors(int n) {
    for (int i = 2; i * i <= n; ++i) {
        while (n % i == 0) {
            cout << i << " ";
            n /= i;
        }
    }
    if (n > 1) cout << n;
}
```
