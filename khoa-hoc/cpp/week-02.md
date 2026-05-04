---
layout: page
title: Tuần 2 - Rẽ nhánh và xử lý điều kiện
permalink: /khoa-hoc/cpp/week-02/
---

<style>
.week-hero {
  padding: 24px;
  border-radius: 18px;
  background: linear-gradient(135deg, #eef6ff, #f8fbff);
  border: 1px solid #dbeafe;
  margin-bottom: 24px;
}
.week-note {
  padding: 14px 16px;
  border-left: 5px solid #2563eb;
  background: #eff6ff;
  border-radius: 10px;
  margin: 18px 0;
}
.week-image {
  margin: 20px 0;
  border-radius: 16px;
  overflow: hidden;
  border: 1px solid #e5e7eb;
  background: #f9fafb;
}
.week-image img {
  width: 100%;
  display: block;
}
.video-box {
  margin: 22px 0;
  padding: 16px;
  border: 1px solid #e5e7eb;
  border-radius: 16px;
  background: #fafafa;
}
.video-title {
  font-weight: 700;
  margin-bottom: 10px;
}
.video-frame {
  position: relative;
  padding-bottom: 56.25%;
  height: 0;
  overflow: hidden;
  border-radius: 12px;
  background: #000;
}
.video-frame iframe {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}
.contest-box {
  padding: 20px;
  border-radius: 16px;
  background: #fff7ed;
  border: 1px solid #fed7aa;
  margin: 24px 0;
}
.contest-button, .form-button, .zalo-button {
  display: inline-block;
  padding: 10px 16px;
  border-radius: 10px;
  text-decoration: none;
  font-weight: 700;
  margin: 6px 8px 6px 0;
}
.contest-button {
  background: #ea580c;
  color: white !important;
}
.form-button {
  background: #2563eb;
  color: white !important;
}
.zalo-button {
  background: #16a34a;
  color: white !important;
}
.problem-card {
  padding: 18px;
  border: 1px solid #e5e7eb;
  border-radius: 16px;
  background: #ffffff;
  margin: 18px 0;
}
.problem-card h3 {
  margin-top: 0;
}
.problem-meta {
  color: #4b5563;
  margin-bottom: 12px;
}
.locked-list {
  padding: 18px;
  border-radius: 16px;
  border: 1px dashed #cbd5e1;
  background: #f8fafc;
  margin: 18px 0;
}
.locked-list li {
  margin-bottom: 8px;
}
details {
  margin: 12px 0;
  padding: 12px 14px;
  border-radius: 10px;
  background: #f9fafb;
  border: 1px solid #e5e7eb;
}
summary {
  cursor: pointer;
  font-weight: 700;
}
.cta-box {
  padding: 24px;
  border-radius: 18px;
  background: linear-gradient(135deg, #eff6ff, #fff7ed);
  border: 1px solid #bfdbfe;
  margin: 28px 0;
}
</style>

<div class="week-hero">

# Tuần 2 - Rẽ nhánh và xử lý điều kiện

Tuần 2 giúp học sinh biết cách dùng `if`, `else if`, `else` để chia bài toán thành nhiều trường hợp.

Đây là bước chuyển quan trọng: từ các bài tính toán đơn giản sang các bài cần **đọc đề, xét điều kiện và quyết định hướng xử lý**.

</div>

## 1. Tổng quan các bài trong tuần

<div class="week-image">
  <img src="/khoa-hoc/cpp/cpp-week-02-overview.png" alt="Tổng quan các bài học tuần 2 - Rẽ nhánh và xử lý điều kiện">
</div>


---

## 2. Làm thử 3 bài đầu trong contest demo

Tuần 2 có một phần demo để học sinh làm thử 3 bài đầu trước khi đăng ký khóa học đầy đủ.

<div class="contest-box">

### 🚀 Contest demo tuần 2

<a class="contest-button" href="https://codeforces.com/group/PYFjMy37xA/contests">Vào contest demo</a>

</div>

<div class="week-note">

👉 Hãy làm thử 3 bài A, B, C trước.  
Nếu học sinh thấy cách học phù hợp, có thể đăng ký để mở khóa toàn bộ hint và video hướng dẫn của các bài còn lại.

</div>

---

## 3. Ba bài học mở miễn phí

<div class="problem-card">

### Bài A: Tìm max 2 số

<div class="problem-meta">Kỹ năng chính: dùng `if else` để so sánh hai số.</div>

<details>
<summary>💡 Hint</summary>

Nhập hai số `a`, `b`.  
Nếu `a > b` thì in `a`, ngược lại in `b`.

</details>

</div>

<div class="problem-card">

### Bài B: Chẵn lẻ

<div class="problem-meta">Kỹ năng chính: kiểm tra chia hết và rẽ nhánh.</div>

<details>
<summary>💡 Hint</summary>

Một số là số chẵn nếu chia cho 2 dư 0.  
Điều kiện cần kiểm tra là `n % 2 == 0`.

</details>

</div>

<div class="problem-card">

### Bài C: Âm dương

<div class="problem-meta">Kỹ năng chính: xét nhiều trường hợp bằng `if`, `else if`, `else`.</div>

<details>
<summary>💡 Hint</summary>

Cần xét 3 trường hợp:

- số lớn hơn 0
- số nhỏ hơn 0
- số bằng 0

</details>

</div>

---

## 4. Video chữa 3 bài đầu

Video dưới đây chữa 3 bài demo đầu tiên của tuần 2.

<div class="video-box">
  <div class="video-title">🎥 Video chữa bài tuần 2 - Bài A, B, C</div>

  <div class="video-frame">
    <iframe 
      src="https://www.youtube.com/embed/VIDEO_TUAN_2_DEMO?rel=0"
      frameborder="0"
      allowfullscreen>
    </iframe>
  </div>
</div>

<div class="week-note">

👉 Nên tự làm 3 bài trước rồi mới xem video chữa.  
Video này giúp học sinh hiểu cách đọc điều kiện, viết nhánh và kiểm tra kết quả.

</div>

---

## 5. Các bài còn lại trong tuần 2

Các bài dưới đây có sẵn **hint và hướng dẫn giải chi tiết** dành cho thành viên chính thức của khóa học.

<div class="locked-list">

<ul>
<li><strong>Bài D: Giờ giấc</strong> — có hint và hướng dẫn giải cho học viên chính thức.</li>
<li><strong>Bài E: Số lớn nhất 3</strong> — có hint và hướng dẫn giải cho học viên chính thức.</li>
<li><strong>Bài F: Xếp loại học lực</strong> — có hint và hướng dẫn giải cho học viên chính thức.</li>
<li><strong>Bài G: Phương trình bậc hai</strong> — có hint và hướng dẫn giải cho học viên chính thức.</li>
<li><strong>Bài H: Đọc ngày trong tuần</strong> — có hint và hướng dẫn giải cho học viên chính thức.</li>
<li><strong>Bài I: Đọc số</strong> — có hint và hướng dẫn giải cho học viên chính thức.</li>
<li><strong>Bài J: Đọc tên tháng</strong> — có hint và hướng dẫn giải cho học viên chính thức.</li>
</ul>

</div>

---

<div style="
padding: 28px;
border-radius: 20px;
background: linear-gradient(135deg, #eff6ff, #fff7ed);
border: 1px solid #bfdbfe;
margin-top: 40px;
text-align: center;
">

<h2 style="margin-top: 0;">
🔓 Mở khóa toàn bộ khóa C++
</h2>

<p style="max-width: 650px; margin: 10px auto; color: #374151;">
Khi đăng ký, học sinh sẽ được:
</p>

<div style="
display: grid;
grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
gap: 10px;
margin-top: 15px;
text-align: left;
">

<div>✔ Truy cập toàn bộ lộ trình 8 tuần</div>
<div>✔ Có tài khoản luyện tập trên OJ</div>
<div>✔ Có hint cho từng bài</div>
<div>✔ Video chữa bài đầy đủ</div>
<div>✔ Định hướng học rõ ràng</div>

</div>

<div style="margin-top: 25px;">

<a href="https://forms.gle/tFNgE7FiSq1LCSeC9"
   style="
   display: inline-block;
   padding: 12px 20px;
   background: #2563eb;
   color: white;
   border-radius: 10px;
   text-decoration: none;
   font-weight: 700;
   margin-right: 10px;
   ">
   👉 Điền form đăng ký
</a>

<a href="https://zalo.me/0906090788"
   style="
   display: inline-block;
   padding: 12px 20px;
   background: #16a34a;
   color: white;
   border-radius: 10px;
   text-decoration: none;
   font-weight: 700;
   ">
   💬 Liên hệ Zalo
</a>

</div>

<p style="margin-top: 20px; color: #6b7280; font-size: 0.95rem;">
Zalo: 0906 090 788 • Facebook: hoang.ha.9134 • Email: ha.hoangthi@gmail.com
</p>

</div>
