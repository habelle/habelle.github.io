---
layout: page
title: Tuần 9 - Hàm và xử lý ký tự
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

# Tuần 9 - Hàm và xử lý ký tự

Tuần 9 giúp học sinh bắt đầu làm quen với:

👉 sử dụng các hàm có sẵn  
👉 xử lý ký tự nâng cao  
👉 viết chương trình gọn hơn, rõ ràng hơn  

Đây là bước chuyển từ “viết code trực tiếp” sang “tổ chức code tốt hơn”.

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

## 2. Làm thử 2 bài đầu

👉 Đây là phần demo miễn phí  
👉 Hai bài đầu giúp học sinh làm quen với xử lý ký tự  

---

### Bài A: Chuyển kí tự hoa, thường

<details>
<summary>💡 Hint</summary>

Một ký tự có thể chuyển đổi giữa chữ hoa và chữ thường dựa trên mã ASCII.

Ví dụ:

- 'a' → 'A'
- 'A' → 'a'

Có thể làm theo 2 cách:

1. Dùng điều kiện:
   - nếu là chữ thường → trừ 32
   - nếu là chữ hoa → cộng 32  

2. Hoặc dùng hàm có sẵn nếu được phép.

</details>

---

### Bài B: Xâu kí tự thường

<details>
<summary>💡 Hint</summary>

Duyệt từng ký tự trong xâu.

Kiểm tra xem ký tự có phải chữ thường hay không.

Có thể dựa vào khoảng:

- 'a' → 'z'

Nếu cần chuyển đổi, áp dụng quy tắc ASCII.

</details>

---

## 3. 🎥 Video chữa 2 bài đầu

<div class="video-box">

<iframe 
width="100%" height="400"
src="https://www.youtube.com/embed/VIDEO_TUAN_9?rel=0"
frameborder="0"
allowfullscreen>
</iframe>

</div>

👉 Nên tự làm trước, sau đó xem video để hiểu cách xử lý ký tự.

---

## 4. Các bài còn lại (dành cho học viên)

<div class="locked-list">

<ul>

<li><b>Bài C: Đếm kí tự ABCDEF</b> — đếm số ký tự thuộc một tập cho trước.</li>

<li><b>Bài D: Đếm kí tự A...Z</b> — luyện đếm chữ cái in hoa.</li>

<li><b>Bài E: Max 2</b> — dùng hàm `max` để tìm giá trị lớn hơn.</li>

<li><b>Bài F: ABS</b> — tính giá trị tuyệt đối, chú ý trường hợp âm.</li>

<li><b>Bài H: Ước chung lớn nhất</b> — sử dụng thuật toán Euclid hoặc hàm có sẵn.</li>

</ul>

</div>

---

## 5. Vì sao tuần 9 quan trọng?

Tuần này giúp học sinh:

- hiểu cách sử dụng hàm để viết code gọn hơn  
- làm quen với thư viện và hàm có sẵn  
- nâng cao kỹ năng xử lý ký tự  
- bắt đầu có tư duy tổ chức chương trình  

👉 Đây là bước đệm trước khi học viết hàm riêng và các thuật toán quan trọng hơn.

---

<div class="cta-box">

## 🔓 Mở khóa toàn bộ khóa học

Học tiếp để:

- Viết code gọn và rõ ràng hơn  
- Thành thạo xử lý ký tự  
- Chuẩn bị cho phần hàm, sắp xếp và tìm kiếm  

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
