# Luyện tập sử dụng DIV và CSS để tạo bố cục cho trang web (Responsive)

Bài thực hành lập trình web — Sử dụng thẻ `<div>` và CSS (Flexbox, Grid, Media Queries) để xây dựng bố cục trang web chuẩn Responsive, hiển thị mượt mà trên Desktop, Tablet và Mobile.

---

## 🎯 Mục tiêu bài học

- Hiểu rõ cách sử dụng các thẻ khối `<div>` để phân vùng nội dung trên trang web.
- Áp dụng mô hình hộp (**Box Model**) với `box-sizing: border-box`.
- Sử dụng **Flexbox** để tạo bố cục đa cột linh hoạt, tránh lỗi tràn hay sụp layout.
- Áp dụng **Media Queries** (`@media screen and (max-width: ...)`) để website tự động co giãn và thích ứng với mọi kích thước màn hình.

---

## 📁 Cấu trúc thư mục

```
div-responsive-layout/
├── index.html   # Cấu trúc HTML phân vùng bằng thẻ <div>
├── style.css    # Định dạng CSS, Flexbox, Grid và Media Queries
└── README.md    # Hướng dẫn và tài liệu dự án
```

---

## 🖥️ Cấu trúc bố cục trang (Layout Structure)

```
┌─────────────────────────────────────────────────────────────┐
│                    .header (Logo & Banner)                  │
├─────────────────────────────────────────────────────────────┤
│         .navbar (Trang chủ | Giới thiệu | Khóa học...)       │
├────────────────┬───────────────────────────┬────────────────┤
│ .sidebar-left  │       .main-content       │ .sidebar-right │
│   (Danh mục,   │    (Bài viết nổi bật,     │   (Sự kiện,    │
│    hỗ trợ)     │     lưới tin tức 2 cột)   │   thông báo)   │
├────────────────┴───────────────────────────┴────────────────┤
│                 .footer (Bản quyền & Liên kết)              │
└─────────────────────────────────────────────────────────────┘
```

---

## 📱 Khả năng Responsive

| Thiết bị | Kích thước | Hành vi bố cục |
|---|---|---|
| **Desktop** | > 991px | 3 cột ngang (`.sidebar-left` 240px + `.main-content` linh hoạt + `.sidebar-right` 240px). Lưới bài viết 2 cột. |
| **Tablet** | 768px – 991px | 2 cột chính phía trên, `.sidebar-right` tự động chuyển xuống dưới dạng 2 cột song song. |
| **Mobile** | < 768px | Tất cả các khối tự động chuyển thành **1 cột dọc** (chiều rộng 100%), thanh menu xếp dọc dễ thao tác cảm ứng, không bị tràn màn hình. |

---

## 🔑 Kỹ thuật CSS mấu chốt

1. **Reset Box Model:**
   ```css
   * {
       box-sizing: border-box;
       margin: 0;
       padding: 0;
   }
   ```
2. **Container linh hoạt bằng Flexbox:**
   ```css
   .container {
       display: flex;
       gap: 20px;
   }
   ```
3. **Media Queries chuyển đổi sang 1 cột:**
   ```css
   @media screen and (max-width: 767px) {
       .container {
           flex-direction: column;
       }
       .sidebar-left, .main-content, .sidebar-right {
           width: 100%;
       }
   }
   ```

---

## 🚀 Cách chạy và kiểm tra

1. Mở file `index.html` trực tiếp trên bất kỳ trình duyệt nào (Chrome, Edge, Firefox).
2. Nhấn phím `F12` (hoặc chuột phải chọn **Inspect**).
3. Bấm vào biểu tượng **Toggle device toolbar** (Ctrl + Shift + M) để kiểm tra giao diện trên nhiều thiết bị như iPhone, iPad, màn hình Laptop.

---

## 👤 Thông tin học viên

- **Học viên:** Ha Thi My Binh
- **Khóa học:** CodeGym — Lập trình Web Frontend
