---
layout: post
title: "Chiến lược thiết kế thuật toán tham lam"
subtitle: "Hiểu rõ mô hình thiết kế thuật toán tham lam để có thể vận dụng hiệu quả"
tags: [Greedy]
author: Hoàng Hà
---

# Chuyên đề: Phương pháp thiết kế thuật toán Tham lam (Greedy Algorithm)

## I. Giới thiệu chung

Thuật toán tham lam (Greedy Algorithm) là một phương pháp thiết kế thuật toán dựa trên nguyên lý lựa chọn tối ưu cục bộ tại mỗi bước với hy vọng rằng lựa chọn này sẽ dẫn đến kết quả tối ưu toàn cục.

### Khi nào nên sử dụng thuật toán tham lam:
- Bài toán có thể phân rã thành các bước con mà mỗi bước có thể chọn tối ưu cục bộ.
- Thỏa mãn tính chất con con tối ưu (Optimal Substructure).
- Không yêu cầu xét lại quyết định đã chọn (tức không cần backtrack).

## II. Mô hình giải thuật tham lam

Thông thường, để giải bài toán bằng thuật toán tham lam, cần:
1. **Xác định mô hình bài toán** (tập hợp các đối tượng và tiêu chí chọn).
2. **Xây dựng hàm so sánh thứ tự lựa chọn**.
3. **Chứng minh chiến lược tham lam là đúng** (thường bằng phản chứng hoặc bất đẳng thức).
4. **Cài đặt và kiểm tra nghiệm đúng với test mẫu và biên.**

---

## III. Bài toán mẫu 1: Hoạt động không chồng chéo (Interval Scheduling)

### Link bài gốc:
https://cses.fi/problemset/task/1630/

### Đề bài (dịch tiếng Việt):
Cho \( n \) hoạt động, mỗi hoạt động \( i \) có thời điểm bắt đầu \( s_i \) và thời điểm kết thúc \( e_i \). Hãy chọn nhiều nhất số lượng hoạt động mà không có hai hoạt động nào trùng thời gian.

### Input:
- Dòng đầu chứa số nguyên \( n \) \( (1 \leq n \leq 2 \cdot 10^5) \).
- \( n \) dòng tiếp theo mỗi dòng chứa hai số nguyên \( s_i, e_i \) \( (0 \leq s_i < e_i \leq 10^9) \).

### Output:
- Số lượng hoạt động có thể chọn.

### Định hướng thuật toán:
- Sắp xếp các hoạt động theo thời gian kết thúc tăng dần.
- Duyệt từ đầu đến cuối, chọn hoạt động tiếp theo nếu nó bắt đầu sau thời điểm kết thúc của hoạt động trước.

### Độ phức tạp:
- \( O(n \log n) \) do thao tác sắp xếp ban đầu.

### Code C++:
```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    int n; cin >> n;
    vector<pair<int, int>> a(n);
    for (int i = 0; i < n; ++i) cin >> a[i].second >> a[i].first;
    sort(a.begin(), a.end());

    int res = 0, last_end = 0;
    for (auto [end, start] : a) {
        if (start >= last_end) {
            ++res;
            last_end = end;
        }
    }
    cout << res << '\n';
}
```

---

## IV. Bài toán mẫu 2: Đổi tiền (Coin Change - Minimum Number of Coins)

### Link bài gốc:
https://cses.fi/problemset/task/1620/

### Đề bài (dịch tiếng Việt):
Cho \( n \) loại tiền có giá trị \( c_1, c_2, ..., c_n \) và số tiền \( x \). Hãy tìm số lượng ít nhất đồng xu cần để tạo thành số tiền \( x \) (có thể dùng không giới hạn mỗi loại).

### Input:
- Dòng đầu chứa hai số nguyên \( n, x \) \( (1 \le n \le 100, 1 \le x \le 10^6) \).
- Dòng thứ hai chứa \( n \) số nguyên \( c_i \) \( (1 \le c_i \le 10^6) \).

