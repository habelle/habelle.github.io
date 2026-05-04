---
layout: page
title: Tuần 10 - Xâu ký tự
permalink: /khoa-hoc/cpp/week-10/
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

# Tuần 10 - Xâu ký tự

Tuần 10 giúp học sinh làm chủ dữ liệu dạng xâu:

👉 duyệt từng ký tự  
👉 đếm và phân loại ký tự  
👉 so sánh xâu  
👉 xử lý bài toán thực tế với chuỗi  

Đây là phần rất quan trọng trong các bài thi lập trình.

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
<a class="current" href="/khoa-hoc/cpp/week-10/">Tuần 10</a>
<a href="/khoa-hoc/cpp/week-11/">Tuần 11</a>
<a href="/khoa-hoc/cpp/week-12/">Tuần 12</a>

</div>
</div>

---

## 1. Tổng quan các bài trong tuần

<div class="week-image">
<img src="/khoa-hoc/cpp/cpp-week-10-overview.png">
</div>

---

## 2. Làm thử 2 bài đầu

👉 Đây là phần demo miễn phí  
👉 Hai bài đầu giúp bạn làm quen với thao tác trên xâu  

---

### Bài A: New string

<details>
<summary>💡 Hint</summary>

Đọc xâu đầu vào.

Duyệt từng ký tự bằng vòng lặp.

Tùy yêu cầu đề bài, bạn có thể:

- tạo xâu mới  
- hoặc in trực tiếp  

👉 Điều quan trọng:

- biết truy cập ký tự: s[i]  
- biết độ dài: s.length()  

</details>

---

### Bài B: String counts

<details>
<summary>💡 Hint</summary>

Duyệt toàn bộ xâu.

Dùng biến đếm để đếm ký tự thỏa mãn điều kiện.

Ví dụ:

- đếm chữ cái  
- đếm số  
- đếm ký tự đặc biệt  

👉 Mỗi lần gặp ký tự hợp lệ → tăng biến đếm

</details>

---

## 3. 🎥 Video chữa 2 bài đầu

<div class="video-box">

<iframe 
width="100%" height="400"
src="https://www.youtube.com/embed/VIDEO_TUAN_10?rel=0"
frameborder="0"
allowfullscreen>
</iframe>

</div>

---

## 4. Các bài còn lại (dành cho học viên)

<div class="locked-list">

<ul>

<li><b>Bài C: Compare</b> — so sánh hai xâu theo thứ tự từ điển.</li>

<li><b>Bài D: Strings</b> — tổng hợp thao tác với xâu.</li>

<li><b>Bài E: Count</b> — đếm ký tự theo nhiều điều kiện.</li>

<li><b>Bài F: Way Too Long Words</b> — rút gọn xâu theo quy tắc.</li>

<li><b>Bài G: Palindrome</b> — kiểm tra xâu đối xứng.</li>

<li><b>Bài H: COUNT LETTERS</b> — thống kê tần suất chữ cái.</li>

<li><b>Bài I: WORD COUNT</b> — đếm số từ trong câu.</li>

<li><b>Bài J: COUNT CHARS</b> — phân loại ký tự trong xâu.</li>

</ul>

</div>

---

## 5. Vì sao tuần 10 quan trọng?

Tuần này giúp học sinh:

- làm chủ dữ liệu dạng xâu  
- hiểu cách xử lý văn bản  
- rèn kỹ năng duyệt và phân tích dữ liệu  
- áp dụng lại vòng lặp và điều kiện  

👉 Xâu ký tự là dạng bài xuất hiện rất nhiều trong thi lập trình.

---

<div class="cta-box">

## 🔓 Mở khóa toàn bộ khóa học

Học tiếp để:

- Thành thạo xử lý xâu  
- Giải được các bài văn bản  
- Chuẩn bị cho thuật toán nâng cao  

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
