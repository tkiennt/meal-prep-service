# Meal Preparation & Virtual Fridge Management Service 🥗🍱

<div align="center">

![.NET](https://img.shields.io/badge/.NET-9.0%20Web%20API-512BD4?style=for-the-badge&logo=dotnet&logoColor=white)
![React](https://img.shields.io/badge/React-18-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript-5.0-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![SQL Server](https://img.shields.io/badge/SQL%20Server-2019+-CC2927?style=for-the-badge&logo=microsoftsqlserver&logoColor=white)
![Architecture](https://img.shields.io/badge/Architecture-N--Layer%20Clean-orange?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

**Hệ sinh thái lập kế hoạch bữa ăn thông minh, quản lý tủ lạnh ảo và điều phối nguyên liệu nấu ăn trực tuyến**

</div>

---

## 🍽️ 1. Giới thiệu Dự án (Project Overview)

**Meal Preparation Service** là giải pháp phần mềm toàn diện giúp người dùng giải quyết bài toán dinh dưỡng hàng ngày, chống lãng phí thực phẩm và tối ưu hóa thời gian chuẩn bị bữa ăn. Hệ thống kết hợp giữa tính năng **Quản lý Tủ lạnh ảo (Virtual Fridge)** để theo dõi nguyên liệu tồn kho theo hạn sử dụng, **Gợi ý & Lên lịch Thực đơn (Meal Planning)** phù hợp với chế độ ăn, cùng phân hệ **Tự động đặt mua nguyên liệu (Ingredient Ordering & Delivery Tracking)**.

Dự án được xây dựng theo chuẩn kiến trúc **N-Layer Enterprise Architecture** trên nền tảng **ASP.NET Core 9.0 Web API** kết hợp giao diện Web hiện đại bằng **React & TypeScript (Vite)**.

---

## 🚀 2. Các Phân hệ & Tính năng Chính (Core Features)

### 🧊 1. Quản lý Tủ lạnh ảo (Virtual Fridge Management)
- Ghi nhận nguyên liệu theo danh mục (thịt, cá, rau củ, gia vị...), số lượng và ngày hết hạn.
- Cảnh báo thực phẩm sắp hết hạn để ưu tiên chế biến, giảm thiểu tối đa tình trạng bỏ phí nguyên liệu.

### 📋 2. Lập kế hoạch Bữa ăn & Thực đơn (Meal Planning & Nutrition)
- Lên lịch bữa ăn theo ngày, tuần dựa trên nguyên liệu sẵn có trong tủ lạnh.
- Tính toán chỉ số dinh dưỡng (Calories, Protein, Carbs, Fats) tương ứng với từng khẩu phần.

### 🛒 3. Đi chợ Thông minh & Đặt hàng (Grocery Ordering)
- Tự động đối chiếu thực đơn với tủ lạnh ảo để sinh ra danh sách nguyên liệu cần mua bổ sung.
- Đặt hàng theo gói bữa ăn (Meal Kits) và theo dõi trạng thái giao vận theo thời gian thực.

### 📊 4. Bảng điều khiển Quản trị viên (Manager Dashboard UI)
- Quản lý danh mục món ăn, công thức nấu, kho hàng thực phẩm và báo cáo doanh thu.
- Tùy biến bảng màu giao diện thương hiệu, quản trị tài khoản và phân quyền người dùng.

---

## 🛠 3. Kiến trúc Hệ thống (System Architecture)

Hệ thống tuân thủ nghiêm ngặt **N-Layer Clean Architecture** với tính phân tách trách nhiệm cao:

```
swd392/
├── src/
│   ├── MealPreparationService.API/          # Tầng Trình diễn (Controllers, JWT Middleware, DTOs, Swagger)
│   ├── MealPreparationService.Business/     # Tầng Nghiệp vụ (Business Logic, Services, Nutrition Calculation)
│   ├── MealPreparationService.DataAccess/   # Tầng Truy xuất Dữ liệu (DbContext, Generic Repository, Unit of Work)
│   └── MealPreparationService.Domain/       # Tầng Thực thể Miền (Domain Entities, Enums)
├── frontend/                                # Ứng dụng Web Frontend (React + TypeScript + Vite)
├── document/                                # Tài liệu kỹ thuật, sơ đồ UML, mô tả dữ liệu database
└── prn222_asm_1/ & prn222_asm_2/            # Các phân hệ bài tập lập trình .NET C# nâng cao
```

---

## ⚙️ 4. Công nghệ Sử dụng (Tech Stack)

| Hạng mục | Công nghệ | Chi tiết |
| :--- | :--- | :--- |
| **Backend Framework** | **ASP.NET Core 9.0** | RESTful Web API hiệu năng cao |
| **Database** | **Microsoft SQL Server** | Cơ sở dữ liệu quan hệ, quan hệ nhiều-nhiều phức tạp |
| **ORM** | **Entity Framework Core 9.0** | Code-First Migrations, LINQ, Lazy/Eager Loading |
| **Frontend** | **React 18 + Vite** | Giao diện Single Page Application (SPA) tốc độ cao |
| **Ngôn ngữ** | **C# / TypeScript** | Kiểm soát kiểu dữ liệu tĩnh nghiêm ngặt cả 2 đầu |
| **Bảo mật & Auth** | **JWT Bearer + BCrypt** | Mã hóa mật khẩu an toàn, phân quyền Role-based |
| **API Documentation** | **Swagger / OpenAPI** | Trực quan hóa và kiểm thử API tương tác |

---

## 💻 5. Hướng dẫn Cài đặt & Khởi chạy (Getting Started)

### 1. Khởi động Backend API (.NET 9)
```bash
cd swd392/src/MealPreparationService.API

# Cập nhật chuỗi kết nối SQL Server trong appsettings.json nếu cần
dotnet restore
dotnet ef database update --project ../MealPreparationService.DataAccess

# Chạy Web API
dotnet run
# API khả dụng tại: https://localhost:5001/swagger
```

### 2. Khởi động Frontend Web (React + Vite)
```bash
cd swd392/frontend

# Cài đặt packages
npm install

# Chạy server phát triển
npm run dev
# Truy cập giao diện tại: http://localhost:5173
```

---

## 👥 6. Tác giả & Đóng góp (Credits)

- **Dự án phát triển bởi:** Đội ngũ phát triển Meal Preparation Service.
- **Thành viên đóng góp:** Trung Kiên ([@tkiennt](https://github.com/tkiennt)):
  - Trực tiếp xây dựng và thiết kế trọn bộ **Manager Dashboard UI** trên Frontend.
  - Thiết kế bảng màu và theme hệ thống (*System color palette*), chuẩn hóa các màn hình quản trị.
  - Đóng góp vào cấu trúc N-Layer và tích hợp các API quản lý dịch vụ bữa ăn.
