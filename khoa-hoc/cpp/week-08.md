---
layout: page
title: Tuần 8 - Xử lý xâu ký tự
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

# Tuần 8 - Xử lý xâu ký tự

Tuần 8 giúp học sinh làm quen với dữ liệu dạng văn bản:

👉 duyệt từng ký tự trong xâu  
👉 đếm ký tự  
👉 so sánh xâu  
👉 kiểm tra xâu đối xứng  
👉 xử lý từ và ký tự theo điều kiện  

Đây là bước chuyển quan trọng từ xử lý số, mảng sang xử lý dữ liệu văn bản.

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
👉 Hai bài đầu giúp học sinh làm quen với thao tác duyệt và xử lý xâu ký tự  

---

### Bài A: New string

<details>
<summary>💡 Hint</summary>

Đọc xâu đầu vào.

Sau đó duyệt từng ký tự trong xâu bằng vòng lặp.

Với mỗi ký tự, xử lý theo đúng yêu cầu đề bài.

Khi làm bài xử lý xâu, cần chú ý:

- độ dài xâu
- vị trí ký tự
- ký tự đầu tiên và ký tự cuối cùng
- kết quả cần tạo ra là xâu mới hay chỉ in trực tiếp

</details>

---

### Bài B: String counts

<details>
<summary>💡 Hint</summary>

Duyệt toàn bộ xâu từ trái sang phải.

Dùng biến đếm để đếm số ký tự thỏa mãn điều kiện.

Nếu đề yêu cầu đếm một loại ký tự cụ thể, hãy kiểm tra từng ký tự khi duyệt.

Ví dụ tư duy chung:

- gặp ký tự cần đếm → tăng biến đếm
- không gặp → bỏ qua

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

👉 Nên tự làm trước, sau đó xem video để hiểu cách duyệt xâu và xử lý từng ký tự.

---

## 4. Các bài còn lại (dành cho học viên)

<div class="locked-list">

<ul>

<li><b>Bài C: Compare</b> — luyện so sánh hai xâu, hiểu thứ tự từ điển và cách so sánh ký tự.</li>

<li><b>Bài D: Strings</b> — tổng hợp các thao tác cơ bản trên xâu như nối, duyệt, truy cập ký tự.</li>

<li><b>Bài E: Count</b> — luyện đếm ký tự thỏa mãn điều kiện trong xâu.</li>

<li><b>Bài F: Way Too Long Words</b> — xử lý xâu theo quy tắc rút gọn, bài kinh điển cho người mới học.</li>

<li><b>Bài G: Palindrome</b> — kiểm tra xâu đối xứng bằng cách so sánh hai đầu.</li>

<li><b>Bài H: COUNT LETTERS</b> — dùng mảng đếm để thống kê số lần xuất hiện của chữ cái.</li>

<li><b>Bài I: WORD COUNT</b> — đếm số từ trong một dòng văn bản, chú ý khoảng trắng và ký tự phân tách.</li>

<li><b>Bài J: COUNT CHARS</b> — đếm ký tự theo yêu cầu, rèn kỹ năng duyệt và phân loại ký tự.</li>

</ul>

</div>

---

## 5. Vì sao tuần 8 quan trọng?

Tuần này giúp học sinh:

- làm quen với dữ liệu dạng xâu ký tự
- biết cách duyệt từng ký tự
- biết cách đếm, so sánh và kiểm tra điều kiện trên xâu
- sử dụng lại kiến thức vòng lặp, điều kiện và mảng
- chuẩn bị cho các bài xử lý văn bản nâng cao hơn

Xử lý xâu là phần rất thường gặp trong các bài thi lập trình cơ bản và học sinh giỏi cấp 2.

Nếu học sinh nắm chắc tuần này, các em sẽ tự tin hơn khi gặp các bài liên quan đến ký tự, từ, câu, chuỗi đối xứng hoặc thống kê tần suất.

---

<div class="cta-box">

## 🔓 Mở khóa toàn bộ khóa học

Học tiếp để:

- Thành thạo xử lý xâu ký tự  
- Biết cách phân tích bài toán văn bản  
- Chuẩn bị tốt cho phần hàm, sắp xếp, tìm kiếm và đệ quy  

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
