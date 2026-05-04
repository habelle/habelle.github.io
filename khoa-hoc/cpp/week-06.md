---
layout: page
title: Tuần 6 - Mảng một chiều
permalink: /khoa-hoc/cpp/week-06/
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
.problem-card{
padding:18px;
border:1px solid #e5e7eb;
border-radius:16px;
background:white;
margin:16px 0
}
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

# Tuần 6 - Mảng một chiều

Tuần 6 là bước chuyển cực kỳ quan trọng:

👉 từ xử lý từng biến → xử lý cả một dãy số  
👉 học cách lưu dữ liệu vào mảng  
👉 duyệt mảng và xử lý theo điều kiện  

Đây là nền tảng cho hầu hết các bài toán lập trình sau này.

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
<a class="current" href="/khoa-hoc/cpp/week-06/">Tuần 6</a>
<a href="/khoa-hoc/cpp/week-07/">Tuần 7</a>
<a href="/khoa-hoc/cpp/week-08/">Tuần 8</a>
<a href="/khoa-hoc/cpp/week-09/">Tuần 9</a>
<a href="/khoa-hoc/cpp/week-10/">Tuần 10</a>
<a href="/khoa-hoc/cpp/week-11/">Tuần 11</a>
<a href="/khoa-hoc/cpp/week-12/">Tuần 12</a>

</div>
</div>

---

## 1. Tổng quan các bài trong tuần

<div class="week-image">
<img src="/khoa-hoc/cpp/cpp-week-06-overview.png">
</div>

---

## 2. Làm thử 2 bài đầu

👉 Đây là phần demo miễn phí  
👉 Hai bài đầu giúp bạn hiểu cách dùng mảng và duyệt mảng  

---

### Bài A: Đảo ngược dãy số

<details>
<summary>💡 Hint</summary>

Có hai cách:

Cách 1:  
- Duyệt từ cuối mảng về đầu và in ra  

Cách 2:  
- Hoán đổi phần tử đầu và cuối  
- Sau đó dịch dần vào giữa  

</details>

---

### Bài B: Tính tổng dãy số

<details>
<summary>💡 Hint</summary>

- Khởi tạo biến tổng = 0  
- Duyệt mảng từ đầu đến cuối  
- Cộng từng phần tử vào tổng  

</details>

---

## 3. 🎥 Video chữa 2 bài đầu

<div class="video-box">

<iframe 
width="100%" height="400"
src="https://www.youtube.com/embed/VIDEO_TUAN_6?rel=0"
frameborder="0"
allowfullscreen>
</iframe>

</div>

👉 Nên tự làm trước, sau đó xem video để hiểu cách duyệt mảng và xử lý.

---

## 4. Các bài còn lại (dành cho học viên)

<div class="locked-list">

<ul>

<li><b>Bài C: Tổng số lẻ trong dãy</b> — chỉ cộng các phần tử thỏa điều kiện.</li>

<li><b>Bài D: Thay thế số nguyên</b> — duyệt mảng và thay đổi phần tử theo yêu cầu.</li>

<li><b>Bài E: Tìm phần tử lớn nhất</b> — dùng biến max và cập nhật khi duyệt.</li>

<li><b>Bài F: Vị trí số nhỏ hơn 10</b> — in ra vị trí thỏa điều kiện.</li>

<li><b>Bài G: Đảo vị trí đầu cuối</b> — hoán đổi phần tử.</li>

<li><b>Bài H: Hoán đổi max - min</b> — tìm vị trí rồi swap.</li>

<li><b>Bài I: Cặp liên kề lớn nhất</b> — xét từng cặp i và i+1.</li>

<li><b>Bài J: Chèn phần tử</b> — dịch mảng sang phải.</li>

<li><b>Bài K: Xóa phần tử</b> — dịch mảng sang trái.</li>

<li><b>Bài L: Đổi sang nhị phân</b> — chia 2 liên tiếp.</li>

<li><b>Bài M: Tìm kiếm tuần tự</b> — duyệt từ đầu đến cuối.</li>

<li><b>Bài N: Sắp xếp chọn</b> — chọn phần tử nhỏ nhất.</li>

<li><b>Bài O: Số nhỏ nhì</b> — theo dõi hai giá trị nhỏ nhất.</li>

</ul>

</div>

---

## 5. Vì sao tuần 6 quan trọng?

Tuần này giúp học sinh:

- hiểu cách lưu và xử lý nhiều dữ liệu  
- làm quen với các bài toán thực tế hơn  
- bắt đầu có tư duy thuật toán cơ bản  
- chuẩn bị nền cho mảng 2 chiều và xâu  

👉 Nếu yếu phần này, các phần sau sẽ rất khó.

---

<div class="cta-box">

## 🔓 Mở khóa toàn bộ khóa học

Học tiếp để:

- Thành thạo mảng  
- Làm được bài khó hơn  
- Tiến tới tư duy thuật toán  

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
