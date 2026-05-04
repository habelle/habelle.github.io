---
layout: page
title: Tuần 8 - Một số hàm có sẵn trong thư viện chuẩn
permalink: /khoa-hoc/cpp/week-08/
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

# Tuần 8 - Một số hàm có sẵn trong thư viện chuẩn

Tuần 8 giúp học sinh làm quen với việc sử dụng các hàm có sẵn trong C++:

👉 chuyển chữ hoa, chữ thường  
👉 kiểm tra và đếm ký tự  
👉 dùng hàm `max`, `abs`  
👉 làm quen với ước chung lớn nhất  

Đây là bước giúp học sinh viết code ngắn gọn hơn, biết tận dụng công cụ có sẵn thay vì tự làm mọi thứ từ đầu.

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
<a class="current" href="/khoa-hoc/cpp/week-08/">Tuần 8</a>
<a href="/khoa-hoc/cpp/week-09/">Tuần 9</a>
<a href="/khoa-hoc/cpp/week-10/">Tuần 10</a>
<a href="/khoa-hoc/cpp/week-11/">Tuần 11</a>
<a href="/khoa-hoc/cpp/week-12/">Tuần 12</a>

</div>
</div>

---

## 1. Tổng quan các bài trong tuần

<div class="week-image">
<img src="/khoa-hoc/cpp/cpp-week-08-overview.png">
</div>

---

## 2. Làm thử 2 bài đầu

👉 Đây là phần demo miễn phí  
👉 Hai bài đầu giúp học sinh làm quen với các hàm xử lý ký tự  

---

### Bài A: Hàm chuyển kí tự hoa, thường

<details>
<summary>💡 Hint</summary>

Bài này thường dùng các hàm xử lý ký tự trong thư viện chuẩn.

Một số hàm cần nhớ:

- `toupper(c)`: chuyển ký tự `c` thành chữ hoa
- `tolower(c)`: chuyển ký tự `c` thành chữ thường

Khi dùng các hàm này, em cần chú ý:

- nhập đúng ký tự
- xử lý kết quả trả về
- in đúng định dạng đề bài yêu cầu

</details>

---

### Bài B: Xâu kí tự thường

<details>
<summary>💡 Hint</summary>

Duyệt từng ký tự trong xâu.

Với mỗi ký tự, có thể dùng:

- `tolower(c)` để chuyển ký tự đó thành chữ thường

Nếu đề yêu cầu cả xâu đều thành chữ thường, hãy xử lý từng ký tự một.

Mẫu tư duy:

- đọc xâu
- duyệt từng vị trí
- chuyển ký tự về chữ thường
- in xâu sau khi xử lý

</details>

---

## 3. 🎥 Video chữa 2 bài đầu

<div class="video-box">

<iframe 
width="100%" height="400"
src="https://www.youtube.com/embed/VIDEO_TUAN_8?rel=0"
frameborder="0"
allowfullscreen>
</iframe>

</div>

👉 Nên tự làm trước, sau đó xem video để hiểu cách sử dụng hàm có sẵn trong thư viện chuẩn.

---

## 4. Các bài còn lại (dành cho học viên)

<div class="locked-list">

<ul>

<li><b>Bài C: Đếm kí tự ABCDEF</b> — luyện đếm các ký tự thuộc một nhóm ký tự cho trước.</li>

<li><b>Bài D: Đếm kí tự A...Z</b> — luyện kiểm tra và đếm chữ cái in hoa.</li>

<li><b>Bài E: Max 2 - Sử dụng hàm max</b> — dùng hàm `max` để tìm số lớn hơn trong hai số.</li>

<li><b>Bài F: ABS -- Trị tuyệt đối</b> — sử dụng hàm trị tuyệt đối để xử lý số âm, số dương.</li>

<li><b>Bài H: Ước chung lớn nhất</b> — làm quen với cách tìm UCLN, có thể dùng thuật toán hoặc hàm hỗ trợ tùy môi trường học.</li>

</ul>

</div>

---

## 5. Vì sao tuần 8 quan trọng?

Tuần này giúp học sinh:

- biết tận dụng thư viện chuẩn của C++
- viết code ngắn gọn và rõ ràng hơn
- hiểu rằng không phải bài nào cũng cần tự xây lại từ đầu
- làm quen với xử lý ký tự, trị tuyệt đối, max và UCLN
- chuẩn bị tốt cho phần viết hàm riêng ở các tuần sau

Đây là bước chuyển từ “biết viết code chạy được” sang “biết dùng công cụ có sẵn để viết code hiệu quả hơn”.

---

<div class="cta-box">

## 🔓 Mở khóa toàn bộ khóa học

Học tiếp để:

- Thành thạo các hàm có sẵn trong C++  
- Biết cách dùng thư viện chuẩn đúng lúc  
- Chuẩn bị cho phần hàm tự viết và thuật toán cơ bản  

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