### Output:
- Một số nguyên là số lượng đồng xu tối thiểu, hoặc \( -1 \) nếu không thể tạo thành số tiền đó.

### Định hướng thuật toán:
- Nếu **hệ thống tiền tệ chuẩn (ví dụ: 1, 5, 10, 25...)** thì tham lam sẽ đúng: luôn chọn đồng xu lớn nhất nhỏ hơn số tiền còn lại.
- Tuy nhiên, trong nhiều trường hợp tổng quát, phải dùng Quy hoạch động.

### Độ phức tạp:
- Nếu dùng tham lam: \( O(n \log n) \) mỗi lần chọn, tổng số đồng xu phụ thuộc vào \( x \).
- Tuy nhiên, nếu bài toán không thỏa mãn tính chất tham lam → cần dùng DP với \( O(n \cdot x) \).

### Code C++ (dùng tham lam nếu hệ chuẩn):
```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    int n, x; cin >> n >> x;
    vector<int> c(n);
    for (int &v : c) cin >> v;
    sort(c.rbegin(), c.rend());

    int res = 0;
    for (int coin : c) {
        if (x >= coin) {
            res += x / coin;
            x %= coin;
        }
    }
    if (x > 0) cout << "-1\n";
    else cout << res << "\n";
}
```

---

## V. Một số lưu ý khi sử dụng thuật toán tham lam:

- Cần chứng minh chiến lược chọn là tối ưu. Không phải bài nào cũng áp dụng được.
- Không nên dùng tham lam nếu bài toán có các trạng thái phụ thuộc nhau hoặc cần thử nhiều hướng.
- Một số bài có thể kết hợp tham lam với cấu trúc dữ liệu như heap, multiset, priority queue.

---

## VI. 5 bài tập vận dụng

### 1. [Job Scheduling with Deadlines](https://www.geeksforgeeks.org/job-sequencing-problem/)
- **Đề:** Có \( n \) công việc, mỗi công việc có deadline và lợi nhuận. Mỗi việc cần 1 đơn vị thời gian. Lên lịch sao cho lợi nhuận lớn nhất.
- **Gợi ý:** Sắp xếp theo lợi nhuận giảm dần, dùng mảng để đánh dấu slot thời gian.

### 2. [Minimum Platforms](https://practice.geeksforgeeks.org/problems/minimum-platforms-1587115620/1)
- **Đề:** Cho thời gian đến và đi của các tàu, tính số lượng sân ga tối thiểu cần thiết.
- **Gợi ý:** Duyệt theo mốc thời gian, tăng hoặc giảm đếm.

### 3. [Activity Selection](https://www.geeksforgeeks.org/activity-selection-problem/)
- **Đề:** Chọn số lượng tối đa các hoạt động không trùng thời gian.
- **Gợi ý:** Chính là bài mẫu 1.

### 4. [Huffman Coding](https://www.geeksforgeeks.org/huffman-coding-greedy-algo-3/)
- **Đề:** Mã hóa dữ liệu với tần suất ký tự để giảm tổng độ dài mã hóa.
- **Gợi ý:** Dùng priority queue tạo cây Huffman.

### 5. [Fractional Knapsack](https://www.geeksforgeeks.org/fractional-knapsack-problem/)
- **Đề:** Cho các vật phẩm có trọng lượng và giá trị, chọn một phần của vật phẩm để tối ưu giá trị trong khi không vượt quá sức chứa.
- **Gợi ý:** Sắp xếp theo tỉ lệ value/weight giảm dần, duyệt từ trên xuống.

---

**Tài liệu này phù hợp cho học sinh luyện thuật toán ở mức cơ bản - trung bình. Các bài nâng cao hơn có thể yêu cầu kết hợp greedy với cấu trúc dữ liệu hoặc tối ưu hóa tìm kiếm.**
