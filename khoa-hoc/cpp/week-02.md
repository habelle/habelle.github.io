---
layout: page
title: Tuần 2 - Bài tập rẽ nhánh và xử lý điều kiện
permalink: /khoa-hoc/cpp/week-02/
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
<li><a class="active" href="/khoa-hoc/cpp/week-02/">Tuần 2<span class="week-topic">Rẽ nhánh và điều kiện</span></a></li>
<li><a href="/khoa-hoc/cpp/week-03/">Tuần 3<span class="week-topic">Vòng lặp phần 1</span></a></li>
<li><a href="/khoa-hoc/cpp/week-04/">Tuần 4<span class="week-topic">Xử lý chữ số</span></a></li>
<li><a href="/khoa-hoc/cpp/week-05/">Tuần 5<span class="week-topic">Vòng lặp lồng nhau</span></a></li>
<li><a href="/khoa-hoc/cpp/week-06/">Tuần 6<span class="week-topic">Mảng một chiều</span></a></li>
<li><a href="/khoa-hoc/cpp/week-07/">Tuần 7<span class="week-topic">Mảng hai chiều</span></a></li>
<li><a href="/khoa-hoc/cpp/week-08/">Tuần 8<span class="week-topic">Xâu ký tự</span></a></li>
  </ul>
</aside>

<main class="course-main" markdown="1">


<div class="course-progress">Tiến độ: Tuần 2 / 8</div>
<div class="course-topbar" markdown="1">
<div>⬅️ [Tuần trước](/khoa-hoc/cpp/week-01/)</div>
<div>[Trang khóa học](/khoa-hoc/cpp/)</div>
<div>[Tuần tiếp theo](/khoa-hoc/cpp/week-03/) ➡️</div>
</div>


# Tuần 2 - Bài tập rẽ nhánh và xử lý điều kiện

👉 Hãy thử làm bài trước khi mở hint hoặc xem video chữa bài.

---

## Bài A: Tìm max 2 số

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/294730/problem/A)

<details>
<summary>Hint</summary>

So sánh hai số và in ra số lớn hơn.

</details>

[🎥 Video chữa bài](VIDEO_A_CHUA_BAI_URL)

---

## Bài B: Chẵn lẻ

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/294730/problem/B)

<details>
<summary>Hint</summary>

Một số chẵn nếu chia cho 2 dư 0.

</details>

[🎥 Video chữa bài](VIDEO_B_CHUA_BAI_URL)

---

## Bài C: Âm dương

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/294730/problem/C)

<details>
<summary>Hint</summary>

Kiểm tra số lớn hơn, nhỏ hơn hay bằng 0.

</details>

[🎥 Video chữa bài](VIDEO_C_CHUA_BAI_URL)

---

## Bài D: Giờ giấc

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/294730/problem/D)

<details>
<summary>Hint</summary>

Chia thành các khoảng thời gian và dùng if else để xử lý.

</details>

[🎥 Video chữa bài](VIDEO_D_CHUA_BAI_URL)

---

## Bài E: Số lớn nhất 3

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/294730/problem/E)

<details>
<summary>Hint</summary>

So sánh từng cặp hoặc dùng biến trung gian để tìm max.

</details>

[🎥 Video chữa bài](VIDEO_E_CHUA_BAI_URL)

---

## Bài F: Xếp loại học lực

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/294730/problem/F)

<details>
<summary>Hint</summary>

Dùng nhiều điều kiện if else theo khoảng điểm.

</details>

[🎥 Video chữa bài](VIDEO_F_CHUA_BAI_URL)

---

## Bài G: Phương trình bậc hai

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/294730/problem/G)

<details>
<summary>Hint</summary>

Tính delta và xét các trường hợp:
- delta < 0
- delta = 0
- delta > 0

</details>

[🎥 Video chữa bài](VIDEO_G_CHUA_BAI_URL)

---

## Bài H: Đọc ngày trong tuần

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/294730/problem/H)

<details>
<summary>Hint</summary>

Dùng if else hoặc switch để ánh xạ số sang tên ngày.

</details>

[🎥 Video chữa bài](VIDEO_H_CHUA_BAI_URL)

---

## Bài I: Đọc số

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/294730/problem/I)

<details>
<summary>Hint</summary>

Phân tích từng chữ số và chuyển thành chữ.

</details>

[🎥 Video chữa bài](VIDEO_I_CHUA_BAI_URL)

---

## Bài J: Đọc tên tháng

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/294730/problem/J)

<details>
<summary>Hint</summary>

Dùng if else hoặc switch để chuyển số tháng thành tên.

</details>

[🎥 Video chữa bài](VIDEO_J_CHUA_BAI_URL)

---


<div class="course-progress">Tiến độ: Tuần 2 / 8</div>
<div class="course-topbar" markdown="1">
<div>⬅️ [Tuần trước](/khoa-hoc/cpp/week-01/)</div>
<div>[Trang khóa học](/khoa-hoc/cpp/)</div>
<div>[Tuần tiếp theo](/khoa-hoc/cpp/week-03/) ➡️</div>
</div>


</main>
</div>
