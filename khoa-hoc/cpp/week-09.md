---
layout: page
title: Tuần 9 - Hàm tự viết
permalink: /khoa-hoc/cpp/week-09/
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

# Tuần 9 - Hàm tự viết

Tuần 9 giúp học sinh:

👉 tự xây dựng hàm riêng  
👉 chia nhỏ bài toán  
👉 tái sử dụng code  
👉 viết chương trình rõ ràng, có cấu trúc  

Đây là bước chuyển cực quan trọng từ “viết code từng bài” sang “tư duy lập trình bài bản”.

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
<a class="current" href="/khoa-hoc/cpp/week-09/">Tuần 9</a>
<a href="/khoa-hoc/cpp/week-10/">Tuần 10</a>
<a href="/khoa-hoc/cpp/week-11/">Tuần 11</a>
<a href="/khoa-hoc/cpp/week-12/">Tuần 12</a>

</div>
</div>

---

## 1. Tổng quan các bài trong tuần

<div class="week-image">
<img src="/khoa-hoc/cpp/cpp-week-09-overview.png">
</div>

---

## 2. Làm thử bài đầu

👉 Đây là phần demo miễn phí  
👉 Bài này giúp bạn hiểu bản chất của hàm  

---

### Bài A: Hàm cộng hai số

<details>
<summary>💡 Hint</summary>

Viết một hàm có dạng:

- nhận 2 tham số a, b  
- trả về kết quả a + b  

Sau đó:

- gọi hàm trong main  
- in kết quả  

👉 Điều quan trọng cần hiểu:

- input của hàm  
- output của hàm  
- cách gọi hàm  

</details>

---

## 3. 🎥 Video chữa bài demo

<div class="video-box">

<iframe 
width="100%" height="400"
src="https://www.youtube.com/embed/VIDEO_TUAN_9?rel=0"
frameborder="0"
allowfullscreen>
</iframe>

</div>

---

## 4. Các bài còn lại (dành cho học viên)

<div class="locked-list">

<ul>

<li><b>Bài B: Hàm maxi</b> — viết hàm tìm số lớn hơn giữa hai số.</li>

<li><b>Bài C: Hàm tráo đổi hai số</b> — luyện swap, có thể dùng biến trung gian hoặc tham chiếu.</li>

<li><b>Bài D: Lập phương</b> — viết hàm tính a³.</li>

<li><b>Bài E: Hàm kiểm tra số chẵn</b> — trả về true/false.</li>

<li><b>Bài F: Đường tròn</b> — tính diện tích, chu vi bằng hàm.</li>

<li><b>Bài G: Hàm kiểm tra nguyên tố</b> — tách logic kiểm tra thành hàm riêng.</li>

<li><b>Bài H: Hàm kiểm tra số hoàn hảo</b> — dùng lại tư duy tuần 5 nhưng đưa vào hàm.</li>

<li><b>Bài I: Hàm tính giai thừa</b> — viết hàm tính n!.</li>

<li><b>Bài J: Giải phương trình bậc nhất</b> — tách xử lý vào hàm.</li>

<li><b>Bài L: BCNN</b> — dùng UCLN để xây dựng hàm BCNN.</li>

<li><b>Bài M: Diện tích tam giác</b> — viết hàm tính toán.</li>

<li><b>Bài N: Max diện tích</b> — gọi nhiều hàm và so sánh.</li>

<li><b>Bài O: TIME</b> — bài tổng hợp logic + hàm.</li>

<li><b>Bài P: Drawbox</b> — dùng hàm để in hình.</li>

</ul>

</div>

---

## 5. Vì sao tuần 9 quan trọng?

Tuần này là bước chuyển lớn về tư duy:

- học sinh biết chia nhỏ bài toán  
- biết tổ chức code  
- biết tái sử dụng hàm  
- giảm lỗi khi viết chương trình dài  

👉 Đây là nền tảng bắt buộc trước khi học thuật toán nâng cao.

---

<div class="cta-box">

## 🔓 Mở khóa toàn bộ khóa học

Học tiếp để:

- Viết chương trình có cấu trúc rõ ràng  
- Làm chủ tư duy lập trình  
- Chuẩn bị cho sắp xếp và tìm kiếm  

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
