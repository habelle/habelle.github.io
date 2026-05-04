---
layout: page
title: Tuần 6 - Mảng một chiều
permalink: /khoa-hoc/cpp/week-06/
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
<li><a class="active" href="/khoa-hoc/cpp/week-06/">Tuần 6<span class="week-topic">Mảng một chiều</span></a></li>
<li><a href="/khoa-hoc/cpp/week-07/">Tuần 7<span class="week-topic">Mảng hai chiều</span></a></li>
<li><a href="/khoa-hoc/cpp/week-08/">Tuần 8<span class="week-topic">Xâu ký tự</span></a></li>
  </ul>
</aside>

<main class="course-main" markdown="1">


<div class="course-progress">Tiến độ: Tuần 6 / 8</div>
<div class="course-topbar" markdown="1">
<div>⬅️ [Tuần trước](/khoa-hoc/cpp/week-05/)</div>
<div>[Trang khóa học](/khoa-hoc/cpp/)</div>
<div>[Tuần tiếp theo](/khoa-hoc/cpp/week-07/) ➡️</div>
</div>


# Tuần 6 - Mảng một chiều

👉 Hãy thử làm bài trước khi mở hint hoặc xem video chữa bài.

---

## Bài A: Đảo ngược dãy số

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/295380/problem/A)

<details>
<summary>Hint</summary>

Duyệt mảng từ cuối về đầu hoặc hoán đổi phần tử đối xứng.

</details>

[🎥 Video chữa bài](VIDEO_A_CHUA_BAI_URL)

---

## Bài B: Tính tổng dãy số

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/295380/problem/B)

<details>
<summary>Hint</summary>

Duyệt mảng và cộng dồn các phần tử.

</details>

[🎥 Video chữa bài](VIDEO_B_CHUA_BAI_URL)

---

## Bài C: Tổng số lẻ trong dãy số

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/295380/problem/C)

<details>
<summary>Hint</summary>

Chỉ cộng các phần tử không chia hết cho 2.

</details>

[🎥 Video chữa bài](VIDEO_C_CHUA_BAI_URL)

---

## Bài D: Thay thế số nguyên

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/295380/problem/D)

<details>
<summary>Hint</summary>

Duyệt mảng và thay đổi phần tử theo điều kiện đề bài.

</details>

[🎥 Video chữa bài](VIDEO_D_CHUA_BAI_URL)

---

## Bài E: Tìm phần tử lớn nhất trong mảng

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/295380/problem/E)

<details>
<summary>Hint</summary>

Khởi tạo max ban đầu, sau đó duyệt và cập nhật.

</details>

[🎥 Video chữa bài](VIDEO_E_CHUA_BAI_URL)

---

## Bài F: Vị trí số nhỏ hơn mười

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/295380/problem/F)

<details>
<summary>Hint</summary>

Duyệt mảng, nếu phần tử < 10 thì in vị trí.

</details>

[🎥 Video chữa bài](VIDEO_F_CHUA_BAI_URL)

---

## Bài G: Đảo vị trí đầu cuối dãy

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/295380/problem/G)

<details>
<summary>Hint</summary>

Hoán đổi phần tử đầu và cuối.

</details>

[🎥 Video chữa bài](VIDEO_G_CHUA_BAI_URL)

---

## Bài H: Đảo chỗ phần tử lớn nhất, bé nhất cho nhau

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/295380/problem/H)

<details>
<summary>Hint</summary>

Tìm vị trí max và min, sau đó hoán đổi.

</details>

[🎥 Video chữa bài](VIDEO_H_CHUA_BAI_URL)

---

## Bài I: Cặp liên kề có tổng lớn nhất

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/295380/problem/I)

<details>
<summary>Hint</summary>

Duyệt từng cặp i và i+1, tính tổng và tìm giá trị lớn nhất.

</details>

[🎥 Video chữa bài](VIDEO_I_CHUA_BAI_URL)

---

## Bài J: Chèn X

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/295380/problem/J)

<details>
<summary>Hint</summary>

Dịch các phần tử sang phải rồi chèn X vào vị trí yêu cầu.

</details>

[🎥 Video chữa bài](VIDEO_J_CHUA_BAI_URL)

---

## Bài K: Xóa X

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/295380/problem/K)

<details>
<summary>Hint</summary>

Dịch các phần tử sang trái để xóa phần tử cần loại bỏ.

</details>

[🎥 Video chữa bài](VIDEO_K_CHUA_BAI_URL)

---

## Bài L: Đổi số thập phân sang số nhị phân

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/295380/problem/L)

<details>
<summary>Hint</summary>

Dùng chia 2 liên tiếp và lưu phần dư vào mảng.

</details>

[🎥 Video chữa bài](VIDEO_L_CHUA_BAI_URL)

---

## Bài M: Tìm kiếm tuần tự

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/295380/problem/M)

<details>
<summary>Hint</summary>

Duyệt mảng từ đầu đến cuối để tìm phần tử.

</details>

[🎥 Video chữa bài](VIDEO_M_CHUA_BAI_URL)

---

## Bài N: Thuật toán sắp xếp chọn

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/295380/problem/N)

<details>
<summary>Hint</summary>

Mỗi bước chọn phần tử nhỏ nhất và đưa về đầu.

</details>

[🎥 Video chữa bài](VIDEO_N_CHUA_BAI_URL)

---

## Bài O: Số nhỏ nhì

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/295380/problem/O)

<details>
<summary>Hint</summary>

Theo dõi hai giá trị nhỏ nhất khi duyệt mảng.

</details>

[🎥 Video chữa bài](VIDEO_O_CHUA_BAI_URL)

---


<div class="course-progress">Tiến độ: Tuần 6 / 8</div>
<div class="course-topbar" markdown="1">
<div>⬅️ [Tuần trước](/khoa-hoc/cpp/week-05/)</div>
<div>[Trang khóa học](/khoa-hoc/cpp/)</div>
<div>[Tuần tiếp theo](/khoa-hoc/cpp/week-07/) ➡️</div>
</div>


</main>
</div>
