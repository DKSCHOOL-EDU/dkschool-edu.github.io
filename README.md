# DKSCHOOL — Phòng thi trực tuyến THPT

> **Học Vững Kiến Thức - Chinh Phục Mọi Kì Thi**

## Cách đưa website lên GitHub Pages (chạy trực tiếp miễn phí)

1. Tạo một repository mới trên [GitHub](https://github.com/new) (chế độ **Public**, ví dụ đặt tên `dkschool`).
2. Giải nén gói `DKSCHOOL-GitHub-Pages.zip` và tải toàn bộ các file bên trong (`index.html`, `404.html`, `.nojekyll`, `robots.txt`, `sitemap.xml`, `README.md`) lên thư mục gốc của repository (chọn **Add file → Upload files → Commit changes**).
3. Vào **Settings → Pages**:
   - Mục **Build and deployment → Source**: chọn **Deploy from a branch**.
   - Mục **Branch**: chọn `main` và thư mục `/ (root)` → bấm **Save**.
4. Chờ khoảng 1–2 phút, website sẽ chạy tại địa chỉ:
   `https://<ten-tai-khoan-github>.github.io/<ten-repo>/`

## Lưu ý nếu có kết nối Firebase (Đăng nhập & Lưu dữ liệu đám mây)

- Vào **Firebase Console → Authentication → Settings → Authorized domains** → bấm **Add domain** và thêm `<ten-tai-khoan-github>.github.io` để Firebase cho phép đăng nhập từ link GitHub Pages.
- Dán nội dung file `firestore.rules` vào mục **Firestore Database → Rules** và bấm **Publish**.
