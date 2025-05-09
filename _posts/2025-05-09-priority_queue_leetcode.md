---
layout: post
title: Cấu trúc dữ liệu Priority Queue
subtitle: Cấu trúc dữ liệu Priority Queue và bài tập ứng dụng trên LeetCode
tags: [Priority Queue]
author: Hoàng Hà
---


## 1. Giới thiệu Priority Queue

### ✅ Khái niệm:
- **Priority Queue (PQ)** là hàng đợi mà phần tử có độ ưu tiên cao nhất được lấy ra trước (không theo thứ tự nhập vào).
- Thường hiện thực bằng **Heap**: 
  - Max Heap (phần tử lớn nhất ưu tiên)
  - Min Heap (phần tử nhỏ nhất ưu tiên)

### ✅ Ứng dụng:
- Lập lịch tiến trình
- Dijkstra, Prim trên đồ thị
- Giữ K phần tử lớn nhất / nhỏ nhất
- Xử lý dòng công việc có độ ưu tiên

### ✅ Cú pháp:

**C++**
```cpp
priority_queue<int> maxPQ;
priority_queue<int, vector<int>, greater<int>> minPQ;
```

**Python**
```python
import heapq
pq = []
heapq.heappush(pq, x)
x = heapq.heappop(pq)
```

---

## 2. 10 Bài tập LeetCode sử dụng Priority Queue

| STT | Bài toán | ID | Mức độ | Mô tả |
|-----|----------|----|--------|-------|
| 1 | [Kth Largest Element in a Stream](https://leetcode.com/problems/kth-largest-element-in-a-stream/) | 703 | Easy | Giữ K phần tử lớn nhất |
| 2 | [Last Stone Weight](https://leetcode.com/problems/last-stone-weight/) | 1046 | Easy | Max heap để phá đá lớn nhất |
| 3 | [Top K Frequent Elements](https://leetcode.com/problems/top-k-frequent-elements/) | 347 | Medium | Tần suất → dùng min heap |
| 4 | [K Closest Points to Origin](https://leetcode.com/problems/k-closest-points-to-origin/) | 973 | Medium | Tính khoảng cách và chọn K điểm gần nhất |
| 5 | [Merge K Sorted Lists](https://leetcode.com/problems/merge-k-sorted-lists/) | 23 | Hard | Gộp nhiều danh sách có thứ tự |
| 6 | [Task Scheduler](https://leetcode.com/problems/task-scheduler/) | 621 | Medium | Ưu tiên task có tần suất cao |
| 7 | [Find Median from Data Stream](https://leetcode.com/problems/find-median-from-data-stream/) | 295 | Hard | Dùng 2 heap để tìm median |
| 8 | [Minimum Cost to Connect Sticks](https://leetcode.com/problems/minimum-cost-to-connect-sticks/) | 1167 | Medium | Quy tắc giống bài Huffman |
| 9 | [Reorganize String](https://leetcode.com/problems/reorganize-string/) | 767 | Medium | Ưu tiên ký tự xuất hiện nhiều |
| 10 | [Swim in Rising Water](https://leetcode.com/problems/swim-in-rising-water/) | 778 | Hard | Dijkstra dùng min heap trên lưới |

---

## 3. Phân tích mẫu: Bài 347 – Top K Frequent Elements

### Đề bài:
Cho mảng `nums` và số nguyên `k`, trả về `k` phần tử xuất hiện nhiều nhất.

### Ý tưởng:
- Dùng `unordered_map` để đếm tần suất.
- Dùng min heap để giữ top K phần tử tần suất cao nhất.

### C++ Code:
```cpp
vector<int> topKFrequent(vector<int>& nums, int k) {
    unordered_map<int, int> freq;
    for (int num : nums) freq[num]++;
    
    priority_queue<pair<int, int>, vector<pair<int, int>>, greater<>> pq;
    for (auto [num, f] : freq) {
        pq.push({f, num});
        if (pq.size() > k) pq.pop();
    }
    
    vector<int> res;
    while (!pq.empty()) {
        res.push_back(pq.top().second);
        pq.pop();
    }
    return res;
}
```

### Độ phức tạp:
- O(n log k) nếu số phần tử khác nhau là n

---

## 4. Tổng kết

| Tình huống | Chiến lược sử dụng Priority Queue |
|------------|----------------------------------|
| Giữ top-K nhỏ nhất | Dùng min heap với size K |
| Gộp luồng dữ liệu | Min heap lấy phần tử nhỏ nhất |
| Ưu tiên xử lý nhanh nhất | Max heap với tần suất/cấp độ |
| Phân vùng / theo dõi trung vị | Dùng 2 heap: max + min heap |

---

Bạn có thể áp dụng PQ trong nhiều bài toán sắp xếp động, greedy, và xử lý ưu tiên!