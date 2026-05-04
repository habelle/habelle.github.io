---
layout: page
title: Tuần 7 - Mảng hai chiều
permalink: /khoa-hoc/cpp/week-07/
---


<style>
.course-shell {
  display: grid;
  grid-template-columns: 270px minmax(0, 1fr);
  gap: 28px;
  align-items: start;
}
.course-sidebar {
  position: sticky;
  top: 18px;
  border: 1px solid #e5e7eb;
  border-radius: 16px;
  background: #ffffff;
  box-shadow: 0 8px 24px rgba(15, 23, 42, 0.08);
  overflow: hidden;
}
.course-sidebar-header {
  padding: 16px 18px;
  background: #111827;
  color: #ffffff;
}
.course-sidebar-header .course-title {
  font-weight: 700;
  font-size: 16px;
  line-height: 1.35;
}
.course-sidebar-header .course-subtitle {
  margin-top: 4px;
  font-size: 13px;
  color: #d1d5db;
}
.course-week-list {
  margin: 0;
  padding: 8px;
  list-style: none;
}
.course-week-list li {
  margin: 4px 0;
}
.course-week-list a {
  display: block;
  padding: 10px 12px;
  border-radius: 10px;
  text-decoration: none;
  color: #374151;
  font-size: 14px;
  line-height: 1.35;
}
.course-week-list a:hover {
  background: #f3f4f6;
}
.course-week-list a.active {
  background: #2563eb;
  color: #ffffff;
  font-weight: 700;
}
.course-week-list .week-topic {
  display: block;
  font-size: 12px;
  opacity: 0.85;
  margin-top: 2px;
}
.course-main {
  min-width: 0;
}
.course-topbar {
  display: flex;
  justify-content: space-between;
  gap: 12px;
  margin: 12px 0 24px;
  padding: 12px 14px;
  border: 1px solid #e5e7eb;
  border-radius: 14px;
  background: #f9fafb;
}
.course-topbar a {
  text-decoration: none;
  font-weight: 600;
}
.course-progress {
  font-size: 14px;
  color: #4b5563;
  margin-bottom: 12px;
}
@media (max-width: 860px) {
  .course-shell {
    display: block;
  }
  .course-sidebar {
    position: relative;
    top: auto;
    margin-bottom: 22px;
  }
  .course-week-list {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
  }
}
</style>


<div class="course-shell">
<aside class="course-sidebar">
  <div class="course-sidebar-header">
    <div class="course-title">Khóa C++ cơ bản</div>
    <div class="course-subtitle">Lộ trình 8 tuần</div>
  </div>
  <ul class="course-week-list">
    <li><a href="/khoa-hoc/cpp/week-01/">Tuần 1<span class="week-topic">Bài tập cơ bản</span></a></li>
<li><a href="/khoa-hoc/cpp/week-02/">Tuần 2<span class="week-topic">Rẽ nhánh và điều kiện</span></a></li>
<li><a href="/khoa-hoc/cpp/week-03/">Tuần 3<span class="week-topic">Vòng lặp phần 1</span></a></li>
<li><a href="/khoa-hoc/cpp/week-04/">Tuần 4<span class="week-topic">Xử lý chữ số</span></a></li>
<li><a href="/khoa-hoc/cpp/week-05/">Tuần 5<span class="week-topic">Vòng lặp lồng nhau</span></a></li>
<li><a href="/khoa-hoc/cpp/week-06/">Tuần 6<span class="week-topic">Mảng một chiều</span></a></li>
<li><a class="active" href="/khoa-hoc/cpp/week-07/">Tuần 7<span class="week-topic">Mảng hai chiều</span></a></li>
<li><a href="/khoa-hoc/cpp/week-08/">Tuần 8<span class="week-topic">Xâu ký tự</span></a></li>
  </ul>
</aside>

<main class="course-main" markdown="1">


<div class="course-progress">Tiến độ: Tuần 7 / 8</div>


# Tuần 7 - Mảng hai chiều

👉 Hãy thử làm bài trước khi mở hint hoặc xem video chữa bài.

---

## Bài A: Nhập, xuất mảng hai chiều

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/295541/problem/A)

<details>
<summary>Hint</summary>

Dùng hai vòng lặp lồng nhau để nhập và xuất từng phần tử của mảng.

</details>

[🎥 Video chữa bài](VIDEO_A_CHUA_BAI_URL)

---

