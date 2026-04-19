<div align="center">

[![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&weight=700&size=50&pause=1000&color=00f2ff&center=true&vCenter=true&width=500&lines=sWEBAKARA+MANAGEMENT;sKARAOKE+3-TIER+APP;MODERN+DASHBOARD)](https://git.io/typing-svg)

<img src="https://img.shields.io/badge/version-1.0.0-blue?style=for-the-badge" alt="Version" />
<img src="https://img.shields.io/badge/license-ISC-green?style=for-the-badge" alt="License" />
<img src="https://img.shields.io/badge/status-Active-success?style=for-the-badge" alt="Status" />

<br/>

![NodeJS](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![Express](https://img.shields.io/badge/Express.js-000000?style=for-the-badge&logo=express&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white)
![Handlebars](https://img.shields.io/badge/Handlebars-000000?style=for-the-badge&logo=handlebarsdotjs&logoColor=white)
![Cloudinary](https://img.shields.io/badge/Cloudinary-3448C5?style=for-the-badge&logo=cloudinary&logoColor=white)

**Hệ thống quản lý Karaoke chuyên nghiệp với kiến trúc 3 lớp hiện đại, tối ưu hiệu năng và trải nghiệm người dùng!**

</div>

---

## Kiến Trúc Hệ Thống (3-Tier Architecture)

Dự án được xây dựng theo chuẩn mực thiết kế tách biệt các lớp trách nhiệm, giúp bảo trì và mở rộng dễ dàng:

- **Controller Layer**: Tiếp nhận và điều phối các yêu cầu từ Client.
- **Business Logic Layer (BUS)**: Xử lý các quy tắc nghiệp vụ phức tạp (tính tiền giờ, quản lý tồn kho).
- **Data Access Object (DAO)**: Giao tiếp trực tiếp với MongoDB để truy vấn dữ liệu.

```text
WebKara/
├── app/
│   ├── bus/          # Lớp xử lý nghiệp vụ chính
│   ├── controllers/  # Bộ điều khiển điều hướng yêu cầu
│   ├── dao/          # Lớp truy cập dữ liệu (Queries)
│   ├── model/        # Định nghĩa Schema Mongoose (MongoDB)
│   ├── routes/       # Cấu hình API và điều hướng trang
│   ├── middlewares/  # Bảo mật JWT & Phân quyền Staff/Manager
│   └── utils/        # Tiện ích bổ trợ toàn hệ thống
├── config/           # Cấu hình kết nối DB & Environment
├── public/           # Assets tĩnh (CSS, JS, Uploads local)
├── views/            # Giao diện Handlebars (Layouts & Partials)
└── app.js            # Entry Point của hệ thống
```

---

## Tính Năng Chủ Chốt

### Quản Lý Phòng Hát Thông Minh
- **Real-time Status**: Theo dõi trạng thái phòng (Trống, Đang hát, Đã đặt, Bảo trì) trực quan.
- **Pricing Engine**: Tự động tính tiền giờ theo bảng giá linh hoạt (Ngày/Đêm, Thường/Vip).
- **Equipment Tracking**: Quản lý chi tiết thiết bị (Loa, Mic, Tivi) lắp đặt trong từng phòng.

### Quản Lý Thực Đơn & Kho Hàng
- **Menu Đa Dạng**: Quản lý mặt hàng theo danh mục (Đồ uống, Thức ăn, Snacks).
- **Auto-Inventory**: Tự động trừ số lượng tồn kho ngay khi xuất hóa đơn dịch vụ.
- **Cảnh báo tồn kho**: Thông báo các mặt hàng sắp hết để nhập hàng kịp thời.

### Quy Trình Đặt Phòng & Thanh Toán
- **Booking Hub**: Ghi nhận đặt trước, quản lý thông tin khách hàng thân thiết.
- **Invoice Generation**: Xuất hóa đơn chi tiết bao gồm Tiền giờ + Dịch vụ + Thuế phí.
- **Optimistic Payment**: Quy trình thanh toán nhanh chóng, hỗ trợ chỉnh sửa trước khi tất toán.

### Bảo Mật & Phân Quyền
- **JWT & Cookie**: Xác thực an toàn, duy trì phiên làm việc ổn định.
- **Role-based Access Control (RBAC)**: Phân quyền chặt chẽ giữa Chủ cửa hàng (Manager) và Nhân viên (Staff).

---

## 💻 Tech Stack

### Backend Powerhouse
- **Runtime**: Node.js & Express Framework.
- **Database**: MongoDB (Mongoose) - Linh hoạt và tốc độ cao.
- **Auth**: JSON Web Token (JWT) + Bcryptjs mã hóa mật khẩu.
- **Storage**: Tích hợp Cloudinary cho việc quản lý ảnh phòng và mặt hàng.

### Frontend & UX/UI
- **View Engine**: Handlebars (HBS) với hệ thống Layout/Partials tối ưu UI.
- **Styles**: CSS3 Custom Design & Bootstrap components.
- **Icons**: FontAwesome & Lucide Icons.

---

## Hướng Dẫn Cài Đặt

### Yêu cầu hệ thống
- **Node.js**: Phiên bản 18 trở lên.
- **MongoDB**: Đã cài đặt MongoDB Local hoặc URI MongoDB Atlas.

### Các bước triển khai

1. **Cài đặt dependencies**:
   ```bash
   npm install
   ```

2. **Cấu hình biến môi trường**:
   Tạo file `.env` và điền đầy đủ các thông tin sau:
   ```env
   PORT=3000
   MONGODB_URI=your_uri_here
   JWT_SECRET=your_jwt_secret
   CLOUDINARY_CLOUD_NAME=your_name
   CLOUDINARY_API_KEY=your_key
   CLOUDINARY_API_SECRET=your_secret
   ```

3. **Khởi tạo Database (Seed Data)**:
   ```bash
   node setup-mongodb.js
   ```

4. **Khởi chạy Development Mode**:
   ```bash
   npm run start
   ```

---

<div align="center">

**Dự án được thiết kế với sự tỉ mỉ về UI/UX và độ ổn định Backend cao nhất!**

---

*Made with ❤️ by WebKara Team*

</div>
