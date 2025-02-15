# E-Commerce Website

Một dự án trang web bán hàng sử dụng Jakarta EE, JSP, và Servlet, triển khai mô hình ba tầng (Three-Tier Architecture) với cơ sở dữ liệu MySQL và quản lý bằng Maven.

## Mục Lục
- [Giới thiệu](#giới-thiệu)
- [Công nghệ sử dụng](#công-nghệ-sử-dụng)
- [Cấu trúc thư mục](#cấu-trúc-thư-mục)
- [Chi tiết từng tầng](#chi-tiết-từng-tầng)
- [Hướng dẫn cài đặt](#hướng-dẫn-cài-đặt)
- [Thông tin liên hệ](#thông-tin-liên-hệ)

## Giới thiệu
Dự án này là một trang web bán hàng đơn giản, hỗ trợ ba vai trò:
- **Customer**: Khách hàng truy cập trang để mua sắm sản phẩm.
- **Employee**: Nhân viên quản lý đơn hàng.
- **Admin**: Quản trị viên quản lý người dùng, theo dõi báo cáo, và thực hiện các thiết lập cho trang.

## Công nghệ sử dụng
- **Jakarta EE**: Nền tảng phát triển ứng dụng web.
- **JSP và Servlet**: Xử lý logic của từng vai trò.
- **MySQL**: Cơ sở dữ liệu chính để lưu trữ thông tin.
- **Maven**: Quản lý các thư viện và phụ thuộc của dự án.

## Cấu trúc thư mục

```plaintext
CNPM
├── src
│   ├── main
│   │   ├── java
│   │   │   ├── com
│   │   │   │   └── Ergoffice
│   │   │   │       ├── model             # Tầng Model (Data Access Layer)
│   │   │   │       │   ├── Customer.java
│   │   │   │       │   ├── Employee.java
│   │   │   │       │   ├── Admin.java
│   │   │   │       │   ├── Product.java
│   │   │   │       │   ├── Order.java
│   │   │   │       │   └── DatabaseUtil.java
│   │   │   │       │
│   │   │   │       ├── dao                # Data Access Object (DAO) classes
│   │   │   │       │   ├── CustomerDAO.java
│   │   │   │       │   ├── EmployeeDAO.java
│   │   │   │       │   ├── AdminDAO.java
│   │   │   │       │   └── ProductDAO.java
│   │   │   │       │
│   │   │   │       ├── controller         # Tầng Controller (Business Logic Layer)
│   │   │   │       │   ├── CustomerServlet.java
│   │   │   │       │   ├── EmployeeServlet.java
│   │   │   │       │   ├── AdminServlet.java
│   │   │   │       │   └── ProductServlet.java
│   │   │   │       │
│   │   │   │       ├── service            # Các lớp Service (Logic, Validation)
│   │   │   │       │   ├── CustomerService.java
│   │   │   │       │   ├── EmployeeService.java
│   │   │   │       │   ├── AdminService.java
│   │   │   │       │   └── ProductService.java
│   │   │   │       │
│   │   │   │       └── util               # Các tiện ích khác
│   │   │   │           ├── DatabaseUtil.java
│   │   │   │           └── Constants.java
│   │   │   │
│   │   ├── resources                      # File cấu hình
│   │   │   └── META-INF
│   │   │       └── persistence.xml
│   │   │
│   │   └── webapp                         # Tầng View (Presentation Layer)
│   │       ├── WEB-INF
│   │       │   └── web.xml                # Cấu hình servlet
│   │       │
│   │       ├── customer                   # Giao diện cho Customer
│   │       │   ├── customerHome.jsp
│   │       │   ├── viewProduct.jsp
│   │       │   ├── cart.jsp
│   │       │   └── orderHistory.jsp
│   │       │
│   │       ├── employee                   # Giao diện cho Employee
│   │       │   ├── employeeHome.jsp
│   │       │   ├── manageOrders.jsp
│   │       │   └── manageInventory.jsp
│   │       │
│   │       ├── admin                      # Giao diện cho Admin
│   │       │   ├── adminHome.jsp
│   │       │   ├── manageUsers.jsp
│   │       │   ├── viewReports.jsp
│   │       │   └── siteSettings.jsp
│   │       │
│   │       ├── common                     # Các trang dùng chung
│   │       │   ├── header.jsp
│   │       │   └── footer.jsp
│   │       │
│   │       └── assets                     # Tài nguyên giao diện
│   │           ├── css
│   │           │   └── styles.css
│   │           ├── js
│   │           │   └── scripts.js
│   │           └── images
│   │               └── logo.png
│   │
├── pom.xml                                # Cấu hình Maven
└── README.md                              # Thông tin dự án