## Bài B: Bảng nhân N

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/295541/problem/B)

<details>
<summary>Hint</summary>

Phần tử ở hàng i, cột j có thể tính từ tích của i và j.

</details>

[🎥 Video chữa bài](VIDEO_B_CHUA_BAI_URL)

---

## Bài C: Tổng thành phần ma trận

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/295541/problem/C)

<details>
<summary>Hint</summary>

Duyệt toàn bộ ma trận và cộng dồn các phần tử.

</details>

[🎥 Video chữa bài](VIDEO_C_CHUA_BAI_URL)

---

## Bài D: Tổng phần tử đường chéo chính

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/295541/problem/D)

<details>
<summary>Hint</summary>

Trong ma trận vuông, phần tử trên đường chéo chính có chỉ số hàng bằng chỉ số cột.

</details>

[🎥 Video chữa bài](VIDEO_D_CHUA_BAI_URL)

---

## Bài E: Tổng đường chéo phụ của ma trận vuông

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/295541/problem/E)

<details>
<summary>Hint</summary>

Với ma trận vuông kích thước n, phần tử thuộc đường chéo phụ khi tổng chỉ số hàng và cột bằng n + 1 nếu đánh số từ 1.

</details>

[🎥 Video chữa bài](VIDEO_E_CHUA_BAI_URL)

---

## Bài F: Tráo đổi đường chéo chính, phụ

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/295541/problem/F)

<details>
<summary>Hint</summary>

Duyệt từng dòng i, đổi phần tử trên đường chéo chính với phần tử tương ứng trên đường chéo phụ.

</details>

[🎥 Video chữa bài](VIDEO_F_CHUA_BAI_URL)

---

## Bài G: Ma trận tam giác trên

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/295541/problem/G)

<details>
<summary>Hint</summary>

Quan sát các phần tử nằm dưới đường chéo chính. Với ma trận tam giác trên, các phần tử đó thường phải bằng 0.

</details>

[🎥 Video chữa bài](VIDEO_G_CHUA_BAI_URL)

---

## Bài H: Ma trận tam giác dưới

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/295541/problem/H)

<details>
<summary>Hint</summary>

Quan sát các phần tử nằm trên đường chéo chính. Với ma trận tam giác dưới, các phần tử đó thường phải bằng 0.

</details>

[🎥 Video chữa bài](VIDEO_H_CHUA_BAI_URL)

---

## Bài I: Nhân một số với ma trận

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/295541/problem/I)

<details>
<summary>Hint</summary>

Duyệt từng phần tử và nhân nó với số đã cho.

</details>

[🎥 Video chữa bài](VIDEO_I_CHUA_BAI_URL)

---

## Bài J: Cộng hai ma trận

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/295541/problem/J)

<details>
<summary>Hint</summary>

Hai ma trận cùng kích thước được cộng bằng cách cộng từng cặp phần tử cùng vị trí.

</details>

[🎥 Video chữa bài](VIDEO_J_CHUA_BAI_URL)

---

## Bài K: Nhân hai ma trận

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/295541/problem/K)

<details>
<summary>Hint</summary>

Phần tử kết quả tại hàng i, cột j bằng tổng các tích giữa hàng i của ma trận thứ nhất và cột j của ma trận thứ hai.

</details>

[🎥 Video chữa bài](VIDEO_K_CHUA_BAI_URL)

---

## Bài L: Ma trận đẹp

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/295541/problem/L)

<details>
<summary>Hint</summary>

Đọc kỹ điều kiện để một ma trận được gọi là đẹp, sau đó duyệt các phần tử cần kiểm tra.

</details>

[🎥 Video chữa bài](VIDEO_L_CHUA_BAI_URL)

---

## Bài M: Tic Tac Toe - version1

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/295541/problem/M)

<details>
<summary>Hint</summary>

Kiểm tra các hàng, các cột và hai đường chéo để xác định trạng thái thắng.

</details>

[🎥 Video chữa bài](VIDEO_M_CHUA_BAI_URL)

---

## Bài N: Kiểm tra ma trận đơn vị

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/295541/problem/N)

<details>
<summary>Hint</summary>

Ma trận đơn vị có các phần tử trên đường chéo chính bằng 1 và các phần tử còn lại bằng 0.

</details>

[🎥 Video chữa bài](VIDEO_N_CHUA_BAI_URL)

---


<div class="course-progress">Tiến độ: Tuần 7 / 8</div>

</main>
</div>
