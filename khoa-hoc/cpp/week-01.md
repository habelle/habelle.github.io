---
layout: page
title: Tuần 1 - Bài tập cơ bản
permalink: /khoa-hoc/cpp/week-01/
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
    <li><a class="active" href="/khoa-hoc/cpp/week-01/">Tuần 1<span class="week-topic">Bài tập cơ bản</span></a></li>
<li><a href="/khoa-hoc/cpp/week-02/">Tuần 2<span class="week-topic">Rẽ nhánh và điều kiện</span></a></li>
<li><a href="/khoa-hoc/cpp/week-03/">Tuần 3<span class="week-topic">Vòng lặp phần 1</span></a></li>
<li><a href="/khoa-hoc/cpp/week-04/">Tuần 4<span class="week-topic">Xử lý chữ số</span></a></li>
<li><a href="/khoa-hoc/cpp/week-05/">Tuần 5<span class="week-topic">Vòng lặp lồng nhau</span></a></li>
<li><a href="/khoa-hoc/cpp/week-06/">Tuần 6<span class="week-topic">Mảng một chiều</span></a></li>
<li><a href="/khoa-hoc/cpp/week-07/">Tuần 7<span class="week-topic">Mảng hai chiều</span></a></li>
<li><a href="/khoa-hoc/cpp/week-08/">Tuần 8<span class="week-topic">Xâu ký tự</span></a></li>
  </ul>
</aside>

<main class="course-main" markdown="1">


<div class="course-progress">Tiến độ: Tuần 1 / 8</div>

# Tuần 1 - Bài tập cơ bản

👉 Hãy thử làm bài trước khi mở hint hoặc xem video chữa bài.

---

## Bài A: Tổng A+B

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/294687/problem/A)

<details>
<summary>Hint</summary>

Nhập hai số và in ra tổng của chúng.

</details>

[🎥 Video chữa bài](VIDEO_A_CHUA_BAI_URL)

---

## Bài B: Tính toán cơ bản

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/294687/problem/B)

<details>
<summary>Hint</summary>

Sử dụng các phép toán cộng, trừ, nhân, chia theo yêu cầu đề bài.

</details>

[🎥 Video chữa bài](VIDEO_B_CHUA_BAI_URL)

---

## Bài C: Hình chữ nhật

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/294687/problem/C)

<details>
<summary>Hint</summary>

Chu vi = 2 × (dài + rộng)  
Diện tích = dài × rộng  

</details>

[🎥 Video chữa bài](VIDEO_C_CHUA_BAI_URL)

---

## Bài D: Đường tròn

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/294687/problem/D)

<details>
<summary>Hint</summary>

Chu vi = 2 × pi × r  
Diện tích = pi × r × r  

</details>

[🎥 Video chữa bài](VIDEO_D_CHUA_BAI_URL)

---

## Bài E: Độ dài

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/294687/problem/E)

<details>
<summary>Hint</summary>

Xác định đơn vị đầu vào và đơn vị cần đổi, sau đó viết công thức chuyển đổi.

</details>

[🎥 Video chữa bài](VIDEO_E_CHUA_BAI_URL)

---

## Bài F: Độ C sang độ F

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/294687/problem/F)

<details>
<summary>Hint</summary>

F = C × 9 / 5 + 32  

</details>

[🎥 Video chữa bài](VIDEO_F_CHUA_BAI_URL)

---

## Bài G: Độ F sang độ C

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/294687/problem/G)

<details>
<summary>Hint</summary>

C = (F − 32) × 5 / 9  

</details>

[🎥 Video chữa bài](VIDEO_G_CHUA_BAI_URL)

---

## Bài O: Two Numbers

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/294687/problem/O)

<details>
<summary>Hint</summary>

Đọc kỹ yêu cầu và thực hiện phép toán tương ứng với hai số đầu vào.

</details>

[🎥 Video chữa bài](VIDEO_O_CHUA_BAI_URL)

---


<div class="course-progress">Tiến độ: Tuần 1 / 8</div>


</main>
</div>
