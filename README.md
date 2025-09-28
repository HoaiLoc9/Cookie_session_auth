# 🍪 Cookie Session Auth

## 📌 Giới thiệu
Dự án này minh họa cách xây dựng hệ thống **Auth** dựa trên **Cookie + Session** với **Express.js** và **MongoDB**.  
Ứng dụng sử dụng `express-session` kết hợp với `connect-mongo` để lưu trữ session trong MongoDB, giúp quản lý đăng nhập an toàn và dễ kiểm soát.  

---

## ⚙️ Cài đặt & Chạy thử

### 1️⃣ Clone repo

git clone https://github.com/HoaiLoc9/Cookie_session_auth.git
cd Cookie_session_auth

### 2️⃣ Cài đặt dependencies

npm install

### 3️⃣ Chạy server

node app.js

### 🔑 Chức năng & Cách test với Postman
## 1. Register

Endpoint: POST http://localhost:3000/auth/register

Body (JSON): 
{
  "username": "admin",
  "password": "12345"
}

Kết quả: Tạo user mới trong MongoDB.

Ảnh minh họa:
![REGISTER](https://github.com/HoaiLoc9/Cookie_session_auth/blob/main/public/results/register.png?raw=true)

Check mongodb:
![CHECK MONGO](https://github.com/HoaiLoc9/Cookie_session_auth/blob/main/public/results/register_checkdb.png?raw=true)

## 2. Login

Endpoint: POST http://localhost:3000/auth/login

Body (JSON):
{
  "username": "admin",
  "password": "12345"
}

Kết quả: Tạo session mới trong MongoDB, sinh cookie connect.sid.

Ảnh minh họa:
![LOGIN](https://github.com/HoaiLoc9/Cookie_session_auth/blob/main/public/results/login.png?raw=true)

Check mongodb:
![LOGIN_CHECKDB](https://github.com/HoaiLoc9/Cookie_session_auth/blob/main/public/results/login_checkdb.png?raw=true)

## 3. Profile

Endpoint: GET http://localhost:3000/auth/profile

Kết quả:
Nếu đã login → hiển thị thông tin user.
Nếu chưa login → yêu cầu login.

Ảnh minh họa:
![Profile](https://github.com/HoaiLoc9/Cookie_session_auth/blob/main/public/results/profile.png?raw=true)

## 4. Logout

Endpoint: GET http://localhost:3000/auth/logout

Kết quả:
Xóa session trong MongoDB.
Cookie connect.sid bị xóa khỏi client.

Ảnh minh họa:
![Profile](https://github.com/HoaiLoc9/Cookie_session_auth/blob/main/public/results/logout.png?raw=true)

Check Mongo:
![Logout_Checkdb](https://github.com/HoaiLoc9/Cookie_session_auth/blob/main/public/results/logout_checkdb.png?raw=true)

cookie_session_auth/
│── app.js             
|── models/User.js
│── routes/auth.js      
│── public/results/     # Hình ảnh test bằng Postman
│   ├── register.png
│   ├── register_checkdb.png
│   ├── login.png
│   ├── login_checkdb.png
│   ├── profile.png
│   ├── logout.png
│   └── logout_checkdb.png
│── package.json
│── README.md


