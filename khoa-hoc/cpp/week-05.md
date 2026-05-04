---
layout: page
title: Tuần 5 - Vòng lặp lồng nhau và in hình sao
permalink: /khoa-hoc/cpp/week-05/
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

# Tuần 5 - Vòng lặp lồng nhau và in hình sao

Tuần 5 giúp học sinh rèn luyện sâu hơn về vòng lặp:

👉 liệt kê nhiều số thỏa mãn điều kiện  
👉 kiểm tra từng số trong một đoạn  
👉 sử dụng vòng lặp lồng nhau  
👉 quan sát quy luật dòng/cột khi in hình  

Đây là tuần rất quan trọng để học sinh chuyển từ “biết dùng vòng lặp” sang “biết tổ chức vòng lặp để giải bài toán”.

</div>

---

## Điều hướng khóa học

<div class="course-nav">
<div class="course-nav-grid">

<a href="/khoa-hoc/cpp/week-01/">Tuần 1</a>
<a href="/khoa-hoc/cpp/week-02/">Tuần 2</a>
<a href="/khoa-hoc/cpp/week-03/">Tuần 3</a>
<a href="/khoa-hoc/cpp/week-04/">Tuần 4</a>
<a class="current" href="/khoa-hoc/cpp/week-05/">Tuần 5</a>
<a href="/khoa-hoc/cpp/week-06/">Tuần 6</a>
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
<img src="/khoa-hoc/cpp/cpp-week-05-overview.png">
</div>

---

## 2. Làm thử 2 bài đầu

👉 Đây là phần demo miễn phí.  
👉 Hai bài đầu giúp học sinh luyện cách “duyệt một đoạn” và kiểm tra từng số trong đoạn.  
👉 Nên tự làm trước khi mở hint.

---

### Bài A: Liệt kê số nguyên tố trong đoạn

<details>
<summary>💡 Hint</summary>

Duyệt từng số trong đoạn.

Với mỗi số, kiểm tra xem số đó có phải là số nguyên tố hay không.

Một số nguyên tố là số lớn hơn 1 và chỉ có đúng hai ước là 1 và chính nó.

Có thể kiểm tra bằng cách thử chia từ 2 đến căn bậc hai của số đó.

</details>

---

### Bài B: Liệt kê số Armstrong

<details>
<summary>💡 Hint</summary>

Duyệt từng số trong đoạn.

Với mỗi số:

1. Lưu lại giá trị ban đầu.
2. Tách từng chữ số bằng `% 10`.
3. Tính tổng lũy thừa các chữ số theo yêu cầu đề bài.
4. So sánh tổng đó với số ban đầu.

Nếu bằng nhau thì đó là số Armstrong.

</details>

---

## 3. 🎥 Video chữa 2 bài đầu

<div class="video-box">

<iframe 
width="100%" height="400"
src="https://www.youtube.com/embed/VIDEO_TUAN_5?rel=0"
frameborder="0"
allowfullscreen>
</iframe>

</div>

👉 Video chữa hai bài demo đầu tiên của tuần 5.  
👉 Học sinh nên tự làm trước, sau đó xem video để kiểm tra lại cách nghĩ và cách tổ chức vòng lặp.

---

## 4. Các bài còn lại (dành cho học viên)

Các bài dưới đây có sẵn hint và hướng dẫn giải chi tiết dành cho học viên chính thức.

<div class="locked-list">

<ul>

<li><b>Bài C: Liệt kê số hoàn hảo</b> — luyện duyệt từng số, tính tổng ước và kiểm tra điều kiện.</li>

<li><b>Bài D: Hình vuông dấu sao</b> — làm quen với vòng lặp lồng nhau để in hình theo dòng và cột.</li>

<li><b>Bài E: Hình vuông sao rỗng</b> — phân biệt vị trí biên và vị trí bên trong của hình.</li>

<li><b>Bài F: Hình tam giác sao trái</b> — quan sát quy luật số dấu sao trên từng dòng.</li>

<li><b>Bài G: Tam giác sao lệch trái</b> — kết hợp khoảng trắng và dấu sao trong từng dòng.</li>

<li><b>Bài H: Hình tam giác sao rỗng lệch phải</b> — chỉ in sao tại các cạnh của tam giác.</li>

<li><b>Bài I: Hình tam giác sao rỗng lệch trái</b> — tiếp tục luyện tư duy biên trong các bài in hình.</li>

</ul>

</div>

---

## 5. Vì sao tuần 5 quan trọng?

Tuần 5 là cầu nối giữa vòng lặp cơ bản và các bài xử lý dữ liệu phức tạp hơn.

Nếu học sinh làm tốt tuần này, các em sẽ:

- biết cách kiểm tra nhiều số trong một đoạn
- hiểu cách lồng vòng lặp
- biết quan sát quy luật dòng/cột
- chuẩn bị tốt cho phần mảng một chiều ở tuần 6
- có tư duy tốt hơn khi gặp bài cần duyệt nhiều lớp

Đây cũng là tuần học sinh dễ “bật lên” về tư duy nếu được luyện đúng cách.

---

<div class="cta-box">

## 🔓 Mở khóa toàn bộ khóa học

Học tiếp để:

- Thành thạo vòng lặp lồng nhau  
- Biết cách phân tích quy luật hình học đơn giản  
- Chuẩn bị chắc nền cho mảng, xâu, hàm và thuật toán cơ bản  

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
