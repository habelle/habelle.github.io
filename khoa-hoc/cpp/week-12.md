---
layout: page
title: Tuần 12 - Đệ quy
permalink: /khoa-hoc/cpp/week-12/
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

# Tuần 12 - Đệ quy

Tuần 12 là bước nâng cao cuối cùng của khóa học:

👉 hiểu cách hàm gọi lại chính nó  
👉 giải bài toán bằng tư duy chia nhỏ  
👉 làm quen với Fibonacci, giai thừa, tìm kiếm nhị phân  

Đây là phần mở ra tư duy thuật toán thực sự.

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
<a href="/khoa-hoc/cpp/week-11/">Tuần 11</a>
<a class="current" href="/khoa-hoc/cpp/week-12/">Tuần 12</a>

</div>
</div>

---

## 1. Tổng quan các bài trong tuần

<div class="week-image">
<img src="/khoa-hoc/cpp/cpp-week-12-overview.png">
</div>

---

## 2. Làm thử bài đầu

👉 Đây là phần demo miễn phí  
👉 Bài này giúp bạn hiểu bản chất đệ quy  

---

### Bài A: Giai thừa - đệ quy

<details>
<summary>💡 Hint</summary>

Đệ quy luôn có 2 phần:

1. Điều kiện dừng  
👉 n = 0 → trả về 1  

2. Gọi lại chính nó  
👉 n! = n × (n-1)!  

👉 Cần nhớ:

- phải có điều kiện dừng  
- nếu không sẽ bị lặp vô hạn  

</details>

---

## 3. 🎥 Video chữa bài demo

<div class="video-box">

<iframe 
width="100%" height="400"
src="https://www.youtube.com/embed/VIDEO_TUAN_12?rel=0"
frameborder="0"
allowfullscreen>
</iframe>

</div>

👉 Đây là phần quan trọng, nên xem kỹ để hiểu bản chất đệ quy.

---

## 4. Các bài còn lại (dành cho học viên)

<div class="locked-list">

<ul>

<li><b>Bài B: In n dòng Hello - đệ quy</b> — luyện cách gọi hàm lặp lại.</li>

<li><b>Bài C: Fibonacci - đệ quy</b> — bài kinh điển của recursion.</li>

<li><b>Bài D: Lũy thừa - đệ quy</b> — tính aⁿ bằng đệ quy.</li>

<li><b>Bài E: Lũy thừa nhanh</b> — tối ưu recursion (rất quan trọng).</li>

<li><b>Bài F: UCLN - đệ quy</b> — thuật toán Euclid.</li>

<li><b>Bài G: In dãy số - đệ quy</b> — thay vòng lặp bằng recursion.</li>

<li><b>Bài H: Tổ hợp - đệ quy</b> — bước đầu tiếp cận toán tổ hợp.</li>

<li><b>Bài I: Max trong dãy</b> — tìm max bằng recursion.</li>

<li><b>Bài J: Binary Search - đệ quy</b> — kết hợp 2 kỹ thuật quan trọng.</li>

<li><b>Bài K: Staircase</b> — bài tổng hợp tư duy đệ quy.</li>

</ul>

</div>

---

## 5. Vì sao tuần 12 quan trọng?

Tuần này là bước chuyển sang tư duy thuật toán:

- hiểu cách chia nhỏ bài toán  
- hiểu cách gọi lại chính mình  
- chuẩn bị cho quy hoạch động (DP) sau này  

👉 Đệ quy là nền tảng của rất nhiều thuật toán nâng cao.

---

<div class="cta-box">

## 🎯 Hoàn thành khóa học C++ cơ bản

Bạn đã đi hết lộ trình 12 tuần.

Nếu muốn tiến xa hơn:

👉 luyện thi học sinh giỏi  
👉 học thuật toán nâng cao  
👉 chinh phục các bài thi lớn  

<br>

<a href="https://forms.gle/tFNgE7FiSq1LCSeC9"
style="padding:12px 20px;background:#2563eb;color:white;border-radius:10px;text-decoration:none;font-weight:700;">
👉 Đăng ký khóa nâng cao
</a>

<a href="https://zalo.me/0906090788"
style="padding:12px 20px;background:#16a34a;color:white;border-radius:10px;text-decoration:none;font-weight:700;">
Liên hệ tư vấn
</a>

</div>
