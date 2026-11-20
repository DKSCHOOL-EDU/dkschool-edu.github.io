# Hướng dẫn đăng DKSCHOOL lên Google (Firebase Hosting + Lưu tài khoản vĩnh viễn)

## Bước 1: Tạo dự án Firebase miễn phí
1. Truy cập https://console.firebase.google.com/ và bấm **Add project** (đặt tên ví dụ `dkschool-exam`).
2. Vào **Build → Authentication → Get started → Email/Password** và bật **Enable**.
3. Vào **Build → Firestore Database → Create database → Start in production mode** (chọn máy chủ `asia-southeast1` Singapore cho tốc độ nhanh nhất tại Việt Nam).

## Bước 2: Lấy mã cấu hình và dán vào web
1. Vào **Project Settings (biểu tượng bánh răng) → Your apps → Web (</>)** để đăng ký ứng dụng web.
2. Sao chép đoạn `firebaseConfig` (gồm `apiKey`, `authDomain`, `projectId`, `storageBucket`, `messagingSenderId`, `appId`).
3. Mở tệp `public/index.html`, tìm đoạn `const FIREBASE_CONFIG = { ... }` ở đầu phần `<script>` và dán các giá trị của bạn vào.
4. (Tùy chọn) Đổi `CLOUD_ADMIN_EMAIL = 'truongkhanhdkschool@gmail.com'` (và trong `firestore.rules`) thành email Admin của riêng bạn.

## Bước 3: Đẩy website và luật bảo mật lên Google
Cài đặt Node.js, sau đó mở Terminal/CMD ngay trong thư mục giải nén và chạy 4 lệnh:
```bash
npm install -g firebase-tools
firebase login
firebase use --add
firebase deploy
```
Sau khi hoàn tất, bạn sẽ nhận ngay đường link dạng `https://ten-du-an.web.app`.
- **Tạo tài khoản Admin đầu tiên:** Mở trang web của bạn, bấm **Đăng ký mới** bằng đúng email `CLOUD_ADMIN_EMAIL` → hệ thống tự gán quyền Quản trị viên.
- **Cập nhật web về sau không mất dữ liệu:** Mỗi khi sửa `public/index.html`, chỉ cần chạy lại `firebase deploy --only hosting`. Toàn bộ tài khoản, đề thi, điểm số và diễn đàn trong Firestore vẫn còn nguyên 100%.

## Bước 4: Đưa lên kết quả tìm kiếm Google
1. Cập nhật tên miền thật của bạn vào `public/robots.txt` và `public/sitemap.xml`.
2. Truy cập https://search.google.com/search-console/about, thêm đường link `.web.app` của bạn và gửi `sitemap.xml` để Google lập chỉ mục.
