---
layout: page
title: Tuần 11 - Sắp xếp và tìm kiếm nhị phân
permalink: /khoa-hoc/cpp/week-11/
---

<style>
.week-hero{
padding:26px;
border-radius:20px;
background:linear-gradient(135deg,#eef6ff,#f8fbff);
border:1px solid #dbeafe;
margin-bottom:24px
}
.course-nav{
padding:16px;
border:1px solid #e5e7eb;
border-radius:16px;
background:#fafafa;
margin:20px 0
}
.course-nav-grid{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(90px,1fr));
gap:8px
}
.course-nav a{
display:block;
padding:8px;
border-radius:10px;
text-align:center;
text-decoration:none;
border:1px solid #e5e7eb;
background:white;
font-weight:600
}
.course-nav a.current{
background:#2563eb;
color:white !important;
border-color:#2563eb
}
.week-image{
margin:20px 0;
border-radius:16px;
overflow:hidden;
border:1px solid #e5e7eb
}
.week-image img{width:100%}
.locked-list{
padding:18px;
border-radius:16px;
border:1px dashed #cbd5e1;
background:#f8fafc;
margin:18px 0
}
details{
margin-top:10px;
padding:10px;
background:#f9fafb;
border-radius:10px;
border:1px solid #e5e7eb
}
.video-box{
margin:24px 0;
padding:16px;
border:1px solid #e5e7eb;
border-radius:16px;
background:#fafafa
}
.cta-box{
padding:28px;
border-radius:20px;
background:linear-gradient(135deg,#eff6ff,#fff7ed);
border:1px solid #bfdbfe;
margin-top:40px;
text-align:center
}
</style>

<div class="week-hero">

# Tuần 11 - Sắp xếp và tìm kiếm nhị phân

Tuần 11 là bước nâng cấp mạnh về tư duy:

👉 sắp xếp dữ liệu  
👉 tìm kiếm nhanh  
👉 tối ưu thuật toán  

Đây là nền tảng cực kỳ quan trọng cho các bài thi học sinh giỏi.

</div>

---

## Điều hướng khóa học

<div class="course-nav">
<div class="course-nav-grid">

<a href="/khoa-hoc/cpp/week-01/">Tuần 1</a>
<a href="/khoa-hoc/cpp/week-02/">Tuần 2</a>
<a href="/khoa-hoc/cpp/week-03/">Tuần 3</a>
<a href="/khoa-hoc/cpp/week-04/">Tuần 4</a>
<a href="/khoa-hoc/cpp/week-05/">Tuần 5</a>
<a href="/khoa-hoc/cpp/week-06/">Tuần 6</a>
<a href="/khoa-hoc/cpp/week-07/">Tuần 7</a>
<a href="/khoa-hoc/cpp/week-08/">Tuần 8</a>
<a href="/khoa-hoc/cpp/week-09/">Tuần 9</a>
<a href="/khoa-hoc/cpp/week-10/">Tuần 10</a>
<a class="current" href="/khoa-hoc/cpp/week-11/">Tuần 11</a>
<a href="/khoa-hoc/cpp/week-12/">Tuần 12</a>

</div>
</div>

---

## 1. Tổng quan các bài trong tuần

<div class="week-image">
<img src="/khoa-hoc/cpp/cpp-week-11-overview.png">
</div>

---

## 2. Làm thử bài đầu

👉 Đây là phần demo miễn phí  
👉 Bài này giúp bạn hiểu bản chất của sắp xếp  

---

### Bài A: SORT1

<details>
<summary>💡 Hint</summary>

Bạn có thể sử dụng hàm sort có sẵn trong C++:

- sort(a, a + n)

Các bước:

1. Nhập mảng  
2. Gọi hàm sort  
3. In lại mảng  

👉 Điều quan trọng:

- hiểu vì sao cần sắp xếp  
- hiểu dữ liệu sau khi sắp xếp giúp gì cho bài toán  

</details>

---

## 3. 🎥 Video chữa bài demo

<div class="video-box">

<iframe 
width="100%" height="400"
src="https://www.youtube.com/embed/VIDEO_TUAN_11?rel=0"
frameborder="0"
allowfullscreen>
</iframe>

</div>

---

## 4. Các bài còn lại (dành cho học viên)

<div class="locked-list">

<ul>

<li><b>Bài B: SORT2</b> — luyện thêm các dạng sắp xếp cơ bản.</li>

<li><b>Bài C: SORT3</b> — hiểu cách thay đổi tiêu chí sắp xếp.</li>

<li><b>Bài D: SORT4</b> — xử lý dữ liệu sau khi sắp xếp.</li>

<li><b>Bài E: SORT5</b> — sắp xếp theo yêu cầu đề bài.</li>

<li><b>Bài F: SORT6</b> — bài tổng hợp sắp xếp.</li>

<li><b>Bài G: SORT7</b> — luyện kỹ năng xử lý sau sort.</li>

<li><b>Bài H: SORT8</b> — bài nâng cao hơn với nhiều điều kiện.</li>

<li><b>Bài I: Binary Search 1</b> — tìm kiếm nhanh trên mảng đã sắp xếp.</li>

<li><b>Bài J: Binary Search 2</b> — xác định vị trí trái/phải.</li>

<li><b>Bài K: Binary Search 3</b> — xử lý biên và điều kiện dừng.</li>

</ul>

</div>

---

## 5. Vì sao tuần 11 quan trọng?

Tuần này là bước nhảy lớn về tư duy:

- từ duyệt O(n) → tìm kiếm O(log n)  
- hiểu cách tối ưu chương trình  
- biết cách xử lý dữ liệu hiệu quả  

👉 Đặc biệt:

Binary Search là kỹ thuật cực kỳ quan trọng trong lập trình thi đấu.

Nếu học sinh nắm chắc tuần này, khả năng giải bài sẽ tăng lên rất nhiều.

---

<div class="cta-box">

## 🔓 Mở khóa toàn bộ khóa học

Học tiếp để:

- Thành thạo sắp xếp  
- Làm chủ Binary Search  
- Giải các bài toán tối ưu  

<br>

<a href="https://forms.gle/tFNgE7FiSq1LCSeC9"
style="padding:12px 20px;background:#2563eb;color:white;border-radius:10px;text-decoration:none;font-weight:700;">
👉 Đăng ký khóa học
</a>

<a href="https://zalo.me/0906090788"
style="padding:12px 20px;background:#16a34a;color:white;border-radius:10px;text-decoration:none;font-weight:700;">
Liên hệ Zalo
</a>

</div>
