---
layout: page
title: Tuần 4 - Vòng lặp nâng cao và xử lý chữ số
permalink: /khoa-hoc/cpp/week-04/
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
<li><a class="active" href="/khoa-hoc/cpp/week-04/">Tuần 4<span class="week-topic">Xử lý chữ số</span></a></li>
<li><a href="/khoa-hoc/cpp/week-05/">Tuần 5<span class="week-topic">Vòng lặp lồng nhau</span></a></li>
<li><a href="/khoa-hoc/cpp/week-06/">Tuần 6<span class="week-topic">Mảng một chiều</span></a></li>
<li><a href="/khoa-hoc/cpp/week-07/">Tuần 7<span class="week-topic">Mảng hai chiều</span></a></li>
<li><a href="/khoa-hoc/cpp/week-08/">Tuần 8<span class="week-topic">Xâu ký tự</span></a></li>
  </ul>
</aside>

<main class="course-main" markdown="1">


<div class="course-progress">Tiến độ: Tuần 4 / 8</div>

# Tuần 4 - Vòng lặp nâng cao và xử lý chữ số

👉 Hãy thử làm bài trước khi mở hint hoặc xem video chữa bài.

---

## Bài A: Đảo ngược số

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/294936/problem/A)

<details>
<summary>Hint</summary>

Dùng vòng lặp để tách từng chữ số bằng phép chia lấy dư cho 10.

</details>

[🎥 Video chữa bài](VIDEO_A_CHUA_BAI_URL)

---

## Bài B: Số Armstrong

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/294936/problem/B)

<details>
<summary>Hint</summary>

Tách từng chữ số, tính tổng lũy thừa các chữ số rồi so sánh với số ban đầu.

</details>

[🎥 Video chữa bài](VIDEO_B_CHUA_BAI_URL)

---

## Bài C: Tìm số đảo ngược của một số

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/294936/problem/C)

<details>
<summary>Hint</summary>

Khởi tạo biến kết quả bằng 0, mỗi lần lấy chữ số cuối và ghép vào kết quả.

</details>

[🎥 Video chữa bài](VIDEO_C_CHUA_BAI_URL)

---

## Bài D: Kiểm tra số đối xứng

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/294936/problem/D)

<details>
<summary>Hint</summary>

Tạo số đảo ngược rồi so sánh với số ban đầu.

</details>

[🎥 Video chữa bài](VIDEO_D_CHUA_BAI_URL)

---

## Bài E: Đọc số

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/294936/problem/E)

<details>
<summary>Hint</summary>

Tách từng chữ số hoặc xử lý theo từng hàng: trăm, chục, đơn vị.

</details>

[🎥 Video chữa bài](VIDEO_E_CHUA_BAI_URL)

---

## Bài F: Viết Bằng Chữ

[🚀 Làm bài](https://codeforces.com/group/EJ0k8l1752/contest/294936/problem/F)

<details>
<summary>Hint</summary>

Chia số thành các phần nhỏ, sau đó chuyển từng phần sang chữ theo quy tắc.

</details>

[🎥 Video chữa bài](VIDEO_F_CHUA_BAI_URL)

---


<div class="course-progress">Tiến độ: Tuần 4 / 8</div>


</main>
</div>
