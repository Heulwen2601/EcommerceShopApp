# EcommerceShopApp

Flutter ecommerce application built with Firebase.

## Tổng quan

Ứng dụng này là một dự án thương mại điện tử Flutter, bao gồm:
- Đăng nhập / đăng ký người dùng với Firebase Authentication
- Trang chủ sản phẩm, tìm kiếm, chi tiết sản phẩm
- Giỏ hàng và đặt hàng
- Quản lý địa chỉ, đơn hàng và sản phẩm
- Bảng điều khiển quản trị với quản lý sản phẩm, đơn hàng và người dùng
- Thay đổi thông tin người dùng: tên, email, mật khẩu, số điện thoại, ảnh đại diện

## Công nghệ chính

- Flutter
- Firebase: Authentication, Firestore, Storage, Cloud Functions
- Provider
- Image picker
- URL launcher
- Permission handler
- Firebase web config hỗ trợ cả web và nền tảng di động

## Cấu trúc chính

- `lib/main.dart`: Khởi tạo Firebase và chạy ứng dụng
- `lib/app.dart`: Thiết lập `MaterialApp` và theme
- `lib/wrappers/authentification_wrapper.dart`: Kiểm tra trạng thái xác thực và chuyển tới `HomeScreen` hoặc `SignInScreen`
- `lib/screens/`: chứa các màn hình chính của ứng dụng
  - `home/`: màn hình chính và ngăn kéo navigation
  - `sign_in/`, `sign_up/`: xác thực người dùng
  - `cart/`, `my_orders/`, `manage_addresses/`: quản lý giỏ hàng, đơn hàng, địa chỉ
  - `admin/`: bảng điều khiển admin
  - `product_details/`, `search_result/`, `category_products/`: hiển thị sản phẩm và tìm kiếm
  - `change_display_name/`, `change_display_picture/`, `change_email/`, `change_password/`, `change_phone/`: thay đổi thông tin người dùng
- `lib/models/`: định nghĩa mô hình dữ liệu như `Product`, `CartItem`, `OrderItem`, `Address`, `Review`
- `lib/services/`: logic kết nối Firebase, xác thực và truy xuất dữ liệu
- `lib/components/`: các widget dùng chung và giao diện tái sử dụng
- `lib/theme.dart`: cấu hình theme và phong cách cho app

## Tính năng nổi bật

- Xác thực Firebase: đăng nhập, đăng ký, đăng xuất
- Điều hướng dựa trên trạng thái người dùng
- Quản lý giỏ hàng và thanh toán đơn hàng
- Quản trị viên có thể quản lý sản phẩm, đơn hàng và người dùng
- Hỗ trợ thay đổi thông tin cá nhân và địa chỉ giao hàng
- Hỗ trợ đa nền tảng: Android/iOS/Web/Windows/Linux/macOS

## Cài đặt và chạy

1. Cài đặt Flutter SDK theo hướng dẫn chính thức
2. Mở terminal tại thư mục dự án
3. Chạy:

```bash
flutter pub get
```

4. Khởi chạy ứng dụng trên thiết bị hoặc trình giả lập:

```bash
flutter run
```

## Lưu ý cấu hình Firebase

- `lib/main.dart` chứa khởi tạo Firebase cho web với `FirebaseOptions` riêng.
- Trên Android/iOS, Firebase mặc định được khởi tạo bằng file cấu hình trong `android/app/google-services.json` và `ios/Runner/GoogleService-Info.plist`.

## Ghi chú thêm

- `pubspec.yaml` sử dụng font `Muli` và tài nguyên `assets/images/`, `assets/icons/`
- Gói `flutter_launcher_icons` dùng để tạo icon ứng dụng
- Dev dependencies: `build_runner`, `hive_generator`

## Chạy thử nghiệm

```bash
flutter test
```

> Nếu cần cấu hình Firebase riêng cho dự án, hãy đảm bảo tạo project Firebase phù hợp và cập nhật các file cấu hình cần thiết.
