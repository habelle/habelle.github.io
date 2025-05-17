---
layout: post
title: "Chuỗi bài tập DFS – Tư duy và vận dụng hiện đại"
subtitle: "6 bài học theo lộ trình sư phạm hiện đại, có link bài tập LeetCode và CSES"
tags: [DFS, Duyệt đồ thị, Phương pháp dạy học, CSES, LeetCode]
author: Hoàng Hà
---

## 📘 Giới thiệu

DFS (Depth-First Search) là một trong những kỹ thuật nền tảng khi học cấu trúc dữ liệu và thuật toán. Tuy nhiên, nhiều giáo viên khi dạy DFS thường chỉ dừng lại ở ví dụ đơn giản và thiếu lộ trình phát triển tư duy. Bài viết này giới thiệu chuỗi 6 bài tập DFS được thiết kế theo **nguyên tắc sư phạm hiện đại**, giúp học sinh:

- Hiểu bản chất DFS qua nhiều bối cảnh
- Tăng dần độ khó từ thao tác đến logic
- Phát triển tư duy phân tích và ứng dụng
- Có cơ hội luyện tập trên các nền tảng uy tín như CSES, LeetCode

---

## 🔢 Danh sách chuỗi bài tập DFS

### 1. **In dãy số duyệt bằng DFS – `dfs_basic.cpp`**  
Nhập đồ thị vô hướng `n` đỉnh `m` cạnh. In thứ tự duyệt DFS từ đỉnh `u`.

🔗 Bài tương tự: [CSES – Counting Rooms](https://cses.fi/problemset/task/1192)

---

### 2. **Đếm số thành phần liên thông – `count_cc.cpp`**  
Cho đồ thị vô hướng. Hỏi có bao nhiêu thành phần liên thông.

🔗 Bài tương tự: [CSES – Building Roads](https://cses.fi/problemset/task/1666)

---

### 3. **Kiểm tra chu trình – `cycle_check.cpp`**  
Kiểm tra xem đồ thị vô hướng có tồn tại chu trình không.

🔗 Bài tương tự: [LeetCode – Graph Valid Tree](https://leetcode.com/problems/graph-valid-tree/)

---

### 4. **Duyệt mê cung bằng DFS – `maze_dfs.cpp`**  
Tìm đường đi từ A → B trong mê cung dạng lưới.

🔗 Bài tương tự: [CSES – Labyrinth](https://cses.fi/problemset/task/1193)

---

### 5. **Liệt kê các thành phần liên thông – `list_cc.cpp`**  
In ra từng thành phần liên thông dưới dạng danh sách đỉnh.

🔗 Bài tương tự: [Codeforces EDU – Connected Components](https://codeforces.com/edu/course/2/lesson/5/1/practice/contest/279634/problem/A)

---

### 6. **Tô màu đồ thị bằng DFS – `coloring_dfs.cpp`**  
Tô hai màu sao cho không có hai đỉnh kề nhau cùng màu (kiểm tra đồ thị hai màu).

🔗 Bài tương tự: [CSES – Building Teams](https://cses.fi/problemset/task/1668)

---

## 🧠 Vì sao chuỗi bài này hiệu quả?

| Nguyên tắc                     | Áp dụng trong chuỗi DFS                                      |
|-------------------------------|---------------------------------------------------------------|
| Từ dễ đến khó                 | Bài 1 in thứ tự → Bài 6 kiểm tra tô màu                      |
| Xoắn ốc – mở rộng dần         | Mỗi bài tái sử dụng DFS, mở rộng logic và ứng dụng           |
| Phân hóa – nhiều mức nhận thức| Có bài cơ bản, bài suy luận logic, bài ứng dụng thực tế      |
| Mục tiêu rõ ràng              | Mỗi bài rèn một kỹ thuật: duyệt, đếm, kiểm tra, lưu tập hợp  |
| Phản hồi dễ kiểm tra          | Output rõ ràng, dễ viết test: số lượng, danh sách, YES/NO    |
| Gắn thực tế                   | Bài mê cung, tô màu dễ hình dung, có thể minh họa bằng hình  |

---

## ✍️ Lời khuyên khi dạy

- Với mỗi bài, nên cho học sinh **vẽ tay đồ thị/mê cung**, mô phỏng DFS trước khi code.
- Khuyến khích học sinh **viết DFS theo cả đệ quy và stack**.
- Dùng hệ thống chấm tự động và luyện tập độc lập.


