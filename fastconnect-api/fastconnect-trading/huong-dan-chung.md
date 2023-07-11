---
description: >-
  FastConnect Trading (FCTrading) là bộ API cung cấp hỗ trợ khách hàng đặt, sửa,
  hủy lệnh và truy vấn thông tin tài khoản.
---

# Hướng dẫn chung

{% hint style="info" %}
SSI hỗ trợ môi trường Python và Node JS.
{% endhint %}

## 1. Quy trình tích hợp

Quy trình tích hợp bao gồm đăng ký sử dụng dịch vụ, Key Credential

### 1.1. Đăng ký dịch vụ

\-          Để tích hợp API FastConnect Trading cần

Giao diện iBoard

Bước 1: Khách hàng đến các chi nhánh/PGD của SSI hoặc đăng ký từ xa qua đường bưu điện/ nhân viên môi giới để đăng ký sử dụng dịch vụ FastConnect API.

Bước 2: Sau khi đăng ký thành công, hệ thống sẽ gửi email đến người dùng và giao diện trên Iboard

Màn hình hiển thị đã đăng ký dịch vụ thành công:

![](<../../.gitbook/assets/image (79).png>)

Màn hình thông tin dịch vụ đã đăng ký

![](<../../.gitbook/assets/image (60).png>)

Bước 3: Tạo Key kết nối để sử dụng dịch vụ

![](<../../.gitbook/assets/image (30).png>)

Key kết nối được tạo thành công

![](<../../.gitbook/assets/image (70).png>)

Bước 4: Lấy ConsumerID và ConsumerSecret thay vào file config: fc\_config (file trong thư mục giải nén khi tải client Python) hoặc file index.js (file trong thư mục giải nén khi tải client NodeJS) và điền đầy đủ các thông tin:

\+ TwoFAType: O là PIN và 1 là OTP (Mã OTP có khi sử dụng hàm GetOTP)

Ví dụ đối với client Python:

![](<../../.gitbook/assets/image (25).png>)

![](<../../.gitbook/assets/image (10).png>)

Bước 5: Lưu thông tin

### 1.2.  Key Credential

Thông tin cấu hình để tích hợp với FCTradingAPI

·         ConsumerID: Định danh tài khoản

·         ConsumerSecrect: Key truy cập server

·         PrivateKey: Được sử dụng để tạo chữ ký số bằng thuật toán RS256

## 2. Thông tin tích hợp

### 2.1. Chứ ký điện tử

