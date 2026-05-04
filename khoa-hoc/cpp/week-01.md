---
layout: page
title: Tuần 1 - Làm quen với C++
permalink: /khoa-hoc/cpp/week-01/
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
.contest-button {
  display: inline-block;
  padding: 10px 16px;
  border-radius: 10px;
  text-decoration: none;
  font-weight: 700;
  background: #ea580c;
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
</style>

<div class="week-hero">

# Tuần 1 - Làm quen với C++

Tuần 1 giúp học sinh bắt đầu từ những thao tác đầu tiên trong C++: nhập xuất dữ liệu, khai báo biến và thực hiện các phép toán cơ bản.

Đây là tuần học miễn phí để học sinh làm quen với cách học của khóa: **đọc đề → tự làm → mở hint khi bí → xem video hướng dẫn sau khi đã thử**.

</div>

## 1. Tổng quan các bài trong tuần

<div class="week-image">
  <img src="/assets/images/cpp-week-01-overview.png" alt="Tổng quan các bài học tuần 1 - Làm quen với C++">
</div>

<div class="week-note">

👉 Bạn có thể thay ảnh trên bằng ảnh thật của tuần 1.  
Gợi ý tên file: `/assets/images/cpp-week-01-overview.png`

</div>

---

## 2. Video lý thuyết tuần 1

Trước khi làm bài, học sinh nên xem video lý thuyết để nắm cách viết chương trình C++ cơ bản, cách dùng `cin`, `cout`, biến và phép toán.

<div class="video-box">
  <div class="video-title">🎥 Video lý thuyết: Làm quen với C++</div>

  <div class="video-frame">
    <iframe 
      src="https://www.youtube.com/embed/VIDEO_LY_THUYET_TUAN_1?rel=0"
      frameborder="0"
      allowfullscreen>
    </iframe>
  </div>
</div>

---

## 3. Làm bài trong contest tuần 1

Toàn bộ bài tập tuần 1 được đặt trong một contest riêng trên Codeforces.

<div class="contest-box">

### 🚀 Contest tuần 1

<a class="contest-button" href="https://codeforces.com/group/PYFjMy37xA/contests">Vào contest tuần 1</a>

</div>

<div class="week-note">

👉 Nên làm bài theo thứ tự từ A đến O.  
Mỗi bài chỉ cần AC là đủ, chưa cần tối ưu phức tạp.

</div>

---

---

## 4. Danh sách bài tập tuần 1

👉 Làm bài theo thứ tự từ A → B → C → ...  
👉 Chỉ mở hint khi đã thử ít nhất 1–2 lần

---

### Bài A: Tổng A+B

<details>
<summary>💡 Hint</summary>

Nhập hai số `a`, `b`, sau đó in ra `a + b`.

</details>

---

### Bài B: Tính toán cơ bản

<details>
<summary>💡 Hint</summary>

Đọc kỹ đề để biết cần thực hiện những phép toán nào.  
Chú ý kiểu dữ liệu nếu có số thực.

</details>

---

### Bài C: Hình chữ nhật

<details>
<summary>💡 Hint</summary>

Chu vi = 2 × (dài + rộng)  
Diện tích = dài × rộng

</details>

---

### Bài D: Đường tròn

<details>
<summary>💡 Hint</summary>

Chu vi = 2 × pi × r  
Diện tích = pi × r × r

</details>

---

### Bài E: Độ dài

<details>
<summary>💡 Hint</summary>

Xác định đơn vị đầu vào và đơn vị cần đổi, sau đó viết công thức.

</details>

---

### Bài F: Độ C sang độ F

<details>
<summary>💡 Hint</summary>

F = C × 9 / 5 + 32

</details>

---

### Bài G: Độ F sang độ C

<details>
<summary>💡 Hint</summary>

C = (F − 32) × 5 / 9

</details>

---

### Bài O: Two Numbers

<details>
<summary>💡 Hint</summary>

Đọc kỹ đề để xác định phép toán cần thực hiện.

</details>

---

## 5. 🎥 Video chữa bài tuần 1

👉 Video này chữa toàn bộ các bài trong tuần.

<div class="video-box">
  <div class="video-title">Video chữa bài tuần 1</div>

  <div class="video-frame">
    <iframe 
      src="https://www.youtube.com/embed/VIDEO_TUAN_1?rel=0"
      frameborder="0"
      allowfullscreen>
    </iframe>
  </div>
</div>

---

💡 Gợi ý khi xem:

- Nếu bạn làm được bài → xem để kiểm tra cách làm  
- Nếu bạn chưa làm được → quay lại thử thêm 1 lần trước khi xem  

👉 Mục tiêu là hiểu cách nghĩ, không phải chỉ xem lời giải

---