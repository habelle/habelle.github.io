---
layout: page
title: Tuần 1 - Làm quen với C++
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

# Tuần 1 - Làm quen với C++

---

## 🎯 Tuần này bạn sẽ học gì?

- Biết viết chương trình C++ đầu tiên
- Làm quen với nhập xuất dữ liệu
- Hiểu biến, kiểu dữ liệu và phép toán cơ bản

👉 Đây là tuần giúp học sinh **bắt đầu từ con số 0** và cảm thấy “mình làm được”

---

## 📌 Cách học trong tuần

1. Vào contest và làm từng bài theo thứ tự  
2. Nếu bí → thử lại 1–2 lần trước khi xem gợi ý  
3. Sau khi làm xong → xem video chữa bài  

👉 Không nên xem lời giải ngay từ đầu

---

# 🧩 Làm bài tại đây

👉 Toàn bộ bài tập tuần 1 nằm trong contest dưới đây:

👉 [🚀 Vào contest Tuần 1](https://codeforces.com/group/PYFjMy37xA/contests)

---

💡 Gợi ý:

- Nên làm theo thứ tự từ A → B → C → ...
- Mỗi bài chỉ cần AC là đủ, không cần tối ưu

---

# 🔍 Xem thử cách học

👉 Đây là cách một bài trong khóa học được hướng dẫn

---

## 🧪 Bài mẫu: Tổng A + B

👉 Làm bài trong contest (bài A)

---

<details>
<summary>💡 Hint 1</summary>

Cần nhập 2 số từ bàn phím

</details>

<details>
<summary>💡 Hint 2</summary>

Tính tổng của 2 số đó

</details>

<details>
<summary>💡 Hint 3</summary>

In kết quả ra màn hình

</details>

---

👉 🎥 Video chữa bài:

[▶ Xem video chữa bài](VIDEO_A_CHUA_BAI_URL)

---

💥 Khi học, học sinh sẽ:

- tự làm trước  
- mở hint khi bí  
- sau đó xem video để hiểu cách làm đúng  

👉 Đây là cách giúp học sinh tiến bộ nhanh nhất

---

# 🚀 Sau tuần này bạn sẽ làm được gì?

- Viết được chương trình C++ đơn giản  
- Hiểu cách nhập và xuất dữ liệu  
- Làm được các bài toán cơ bản  

👉 Quan trọng nhất: **bắt đầu quen với việc tự giải bài**

---

# 🔓 Học tiếp các tuần sau

👉 Tuần 1 là phần mở đầu miễn phí

Từ tuần 2 trở đi, học sinh sẽ:

- Làm các bài có điều kiện (`if else`)
- Học vòng lặp, mảng, xâu ký tự
- Giải các bài toán khó dần theo lộ trình

---

## 👉 Đăng ký để học đầy đủ lộ trình

[👉 Đăng ký qua Google Form](LINK_GOOGLE_FORM)

hoặc  

👉 Liên hệ trực tiếp:
- Zalo: 0906 090 788  
- Facebook: http://facebook.com/hoang.ha.9134  
- Email: ha.hoangthi@gmail.com  

---

💡 Gợi ý:

👉 Hãy học thử tuần 1, nếu thấy phù hợp hãy quay lại đăng ký để học tiếp các tuần sau.