Signature là một chuỗi ký tự được tạo ra từ một thuật toán cho trước, sử dụng để kiểm tra tính đúng đắn của dữ liệu trên đường truyền giữa 2 hệ thống. Một số thuật toán đang sử dụng là MD5, SHA256, RSA.\
Tham khảo thêm: [Wikipedia](https://en.wikipedia.org/wiki/HMAC)

Trong tài liệu này sử dụng thuật toán RSA + SHA256 để tạo Signature. Dữ liệu đầu vào bao gồm Secret Key và data, data là một json body chứa thông tin đặt/sửa/xóa

### 2.2. Python Client

#### 2.2.1. Cài đặt

\-          Yêu cầu cài đặt Python 3.x trở lên ( có thể tải bản python.org/downloads/release/python-370/)

{% hint style="info" %}
**Lưu ý**: Nhớ tick Add system path khi setup Python
{% endhint %}

\-          Khi cài đặt không sử dụng phiên bản Python mới nhất

Ví dụ: Nếu phiên bản 3.9 là bản mới nhất thì tải bản 3.8 đồ về bản 3.0

\-          Tải client và giải nén:

![](<../../.gitbook/assets/image (56).png>)

Bước 1: Giải nén

![](<../../.gitbook/assets/image (43).png>)

Bước 2: Gõ cmd vào ô địa chỉ thư mục để khởi tạo command line

![](<../../.gitbook/assets/image (99).png>)

Màn hình hiển thị cửa sổ như sau:

![](<../../.gitbook/assets/image (111).png>)

Bước 3: Điền thông tin trong file fc\_config.py tại thư mục examples

![](<../../.gitbook/assets/image (109).png>)

{% hint style="info" %}
**Lưu ý**: TwoFAType = 0: PIN và 1: OTP (SMS/ Email/ SmartOTP)
{% endhint %}

Bước 4: Cài đặt Client

Chạy câu lệnh

```
pip install ssi-fctrading
```

_Đối với Khách hàng là nhân viên và dùng mạng nội bộ công ty SSI_

Bước 4.1. Chạy câu lệnh

<pre><code><strong>npm config set strict-ssl false
</strong></code></pre>

Bước 4.2. Tiếp tục chạy câu lệnh

```
pip install --trusted-host pypi.org --trusted-host
files.pythonhosted.org --proxy=http://<username>:<password>@<host>:<port> dist/<tenthumuc>
```

{% hint style="info" %}
**Lưu ý**:

\+ username và password ( không có ký tự) đăng nhập tài khoản tại SSI.

\+ Nếu password có @ -> Chuyển thành %40
{% endhint %}

Ví dụ như ảnh:&#x20;

![](<../../.gitbook/assets/image (49).png>)

Bước 4.3. Chạy câu lệnh

```
pip install ssi-fctrading
```

Ví dụ như ảnh:&#x20;

![](<../../.gitbook/assets/image (37).png>)

Bước 5: Click douple vào file install\_example để chạy câu lệnh

Bước 6: Tiếp tục click douple vào file example\_api -> Cài đặt thành công như ảnh:

![](<../../.gitbook/assets/image (66).png>)

{% hint style="info" %}
**Lưu ý**:&#x20;

\+ Chỉ cài đặt 1 lần duy nhất. Lần tiếp chạy chỉ cần click douple vào file example\_api và example\_stream

* Đặt/sửa/hủy lệnh và truy vẫn thông tin tại link: http://127.0.0.1:8000/docs (khoanh đỏ trong ảnh)&#x20;
* Nghe streaming lệnh

\+ File example\_api và example\_streaming đã bao gồm hết các hàm trong link đính kèm
{% endhint %}

#### 2.2.2. Chạy Client

Mở link: [http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs) để đặt lệnh và truy vấn thông tin lệnh

![](<../../.gitbook/assets/image (98).png>)

#### 2.2.3. Streaming

* Click douple vào file example\_stream để nghe Streaming lệnh. Thông tin như ảnh:

![](<../../.gitbook/assets/image (64).png>)

### 2.3. NodeJS Client

#### 2.3.1. Cài đặt

* Máy tính có cài đặt NodeJS ( cài đặt từ bản v.10.15.3 trở lên)
* Kiểm tra máy tính đã cài đặt NodeJS và version: cmd node –version

![](<../../.gitbook/assets/image (110).png>)

* Tải client và giải nén:

![](<../../.gitbook/assets/image (84).png>)

Bước 1: Giải nén

![](<../../.gitbook/assets/image (9).png>)

Bước 2: Gõ cmd vào ô địa chỉ thư mục để khởi tạo command line

![](<../../.gitbook/assets/image (16).png>)

Màn hình hiển thị cửa sổ như sau:

![](<../../.gitbook/assets/image (34).png>)

Bước 3: Khi chạy xong gõ câu lệnh

```
npm install ssi-fctrading
```

_Đối với Khách hàng là nhân viên và dùng mạng nội bộ công ty SSI_

Bước 3.1. Chạy câu lệnh

```
npm config set strict-ssl false
```

Ví dụ như ảnh:&#x20;

![](<../../.gitbook/assets/image (13).png>)

Bước 3.2. Chạy tiếp câu lệnh

```
npm install --proxy http://<username>:<password>@<host>:<port> ssi-fctrading
```

Ví dụ như ảnh:&#x20;

![](<../../.gitbook/assets/image (106).png>)

Bước 3.3. Chạy tiếp câu lệnh&#x20;

```
npm install ssi-fctrading
```

Ví dụ như ảnh:&#x20;

![](<../../.gitbook/assets/image (20).png>)

Bước 4. Tiếp tục gõ câu lệnh: node index.js -> Enter

![](<../../.gitbook/assets/image (65).png>)

Bước 5: Giải nén client thành công:

#### 2.3.2. Chạy Client

* Để thuận tiện cho việc test dữ liệu từ Client, người dùng có thể sử dụng thông tin được điền sẵn trong file  index.js.
* Lấy Key được tạo ở Iboard thay vào file index.js và chạy lại cmd như sau:

Bước 1: Tạo Key ở IBoard:

![](<../../.gitbook/assets/image (95).png>)

Bước 2:

* Thay ConsumerID và ConsumerSecret vào file index.js:

![](<../../.gitbook/assets/image (31).png>)

Bước 3: Phương thức giao dịch của khách hàng

Bước 3.1:  Khách hàng sử dụng PIN để giao dịch:

* Điền PIN khách hàng giao dịch vào trường Code ở 2 hàm “mockStockData” và “mockDeterativeData”

![](<../../.gitbook/assets/image (22).png>)

\-> Lưu file index.js

Bước 4: Mở cmd và chạy lại câu lệnh: ctrl C -> node index.js

![](<../../.gitbook/assets/image (54).png>)

Bước 5: Giải nén và Cài đặt client thành công

![](<../../.gitbook/assets/image (39).png>)

Bước 6: Chạy trình duyệt hàm “/verifyCode” để verify mã PIN:

![](<../../.gitbook/assets/image (61).png>)

Bước 7: Đặt/ Hủy/ Sửa lệnh và Query thông tin lệnh như trước đây:

Ví dụ như ảnh:

![](<../../.gitbook/assets/image (76).png>)

Bước 3.2. Khách hàng sử dụng 2FA để giao dịch (SMS/ Email/ SmartOTP)

* Chạy trình duyệt hàm “/getOtp” để lẫy mã OTP ở điện thoại nếu là SMS/ SmartOTP hoặc OTP ở email nếu là Email

![](<../../.gitbook/assets/image (58).png>)

* Điền mã OTP nhận được vào trường code của 2 hàm “mockStockData” và “mockDeterativeData”

![](<../../.gitbook/assets/image (71).png>)

\-> Lưu file index.js

Bước 4: Mở cmd và chạy lại câu lệnh: ctrl C -> node index.js

![](<../../.gitbook/assets/image (28).png>)

Bước 5: Giải nén và Cài đặt client thành công

![](<../../.gitbook/assets/image (42).png>)

Bước 6: Đặt/ Hủy/ Sửa lệnh và Query thông tin lệnh

Ví dụ: Lấy thông tin Get MaxBuyQty

* Điền thông tin muốn truy vấn ở hàm accountBalance trong file index.js -> Save

![](<../../.gitbook/assets/image (1).png>)

* Mở trình duyệt và chạy câu lệnh: http://localhost:3012/accountBalance

![](<../../.gitbook/assets/image (44).png>)

#### 2.3.3.   Streaming Market data

Streaming trading chỉ có khi đặt/ sửa/ hủy lệnh

![](<../../.gitbook/assets/image (38).png>)
