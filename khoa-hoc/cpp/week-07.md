---
layout: page
title: Tuần 7 - Mảng hai chiều
permalink: /khoa-hoc/cpp/week-07/
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

# Tuần 7 - Mảng hai chiều

Tuần 7 giúp học sinh mở rộng từ mảng một chiều sang ma trận:

👉 làm việc với hàng và cột  
👉 duyệt ma trận bằng 2 vòng lặp  
👉 xử lý các bài toán bảng số  

Đây là bước quan trọng để chuẩn bị cho các bài toán nâng cao hơn.

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
<a class="current" href="/khoa-hoc/cpp/week-07/">Tuần 7</a>
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
<img src="/khoa-hoc/cpp/cpp-week-07-overview.png">
</div>

---

## 2. Làm thử 2 bài đầu

👉 Đây là phần demo miễn phí  
👉 Hai bài đầu giúp bạn hiểu cách làm việc với ma trận  

---

### Bài A: Nhập, xuất mảng hai chiều

<details>
<summary>💡 Hint</summary>

Dùng 2 vòng lặp:

- vòng ngoài duyệt theo hàng  
- vòng trong duyệt theo cột  

Nhập từng phần tử a[i][j]  
Sau đó in lại theo đúng định dạng  

</details>

---

### Bài B: Bảng nhân N

<details>
<summary>💡 Hint</summary>

Phần tử tại vị trí (i, j):

👉 thường được tính bằng i × j  

Dùng 2 vòng lặp để in bảng  

</details>

---

## 3. 🎥 Video chữa 2 bài đầu

<div class="video-box">

<iframe 
width="100%" height="400"
src="https://www.youtube.com/embed/VIDEO_TUAN_7?rel=0"
frameborder="0"
allowfullscreen>
</iframe>

</div>

👉 Nên tự làm trước, sau đó xem video để hiểu cách duyệt ma trận.

---

## 4. Các bài còn lại (dành cho học viên)

<div class="locked-list">

<ul>

<li><b>Bài C: Tổng thành phần ma trận</b> — duyệt toàn bộ bảng và cộng dồn.</li>

<li><b>Bài D: Tổng đường chéo chính</b> — phần tử có chỉ số i = j.</li>

<li><b>Bài E: Tổng đường chéo phụ</b> — phần tử có i + j = n + 1.</li>

<li><b>Bài F: Đổi chéo chính - phụ</b> — hoán đổi hai đường chéo.</li>

<li><b>Bài G: Ma trận tam giác trên</b> — xét phần tử phía trên đường chéo.</li>

<li><b>Bài H: Ma trận tam giác dưới</b> — xét phần tử phía dưới đường chéo.</li>

<li><b>Bài I: Nhân ma trận với số</b> — nhân từng phần tử.</li>

<li><b>Bài J: Cộng hai ma trận</b> — cộng từng phần tử tương ứng.</li>

<li><b>Bài K: Nhân hai ma trận</b> — kết hợp hàng và cột.</li>

<li><b>Bài L: Ma trận đẹp</b> — kiểm tra điều kiện đặc biệt.</li>

<li><b>Bài M: Tic Tac Toe</b> — kiểm tra hàng, cột, đường chéo.</li>

<li><b>Bài N: Ma trận đơn vị</b> — đường chéo = 1, còn lại = 0.</li>

</ul>

</div>

---

## 5. Vì sao tuần 7 quan trọng?

Tuần này giúp học sinh:

- hiểu cách xử lý dữ liệu dạng bảng  
- làm quen với tư duy hàng/cột  
- rèn kỹ năng dùng 2 vòng lặp  
- chuẩn bị tốt cho bài toán xâu và thuật toán nâng cao  

👉 Đây là nền tảng quan trọng cho các bài toán sau này.

---

<div class="cta-box">

## 🔓 Mở khóa toàn bộ khóa học

Học tiếp để:

- Thành thạo mảng hai chiều  
- Giải được các bài toán bảng phức tạp  
- Chuẩn bị cho xâu và thuật toán  

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
