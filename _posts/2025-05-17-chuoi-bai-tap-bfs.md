---
layout: post
title: "Chuỗi bài tập BFS – Phát triển tư duy từ cơ bản đến vận dụng"
subtitle: "6 bài học kèm link bài LeetCode, CSES giúp học sinh rèn chắc kỹ thuật BFS"
tags: [BFS, Duyệt đồ thị, Phương pháp dạy học, CSES, LeetCode]
author: Hoàng Hà
---

## 📘 Giới thiệu

BFS (Breadth-First Search) là kỹ thuật duyệt đồ thị theo chiều rộng, rất hiệu quả trong việc tìm đường đi ngắn nhất, kiểm tra tính liên thông, duyệt theo lớp,... Đặc biệt, BFS được ứng dụng rất nhiều trong các bài toán về **đường đi, mê cung, trò chơi, lưới 2 chiều**.

Chuỗi bài tập sau được thiết kế theo các **nguyên tắc sư phạm hiện đại**, giúp học sinh phát triển tư duy từng bước và áp dụng vào nhiều dạng đề thực tế.

---

## 🔢 Danh sách chuỗi bài tập BFS

### 1. **Duyệt theo BFS từ một đỉnh – `bfs_basic.cpp`**  
Cho đồ thị vô hướng. Bắt đầu từ đỉnh `u`, in thứ tự các đỉnh được duyệt theo BFS.

🔗 Bài tương tự: [CSES – Counting Rooms](https://cses.fi/problemset/task/1192)

---

### 2. **Tìm đường đi ngắn nhất từ một đỉnh – `shortest_path.cpp`**  
Tính khoảng cách ngắn nhất (số bước) từ đỉnh `u` đến mọi đỉnh còn lại.

🔗 Bài tương tự: [CSES – Shortest Routes I](https://cses.fi/problemset/task/1671) *(dùng Dijkstra, nhưng BFS nếu trọng số = 1)*  
Hoặc: [LeetCode 1091 – Shortest Path in Binary Matrix](https://leetcode.com/problems/shortest-path-in-binary-matrix/)

---

### 3. **Tìm đường đi từ A đến B trong mê cung – `maze_path.cpp`**  
Cho mê cung dạng lưới, di chuyển 4 hướng. Tìm đường ngắn nhất từ A → B.

🔗 Bài tương tự: [CSES – Labyrinth](https://cses.fi/problemset/task/1193)

---

### 4. **Tô màu theo lớp BFS – `color_bfs.cpp`**  
Tô 2 màu xen kẽ sao cho không có 2 đỉnh kề nhau cùng màu.

🔗 Bài tương tự: [CSES – Building Teams](https://cses.fi/problemset/task/1668)

---

### 5. **Số bước ngắn nhất để chuyển trạng thái – `min_steps.cpp`**  
Từ trạng thái `S`, mỗi bước thực hiện một phép biến đổi (quy định). Tìm số bước ít nhất để đến trạng thái `T`.

🔗 Bài tương tự: [LeetCode 752 – Open the Lock](https://leetcode.com/problems/open-the-lock/)

---

### 6. **Số lượng bước xa nhất từ một điểm – `farthest.cpp`**  
Tìm đỉnh xa nhất (tính theo số bước BFS) từ đỉnh xuất phát `u`.

🔗 Bài tương tự: [CSES – Message Route](https://cses.fi/problemset/task/1667)

---

## 🧠 Vì sao chuỗi bài này hiệu quả?

| Nguyên tắc                     | Áp dụng trong chuỗi BFS                                      |
|-------------------------------|---------------------------------------------------------------|
| Từ dễ đến khó                 | Từ duyệt cơ bản → đường đi ngắn nhất → bài biến trạng thái   |
| Xoắn ốc – mở rộng dần         | Mỗi bài xây trên tư duy BFS, nhưng thêm logic/phản xạ mới    |
| Phân hóa – nhiều mức nhận thức| Có bài nhập môn (1–2), suy luận (3–4), ứng dụng (5–6)         |
| Mục tiêu rõ ràng              | Mỗi bài rèn một mục tiêu: duyệt, tìm đường, tô màu, BFS trên trạng thái |
| Phản hồi dễ kiểm tra          | Output cụ thể: đường đi, số bước, danh sách đỉnh, YES/NO     |
| Gắn thực tế                   | Bài mê cung, trạng thái khóa số gần gũi và sinh động         |

---

## ✍️ Gợi ý khi dạy học

- Cho học sinh chạy tay ví dụ BFS với hàng đợi `queue`
- So sánh BFS với DFS trong từng bài để phân biệt bản chất
- Mở rộng BFS trên lưới 2D và trên không gian trạng thái
- Tập cho học sinh tư duy mô hình hóa bài toán về “trạng thái” để áp dụng BFS

---

Bạn muốn mình soạn chi tiết từng đề, tạo bộ test chấm offline hoặc bài Word/PDF? Hãy để lại yêu cầu, mình sẽ hỗ trợ đầy đủ!
